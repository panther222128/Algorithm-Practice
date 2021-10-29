### Number Line Jumps

Source: <https://www.hackerrank.com/challenges/kangaroo/problem?isFullScreen=true>

Difficulty: Easy

```swift
func kangaroo(x1: Int, v1: Int, x2: Int, v2: Int) -> String {
    
    return v1 > v2 && (x2 - x1) % (v1 - v2) == 0 ? "YES" : "NO"
    
}
```
