### 442. Find All Duplicates in an Array

Source: <https://leetcode.com/problems/find-all-duplicates-in-an-array/>

Difficulty: Medium

```swift
// Solution 1
func findDuplicates(_ nums: [Int]) -> [Int] {
        
    var dict = [Int:Int]()
    var result = [Int]()
        
    for i in nums {
        dict[i, default: 0] += 1
    }
        
    for (key, value) in dict {
        if value > 1 {
            result.append(key)
        }
    }
        
    return result
        
}
 
// Solution 2
func findDuplicates(_ nums: [Int]) -> [Int] {
        
    let sorted = nums.sorted(by: < )
    
    var left = 0
    var right = 1
    var result = [Int]()
        
    while right < sorted.count {
        if sorted[left] == sorted[right] {
            result.append(sorted[right])
        }
        left += 1
        right += 1
    }
        
    return result
        
}
```
