### HackerRank in a String!

Source: <https://www.hackerrank.com/challenges/hackerrank-in-a-string/problem?isFullScreen=true>

Difficulty: Easy

```swift
func hackerrankInString(s: String) -> String {
    
    let hackerrankChar: [Character] = ["h", "a", "c", "k", "e", "r", "r", "a", "n", "k"]
    var candidate: [Character] = []
    var ind = 0
    
    for i in s {
        if hackerrankChar.contains(i) {
            if i == hackerrankChar[ind] {
                ind += 1
                candidate.append(i)
            }
        }
        if candidate.count == hackerrankChar.count {
            break
        }
    }
    
    if candidate == hackerrankChar {
        return "YES"
    } else {
        return "NO"
    }
    
}
```
