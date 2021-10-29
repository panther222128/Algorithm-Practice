### Staircase

Source: <https://www.hackerrank.com/challenges/staircase/problem?isFullScreen=true>

Difficulty: Easy

```swift
func staircase(n: Int) -> Void {

    var result = ""

    for _ in 1...n {
        result.append(" ")
    }

    for _ in 1...n {
        result.removeFirst()
        result.append("#")
        print(result)
    }
}
```
