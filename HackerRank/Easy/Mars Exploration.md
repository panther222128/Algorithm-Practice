### Mars Exploration

Source: <https://www.hackerrank.com/challenges/mars-exploration/problem?isFullScreen=true>

Difficulty: Easy

```swift
func marsExploration(s: String) -> Int {
    let char = Array(s)
    var result = 0
    for i in 0..<char.count {
        if i % 3 == 1 {
            if char[i] != "O" {
                result += 1
            }
        } else if i % 3 == 2 {
            if char[i] != "S" {
                result += 1
            }
        } else if i % 3 == 0 {
            if char[i] != "S" {
                result += 1
            }
        }
    }
    return result
}
```
