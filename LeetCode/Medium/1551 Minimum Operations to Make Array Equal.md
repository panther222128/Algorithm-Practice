Source: <https://leetcode.com/problems/minimum-operations-to-make-array-equal/>

Difficulty: Medium

```swift
func minOperations(_ n: Int) -> Int {
        
    var arr = [Int]()
        
    for i in 0...(n - 1) {
        arr.append(2 * i + 1)
    }
        
    var result = 0
        
    if arr.count % 2 == 0 {
        let middleInd = arr.count / 2
        let target = (arr[middleInd] + arr[middleInd - 1]) / 2
        for i in arr[middleInd...] {
            result += i - target
        }
    } else if arr.count % 2 == 1 {
        let middleInd = arr.count / 2
        let target = arr[middleInd]
        for i in arr[(middleInd + 1)...] {
            result += i - target
        }
    }
        
    return result
        
}
```
