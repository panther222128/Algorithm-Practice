### A Very Big Sum

Source: <https://www.hackerrank.com/challenges/a-very-big-sum/problem?isFullScreen=true>

Difficulty: Easy

```swift
func aVeryBigSum(ar: [Int]) -> Int {
    return ar.reduce(0) { $0 + $1 }
}
```
