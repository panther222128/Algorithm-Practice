### Caesar Cipher

Source: <https://www.hackerrank.com/challenges/caesar-cipher-1/problem?isFullScreen=true>

Difficulty: Easy

```swift
func caesarCipher(s: String, k: Int) -> String {
    
    if k == 0 {
        return s
    }
    
    let original = "abcdefghijklmnopqrstuvwxyz"
    var alternated = "abcdefghijklmnopqrstuvwxyz"
        
    for _ in 1...(k % 52) {
        alternated.append(alternated.removeFirst())
    }
    
    var dict = [Character:Character]()
    
    for i in 0..<original.count {
        dict[Array(original)[i], default: " "] = Array(alternated)[i]
    }
    
    var result = Array(s)
    
    for i in 0..<result.count {
        if result[i].isUppercase {
            if dict.keys.contains(Character(result[i].lowercased())) {
                let lower = result[i].lowercased()
                let altValue = dict[Character(lower)]?.uppercased()
                result[i] = Character(altValue?.uppercased() ?? "")
            }
        } else {
            if dict.keys.contains(result[i]) {
                guard let altValue = dict[result[i]] else { return "" }
                result[i] = altValue
            }
        }
        
    }
    
    return String(result)
    
}
```
