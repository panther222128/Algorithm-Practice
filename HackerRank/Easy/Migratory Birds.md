### Migratory Birds

Source: <https://www.hackerrank.com/challenges/migratory-birds/problem?isFullScreen=true>

Difficulty: Easy

```swift
func migratoryBirds(arr: [Int]) -> Int {
    var dict = [Int:Int]()
    for i in arr {
        dict[i, default: 0] += 1
    }
    let sorted = dict.sorted { $0.0 < $1.0 }
    let sort = sorted.sorted { $0.1 > $1.1 }
    return sort.first?.key ?? 0
}
```
