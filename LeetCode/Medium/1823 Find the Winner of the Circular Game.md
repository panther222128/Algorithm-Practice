Source: <https://leetcode.com/problems/find-the-winner-of-the-circular-game/>

Difficulty: Medium

```swift
func findTheWinner(_ n: Int, _ k: Int) -> Int {

    var arr = Array(1...n)
    if k == 1 {
        return arr[arr.count-1]
    } else {
        while arr.count != 1 {
            for i in 1...(k-1) {
                arr.append(arr.removeFirst())
            }
            arr.removeFirst()
        }
    }
    
    return arr[0]
    
}
```
