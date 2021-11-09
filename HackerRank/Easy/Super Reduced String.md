### Super Reduced String

Source: <https://www.hackerrank.com/challenges/reduced-string/problem?isFullScreen=true>

Difficulty: Easy

```swift
func superReducedString(s: String) -> String {
    
    var stack = [Character]()
    
    for i in s {
        if !stack.isEmpty && stack.last == i {
            stack.removeLast()
        } else {
            stack.append(i)
        }
    }
    
    if stack.isEmpty {
        return "Empty String"
    } else {
        return String(stack)
    }
    
}
```
