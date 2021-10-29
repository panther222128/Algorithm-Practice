### Plus Minus

Source: <https://www.hackerrank.com/challenges/plus-minus/problem?isFullScreen=true>

Difficulty: Easy

```swift
func plusMinus(arr: [Int]) -> Void {
    let plus = arr.filter { $0 > 0 }.count
    let minus = arr.filter { $0 < 0 }.count
    let zero = arr.filter { $0 == 0 }.count
    let flPlus = Float(plus)
    let flMinus = Float(minus)
    let flZero = Float(zero)
    let flCount = Float(arr.count)
    print(round(flPlus / flCount * 1000000) / 1000000)
    print(round(flMinus / flCount * 1000000) / 1000000)
    print(round(flZero / flCount * 1000000) / 1000000)
}
```
