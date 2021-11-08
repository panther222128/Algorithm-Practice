### Birthday Cake Candles

Source: <https://www.hackerrank.com/challenges/birthday-cake-candles/problem?isFullScreen=true>

Difficulty: Easy

```swift
func birthday(s: [Int], d: Int, m: Int) -> Int {
    var startIndex = 0
    var result = 0
    while startIndex + m < s.count + 1 {
        if s[temp..<m + temp].reduce(0, { $0 + $1 }) == d {
            result += 1
        }
        temp += 1
    }
    return result
}
```
