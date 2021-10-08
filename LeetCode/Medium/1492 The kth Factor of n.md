Source: <https://leetcode.com/problems/minimize-maximum-pair-sum-in-array/>

Difficulty: Medium

```swift
func kthFactor(_ n: Int, _ k: Int) -> Int {

    var temp = [Int]()
    
    for i in 1...n {
        if n % i == 0 {
            temp.append(i)
        }
    }
    
    if temp.count > k - 1 {
        return temp[k - 1]
    } else {
        return -1
    }

}
```
