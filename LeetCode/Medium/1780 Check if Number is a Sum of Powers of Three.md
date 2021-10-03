### 1780. Check if Number is a Sum of Powers of Three

Source: <https://leetcode.com/problems/check-if-number-is-a-sum-of-powers-of-three/>

Difficulty: Medium

```swift
func checkPowersOfThree(_ n: Int) -> Bool {
        
    var origin = n
    var temp = [Int]()
        
    while origin != 0 {
        temp.append(origin % 3)
        origin = origin / 3
    }
        
    return !temp.contains(2)
        
}
```
