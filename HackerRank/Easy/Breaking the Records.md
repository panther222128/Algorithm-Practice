### Breaking the Records

Source: <https://www.hackerrank.com/challenges/breaking-best-and-worst-records/problem?isFullScreen=true>

Difficulty: Easy

```swift
func breakingRecords(scores: [Int]) -> [Int] {
    
    var minTemp = scores[0]
    var maxTemp = scores[0]
    
    var minCount = 0
    var maxCount = 0
    
    for i in scores {
        if i < minTemp {
            minCount += 1
            minTemp = i
        }
        if i > maxTemp {
            maxCount += 1
            maxTemp = i
        }
    }
    
    return [maxCount, minCount]
    
}
```
