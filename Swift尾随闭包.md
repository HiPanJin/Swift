### Swift尾随闭包

闭包是一种自包含的功能块,它可以在代码中被传递和使用。当我们使用闭包作为函数的参数时,尾随闭包允许我们将闭包的实现写在函数调用的括号外面,以增加代码的可读性。

#### 1. 无参数无返回值的尾随闭包

```swift
func printLog(logClosure: () -> Void) {
  logClosure() 
}

printLog {
  print("Hi")
}
```

#### 2. 有参数无返回值的尾随闭包

```swift 
func printLog(message: String, logClosure: (String) -> Void) {
  logClosure(message)
}

printLog(message: "Hello") { message in
  print(message)
}
```

#### 3. 有参数有返回值的尾随闭包

```swift
func transform(value: String, transformClosure: (String) -> String) -> String {
  return transformClosure(value)
}

let result = transform(value: "Hello") { value in
  return "Hi, " + value 
}

print(result) // "Hi, Hello"
```

