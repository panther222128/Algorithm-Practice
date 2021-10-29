### Mini-Max Sum

Source: <https://www.hackerrank.com/challenges/mini-max-sum/problem?isFullScreen=true>

Difficulty: Easy

```swift
func miniMaxSum(arr: [Int]) -> Void {
    let sorted = arr.sorted()
    let mn = sorted[0...arr.count - 2].reduce(0) { $0 + $1 }
    let mx = sorted[1...].reduce(0) { $0 + $1 }
    print("\(mn) \(mx)")
}
```
