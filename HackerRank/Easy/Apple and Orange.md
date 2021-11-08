### Apple and Orange

Source: <https://www.hackerrank.com/challenges/apple-and-orange/problem?isFullScreen=true>

Difficulty: Easy

```swift
func countApplesAndOranges(s: Int, t: Int, a: Int, b: Int, apples: [Int], oranges: [Int]) -> Void {
    var applesInArea = 0
    var orangesInArea = 0
    for i in apples {
        if i + a <= t && i + a >= s {
            applesInArea += 1
        }
    }
    for i in oranges {
        if b + i <= t && b + i >= s {
            orangesInArea += 1
        }
    }
    print(applesInArea)
    print(orangesInArea)
}
```
