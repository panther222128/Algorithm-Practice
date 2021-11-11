### Pangrams

Source: <https://www.hackerrank.com/challenges/pangrams/problem?isFullScreen=true>

Difficulty: Easy

```swift
func pangrams(s: String) -> String {
    
    let lower = s.lowercased()
    let set = Set(lower)

    if set.contains(" ") {
        if set.count == 27 {
            return "pangram"
        } else {
            return "not pangram"
        }
    } else {
        if set.count == 26 {
            return "pangram"
        } else {
            return "not pangram"
        }
    }
    
}
```
