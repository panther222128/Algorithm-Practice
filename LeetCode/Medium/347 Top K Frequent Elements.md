Source: <https://leetcode.com/problems/top-k-frequent-elements/>

Difficulty: Medium

```swift
func topKFrequent(_ nums: [Int], _ k: Int) -> [Int] {
        
    var dict = [Int:Int]()
    var result: [Int] = []
    
    for i in nums {
        dict[i, default: 0] += 1
    }
        
    let sorted = dict.sorted { $0.1 > $1.1 }
        
    for i in 0..<k {
        result.append(sorted[i].key)
    }
        
    return result
        
}
```
