### Time Conversion

Source: <https://www.hackerrank.com/challenges/mini-max-sum/problem?isFullScreen=true>

Difficulty: Easy

```swift
func timeConversion(s: String) -> String {
    
    let zero = "0"
    
    let fisrtIndex = s.index(s.startIndex, offsetBy: 0)
    let secondIndex = s.index(s.startIndex, offsetBy: 1)
    let forResultIndex = s.index(s.startIndex, offsetBy: 2)
    
    let firstTwo = s[fisrtIndex...secondIndex]
    
    let lastFirstIndex = s.index(s.startIndex, offsetBy: 9)
    let lastSecondIndex = s.index(s.startIndex, offsetBy: 8)
    
    let lastTwo = s[lastSecondIndex...lastFirstIndex]
    
    let firstTwoAfter = s[forResultIndex..<lastSecondIndex]
    
    if lastTwo == "AM" && Int(firstTwo)! < 12 {
        return String(s[..<lastSecondIndex])
    } else if lastTwo == "AM" && Int(firstTwo)! >= 12 {
        return zero+String(Int(firstTwo)!-12)+firstTwoAfter
    } else if lastTwo == "PM" && Int(firstTwo)! > 12 {
        return zero+String(Int(firstTwo)!-12)+firstTwoAfter
    } else if lastTwo == "PM" && Int(firstTwo)! < 12 {
        return "\(Int(firstTwo)!+12)"+firstTwoAfter
    } else if lastTwo == "PM" && Int(firstTwo)! == 12 {
        return String(s[..<lastSecondIndex])
    } else {
        return "ERROR"
    }
 
}
```
