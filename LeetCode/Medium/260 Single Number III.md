### 260. Single Number III

Source: <https://leetcode.com/problems/single-number-iii/>

Difficulty: Medium

```swift
func singleNumber(_ nums: [Int]) -> [Int] {
        
    var dict = [Int:Int]()
    var result = [Int]()
        
    for i in nums {
        dict[i, default: 0] += 1
    }
        
    for (key, value) in dict {
        if value == 1 {
            result.append(key)
        }
    }
        
    return result
    
}
```
