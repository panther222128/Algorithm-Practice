### CamelCase

Source: <https://www.hackerrank.com/challenges/camelcase/problem?isFullScreen=true>

Difficulty: Easy

```swift
func camelcase(s: String) -> Int {
    var result = 0
    for i in s {
        if i.isUppercase {
            result += 1
        }
    }
    return result + 1
}
```

```swift
func camelcase(s: String) -> Int {
    return s.filter { $0.isUppercase }.count + 1
}
```
