### Birthday Cake Candles

Source: <https://www.hackerrank.com/challenges/birthday-cake-candles/problem?isFullScreen=true>

Difficulty: Easy

```swift
func birthdayCakeCandles(candles: [Int]) -> Int {
    return candles.filter { $0 == candles.max() }.count
}
```
