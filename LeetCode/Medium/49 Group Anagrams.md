Source: <https://leetcode.com/problems/group-anagrams/>

Difficulty: Medium

```swift
func groupAnagrams(_ strs: [String]) -> [[String]] {

    var temp = [String: [String]]()
    
    for i in 0..<strs.count {
        let mytemp = String(strs[i].sorted())
        temp[mytemp, default: []] += [strs[i]]
    }
        
    return Array(temp.values)
}
```
