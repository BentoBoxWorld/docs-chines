# 简介

BentoBox 为开发人员提供了数据库 API，因此您无需自己创建数据库。可以选择将 BentoBox 数据库用于存储数据的方式，包括平面文件、MySQL、Mongo、SQLite、PostGreSQL、MariaDB 等等。您不必担心或关心使用的是哪一种。请注意，YAML 不再作为数据库的支持，但是通过 Config API 用于配置文件。

## 理念

我们采用了 BentoBox 数据库的 "NoSQL" 方法。也就是说，我们将序列化的 Java 对象存储为数据库中的 JSON "blob"。数据库中的每个表都被分配为存储特定的 Java 对象，例如岛屿、玩家、挑战等，表中的每个条目都是一个对象。表有两列 - 一个唯一的 ID 和 JSON 对象。像 PostgreSQL 这样的数据库可以以二进制形式存储这些 JSON 对象，这使得它们能够有效地处理这种方法。

### 我如何从 BentoBox 外部访问数据？
大多数支持的数据库，例如 MySQL、PostgreSQL 等，都支持直接在 JSON 数据上进行查询。唯一不支持的是基于平面文件的数据库，例如 JSON 和 SQLite。因此，您应该查阅关于如何在您的数据库中进行 JSON 查询的文档。

## 如何操作

要将类存储在 BentoBox 数据库中，请执行以下操作：

1. 创建一个扩展 DataObject 的类
2. 定义类的字段
3. 一个字段必须是名为 **uniqueId** 的字符串。这是数据库用来标识对象的唯一 ID（键）
4. 使用 @Expose 注释公开您想要存储在数据库中的每个字段
5. 确保类具有 [零参数构造函数](https://en.wikipedia.org/wiki/Nullary_constructor)
6. 为每个字段创建一个 getter 和 setter - 大多数 IDE 应该能够为您自动完成此操作

**警告：** 类的完整规范名称用于在数据库中创建表，但该名称的最大长度只能为 **64 个字符**。因此，在定义数据对象类时，请确保包和类名的长度足够短，以适应该限制。**另外**，由于 BentoBox 允许数据库表具有前缀，因此请确保您的规范名称总长度不超过约 60 个字符，以留出前缀的空间。

对于某些字段类型，特别是自定义类型，您可能需要定义自己的 Adapter 类来处理字段数据的序列化和反序列化。

## 示例
```
public class Names implements DataObject {

    @Expose
    private String uniqueId = ""; // 名称
    @Expose
    private UUID uuid;
    
    public Names() {}
    
    public Names(String name, UUID uuid) {
        this.uniqueId = name;
        this.uuid = uuid;
    }
    
    @Override
    public String getUniqueId() {
        return uniqueId;
    }

    @Override
    public void setUniqueId(String uniqueId) {
        this.uniqueId = uniqueId;        
    }

    /**
     * @return uuid
     */
    public UUID getUuid() {
        return uuid;
    }

    /**
     * @param uuid 要设置的 uuid
     */
    public void setUuid(UUID uuid) {
        this.uuid = uuid;
    }


}
```

## uniqueID

DataObject 接口合同要求您重写 getUniqueId() 和 setUniqueID() 方法。uniqueId 是一个字符串，用于在数据库中标识数据对象。典型的 uniqueId 是玩家的 UUID（转换为字符串）。如果只会有一个数据库对象，此 uniqueId 可以是一个常量，例如 "TopTen"。uniqueId 只需要在您创建的类型的数据对象范围内是唯一的。它不必对每个数据对象都是唯一的。

# 实例化数据库对象

创建数据对象后，必须实例化它才能使用。您可以通过创建一个新的 BSBDatabase 对象，第一个参数为 BSkyBlock，第二个参数为您的类，来实现这一点。例如：

`

BSBDatabase<Names> names = new BSBDatabase<>(plugin, Names.class);`

# 将数据保存到数据库

要将数据写入数据库，请执行以下操作：

1. 创建您的数据库对象的一个实例，在本示例中为 Names 类
2. 将数据放入其中，可以通过构造函数或使用 setter 方法
3. 使用 saveObject() 方法将其保存到数据库

例如：

`names.saveObject(new Names(user.getName(), user.getUniqueId()));`

您可以通过重复调用 saveObject 方法来将多个对象保存到数据库。如果对象的唯一 ID 与先前保存的对象相同，则会自动覆盖它。

# 从数据库加载数据

有两种加载数据的方法 - 按 uniqueId 加载特定记录（对象），或一次性加载此类型的所有对象。

## 加载单个对象

要做到这一点，您必须知道您想要的记录的 uniqueId。然后使用 loadObject 方法，将 uniqueId 作为参数。例如：

`Names loadedName = names.loadObject("tastybento");`

如果您知道您从加载的对象中需要什么数据，并且确定它存在，则可以直接获取它：

`UUID uuid = names.loadObject(string).getUuid();`

## 加载所有对象

有时您需要将整个数据库加载到内存中，以便随时访问。除非需要，否则尽量不要这样做。要加载所有对象，请使用 loadObjects() 方法。这将以列表的形式加载它们全部。例如：

`List<UUID> uuids = names.loadObjects();`

请注意，从数据库加载可能需要很长时间，因此不应在游戏过程中的主线程上执行。您应该能够在异步线程中加载对象。

# 检查对象是否存在于数据库中

要检查对象是否存在，您必须知道其 uniqueId。像这样检查它：

`return names.objectExists("tastybento") ? "他在数据库中存在" : "谁？";`

检查对象的存在也可能需要很长时间，因此如果可能，请不要在主线程上执行此操作。

# 在数据库中删除对象

删除对象需要您知道其 uniqueId。像这样删除对象：

`names.deleteObject("tastybento");`

如果无法删除对象，该方法将在控制台中记录错误，否则它将保持沉默。

目前，没有办法删除数据库中的所有对象。

# 关闭数据库

数据库连接在禁用插件时会自动关闭，但如果您希望显式关闭连接以节省资源，请使用此方法：

`names.close()`

这将立即释放连接对象的数据库和任何 JDBC 资源，而不是等待它们自动释放。

# 对象类型支持

*不再支持 YAML 数据库！*
数据库使用 GSON 对对象进行序列化。这处理大多数通用对象类型以及所有实现 [ConfigurationSerializable](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/configuration/serialization/ConfigurationSerializable.html) 接口的 Bukkit 类，例如：

* World
* 位置（Location）
* 向量（Vector，Bukkit 的向量）
* 药水效果类型（PotionEffectType）
* 等等

如果您实现了必须序列化并存储在数据库中的对象，则应该实现 Bukkit 的 [ConfigurationSerializable](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/configuration/serialization/ConfigurationSerializable.html) 接口。