Source: <https://leetcode.com/problems/partitioning-into-minimum-number-of-deci-binary-numbers/>

Difficulty: Medium

```swift
func minPartitions(_ n: String) -> Int {
    return n.map { Int(String($0)! }.max() ?? -1
}
```
