Source: <https://leetcode.com/problems/rabbits-in-forest/>

Difficulty: Medium

```swift
func numRabbits(_ answers: [Int]) -> Int {

    var setForDictKey = Set(answers)
    var result = 0
    var dict = [(Int, Int)]()
    
    for i in setForDictKey {
        let count = answers.filter { $0 == i }.count
        dict.append((i, count))
    }


    for i in dict {
        result += i.1 / (i.0 + 1) * (i.0 + 1)
        if i.1 % (i.0 + 1) > 0 {
            result += i.0 + 1
        } else {
            
        }
    }
    
    return result
    
}
```
