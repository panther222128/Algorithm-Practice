### Compare the Triplets

Source: <https://www.hackerrank.com/challenges/compare-the-triplets/problem?isFullScreen=true>

Difficulty: Easy

```swift
func compareTriplets(a: [Int], b: [Int]) -> [Int] {
    var temp = [0, 0]
    for i in 0..<a.count {
        if a[i] > b[i] {
            temp[0] += 1
        } else if a[i] < b[i] {
            temp[1] += 1
        } else {
            
        }
    }
    return temp
}
```
