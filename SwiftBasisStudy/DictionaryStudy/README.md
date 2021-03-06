#Dictionary
字典是一种存储多个相同类型的值的容器。每个值（value）都关联唯一的键（key），键作为字典中的这个值数据的标识符。和数组中的数据项不同，字典中的数据项并没有具体顺序。

## 初始化空的Dictionary
```
    var namesOfIntegers = [Int: String]()

    if namesOfIntegers.isEmpty {
    print("nameofIntegers has no items")
    }

    var namesOfIntegers2 :Dictionary<Int,String> = [:];

    if namesOfIntegers2.isEmpty {
    print("nameOfIntegers isEmpty")
    }

    namesOfIntegers[16] = "sexteen"
```

## 初始化有初值的Dictionary
```
var airports :[String :String] = ["YYZ":"Toronto Person","DUB":"Dublin"];

var airports2 = ["YYY":"Toronto Person","DUB":"Dublin"]
```
## 增加或者修改一个值
```
airports ["YYZ"] = "Toronto Person2"

airports ["YYXX"] = "Toronto Person3"

print("now airports is \(airports)")
```
更新值updateValue (value, forKey: key)  返回旧值 （执行修改操作） ，不存在反回nil （执行插入操作）
```
if let oldValue = airports.updateValue("123", forKey: "YYX") {
print("\(airports)  The old Value of YYX is \(oldValue)")
} else {
print("\(airports)")
}

if let airportName = airports["YYX"] {
print("The name of airport is \(airportName)")
} else {
print("The airport is not in the Dictionary")
}

airports ["APL"] = "Apple International"

print(airports)
```
如果一个key的值被置为nil 那么那就被移除了也可以使用 removeValueForKey("APL")
```
airports ["APL"] = nil

print(airports)

if let oldValue = airports.removeValueForKey("APL") {
print("the \(oldValue) is removed from Dictionary")
} else {
print("the Key APL is not exists")
}
```
## 遍历Dictionary
```
for (airportcode,airportName) in airports {
print("\(airportcode): \(airportName)")
}

for key in airports.keys {
print(key)
}

for value in airports.values {
print(value)
}
```
获取的是无序的再末尾加上.sort() 就成为有序的了
```
  let keys = airports.keys

  let values = airports.values
```
