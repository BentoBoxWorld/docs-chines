# BentoBox 持久化元数据 API

BentoBox 提供了一个持久化元数据 API，允许在用户、玩家或岛屿上持久地存储元数据。
这使得不需要或不想处理自己的数据库存储的插件可以使用这个 API 来存储数据。
例如，边界插件（Border addon）只需要存储一个简单的布尔值来记录用户的边界是否开启。
将这个信息存储在数据库表中会是过度的，因此，插件可以通过 User 类将这个布尔值放入 Player 对象中。

## 快速示例

### 设置元数据
通过提供一个字符串键和一个带有你想要存储的对象的新 `MetaDataValue` 来设置元数据。
```
// 在用户上放置一个布尔标签，其值为 true，并将其命名为 Border_state
user.putMetaData("Border_state", new MetaDataValue(true));
```

### 检查元数据
通过提供一个字符串键来读取元数据。返回的是一个 `Optional`，你可以检查它是否存在
```
// 检查用户是否有名为 Border_state 的元数据
boolean on = user.getMetaData("Border_state").map(md -> md.asBoolean()).orElse(false);
```

记住，`getMetaData` 返回一个 `Optional`，所以如果你检查一个元数据键而它不存在，那么你会得到一个 `Optional.empty()`。
因此，如果你希望明确检查一个标签是否存在或不存在，使用 `isPresent()`：

```
if (user.getMetaData("My_key").isPresent()) {
    // 做一些事情
} else {
    // 做其他事情
}
```

当然，你也可以使用 `ifPresent()` 方法来执行像这样的操作：

```
user.getMetaData("My_key").ifPresent(key -> System.out.println("你的键值是 " + key.asInt()));
```

然而，通常情况下，你想要获取值并对其进行一些操作，因此 `map()` 和 `orElse()` 语法最为有用。

### 移除元数据
可以通过键从岛屿或用户上移除元数据。

示例：
```
island.removeMetaData("Bank_balance");
```
如果你希望检查数据是否真的被移除了，那么 `removeMetaData` 将返回一个 `MetaDataValue`，它将是被移除的数据，或者如果数据不存在，则为 `Optional.empty()` / `null`。

## 支持的值类型
你可以存储以下类型的元数据：

* String（字符串）
* Integer（整数）
* Float（浮点数）
* Double（双精度浮点数）
* Long（长整型）
* Short（短整型）
* Byte（字节）
* Boolean（布尔值）

## 获取器
虽然你可以存储数据而不必指定数据类型，但在获取数据时你必须使用正确的获取器。
如果不这样做，你的数据将是 `null`。获取器如下：

* `asInt()`
* `asFloat()`
* `asDouble()`
* `asLong()`
* `asShort()`
* `asByte()`
* `asBoolean()`
* `asString()`

示例：
```
String nameTag = user.getMetaData("Level_nametag").map(MetaData::asString).orElse("No nametag");
```

## 键命名约定
虽然键可以任意命名，但你应该避免与其他插件冲突，所以约定是以你的插件名称作为前缀。示例：

* Level_name
* Challenges_latestChallenge
* Border_state
* 等。

## 岛屿和玩家对象元数据
岛屿和玩家对象有与 User 类相同的元数据 API。虽然可以操作 Player 对象元数据，但最好通过 User 类 API 完成。

岛屿元数据在服务器关闭时或数据库定期保存时被保存。