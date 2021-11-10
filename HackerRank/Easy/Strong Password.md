### Strong Password

Source: <https://www.hackerrank.com/challenges/strong-password/problem?isFullScreen=true>

Difficulty: Easy

```swift
func minimumNumber(n: Int, password: String) -> Int {
    
    let spe = "!@#$%^&*()-+"
    var result = 0
    var temp = 0
    
    if password.filter ({ $0.isUppercase }).count == 0 {
        result += 1
    }
    
    if password.filter ({ $0.isLowercase }).count == 0 {
        result += 1
    }
    
    if password.filter ({ $0.isNumber }).count == 0 {
        result += 1
    }
    
    for i in password {
        if spe.contains(i) {
            temp += 1
        }
    }
    
    if temp == 0 {
        result += 1
    }
    
    let pwdCount = password.count + result
    
    if pwdCount < 6 {
        result += 6 - pwdCount
    }
    
    return result
    
}
```
