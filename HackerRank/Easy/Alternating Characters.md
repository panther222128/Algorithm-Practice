### Alternating Characters

Source: <https://www.hackerrank.com/challenges/alternating-characters/problem?isFullScreen=true>

Difficulty: Easy

```swift
func alternatingCharacters(s: String) -> Int {

    var stack = [Character]()
    
    for i in s {
        if stack.isEmpty {
            stack.append(i)
        } else {
            if stack.last! != i {
                stack.append(i)
            }
        }
    }
    
    return s.count - stack.count
    
}
```
