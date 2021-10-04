### 137. Single Number II

Source: <https://leetcode.com/problems/single-number-ii/>

Difficulty: Medium

```swift
func singleNumber(_ nums: [Int]) -> Int {
        
    var dict = [Int:Int]()
    var result = Int()
        
    for i in nums {
        dict[i, default: 0] += 1
    }
        
    for (key, value) in dict {
        if value == 1 {
            result = key
        }
    }
        
    return result
        
}
```
