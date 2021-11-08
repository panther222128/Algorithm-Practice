### Grading Students

Source: <https://www.hackerrank.com/challenges/grading/problem?isFullScreen=true>

Difficulty: Easy

```swift
func gradeRound(grade: Int) -> Int {
    let before: Double = Double(grade) / 10
    let ceiling = ceil(before)
    var multi = Int(ceiling * 10)
    if multi - grade > 5 {
        multi -= 5
    }
    if multi - grade < 3 {
        return multi
    } else {
        return grade
    }
}

func gradingStudents(grades: [Int]) -> [Int] {
    var result = [Int]()
    for i in grades {
        if i < 38 {
            result.append(i)
        }
        if i >= 38 {
            result.append(gradeRound(grade: i))
        }
    }
    return result
}
```
