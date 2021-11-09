### Divisible Sum Pairs

Source: <https://www.hackerrank.com/challenges/divisible-sum-pairs/problem?isFullScreen=true>

Difficulty: Easy

```swift
func divisibleSumPairs(n: Int, k: Int, ar: [Int]) -> Int {
    
    var result = [[Int]]()

    for i in 0..<ar.count {
        for j in 0..<ar.count {
            if i < j {
                if (ar[i] + ar[j]) % k == 0 {
                    result.append([ar[i], ar[j]])
                }
            }
        }
    }
    
    return result.count
}
```
