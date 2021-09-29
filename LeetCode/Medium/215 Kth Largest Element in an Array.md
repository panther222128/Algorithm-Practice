Source: <https://leetcode.com/problems/kth-largest-element-in-an-array/>

Difficulty: Medium

```swift
func findKthLargest(_ nums: [Int], _ k: Int) -> Int {

    let sortedArray = nums.sorted(by: >)
    return sortedArray[k-1]
    
}
```
