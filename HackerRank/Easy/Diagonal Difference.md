### Diagonal Difference

Source: <https://www.hackerrank.com/challenges/diagonal-difference/problem?isFullScreen=true>

Difficulty: Easy

```swift
func diagonalDifference(arr: [[Int]]) -> Int {
    
    var first = Int()
    var second = Int()
    
    for i in 0..<arr.count {
        first += arr[i][i]
    }
    
    let a = arr.count-1
    
    for i in 0..<arr.count {
        second += arr[i][a-i]
    }
    
    return abs(first - second)
    
}
```
