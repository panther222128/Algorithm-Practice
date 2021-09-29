Source: <https://leetcode.com/problems/rotate-array/>

Difficulty: Medium

```swift
func rotate(_ nums: inout [Int], _ k: Int) {

    if k % nums.count > 0 {
        for i in 1...(k % nums.count) {
            nums.insert(nums.removeLast(), at: 0)
        }
    } else if nums.count == 1 {
            
    } else if k % nums.count == 0 {
        
    } else {
        
    }
    
}
```
