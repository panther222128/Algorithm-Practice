### Simple Array Sum

Source: <https://www.hackerrank.com/challenges/simple-array-sum/problem?isFullScreen=true>

Difficulty: Easy

```swift
func simpleArraySum(ar: [Int]) -> Int {
    return ar.reduce(0) { $0 + $1 }
}
```
