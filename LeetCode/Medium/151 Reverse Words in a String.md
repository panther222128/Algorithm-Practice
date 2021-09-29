Source: <https://leetcode.com/problems/reverse-words-in-a-string/>

Difficulty: Medium

```swift
func reverseWords(_ s: String) -> String {

    let words = s.components(separatedBy: " ").filter { $0 != "" }
    let reversedWords = Array(words.reversed())
        
    var result = ""
        
    for i in 0..<reversedWords.count {
        if i != reversedWords.count - 1 {
            result.append(reversedWords[i])
            result.append(" ")
        } else {
            result.append(reversedWords[i])
        }
    }
        
    return result
    
}
```
