# Swift for Algorithm

## 문자와 문자열

### 문자열의 수정

```swift
var variableString = "Cat"
variableString += "is cute"
// variableString = "Cat is cute"
```

### 반복문으로 문자 접근

```swift
for character in "cat" {
	print(character)
}
// c
// a
// t
```

### 문자 배열을 문자열로

```swift
let catChar: [Character] = ["C", "a", "t"]
let catString = String(catChar)
print(catString)
// "Cat"
```

### 문자열을 문자 배열로

```swift
var cuteCat = "CuteCat"
let catCharArray = cuteCat.map { $0 }
let catStrArray = cuteCat.map { String($0) }
catCharArray = ["C", "u", "t", "e", "C", "a", "t"]
catStrArray = ["C", "u", "t", "e", "C", "a", "t"]
```

### 문자열에 문자 결합

```swift
var cat = "Cat"
let exclamationMark: Character = "!"
cat.append(exclmationMark)
```

### 문자열의 길이

```swift
var strTest = "Cat"
strTest.count // 3
```

### 문자열의 시작과 끝 문자

```swift
var forestCat = "forestCat"
forest.prefix(1) // "f"
forest.suffix(1) // "t"
forest.prefix(2) // "fo"
forest.suffix(2) // "at"
```

### 문자열의 범위 추출

```swift
var forestCat = "forestCat"
var strRange = forestCat.index(forestCat.startIndex, offsetBy: 1)...forestCat.index(forestCat.endIndex, offsetBy: -2)
forestCat[strRange] // "orestCa"
```

### 문자열 대소문자 변경

```swift
var beautifulCat = "BeautifulCat"
beautifulCat.lowercased() // "beautifulcat"
beautifulCat.uppercased() // "BEAUTIFULCAT"
```

### 문자열 인덱스

```swift
var beautifulCat = "BeautifulCat"
beautifulCat[beautifulCat.startIndex] // "B"
beautifulCat[beautifulCat.index(after: beautifulCat.startIndex)] // "e"
beautifulCat[beautifulCat.index(before: beautifulCat.endIndex)] // "t"
beautifulCat[beautifulCat.index(beautifulCat.startIndex, offsetBy: 2)] // "a"
beautifulCat[beautifulCat.index(beautifulCat.endIndex, offsetBy: -2)] // "a"
```

---

## 배열

### 요소 접근

```swift
var catCharArray = ["C", "a", "t"]

catCharArray[0] // "C"
catCharArray[0..<2] // ["C", "a"]

// 첫 번째 요소
catCharArray.first // "C"

// 마지막 요소
catCharArray.last // "t"
```

### 요소 변경

```swift
var catCharArray = ["C", "a", "t"]

catCharArray[0] = "B"
catCharArray // ["B", "a", "t"]
```

### 요소 추가

```swift
var numbers = [0, 1, 2, 3, 4]

numbers.append(5)
numbers // [0, 1, 2, 3, 4, 5]

numbers += [6, 7]
numbers // [0, 1, 2, 3, 4, 5, 6, 7]

// 특정 인덱스 위치에 추가
numbers.insert(8, at: 8)
numbers // [0, 1, 2, 3, 4, 5, 6, 7, 8]
```

### 요소 삭제

```swift
// 특정 인덱스 요소 삭제
var numbers = [0, 1, 2, 3, 4, 5, 6, 7]

numbers.remove(at: 0)
numbers // [1, 2, 3, 4, 5, 6, 7]

// 첫 번째 요소 삭제
numbers.removeFirst()
numbers // [2, 3, 4, 5, 6, 7]

// 마지막 요소 삭제
numbers.removeLast()
numbers // [2, 3, 4, 5, 6]

// 특정 범위 삭제
numbers.removeSubrange(1..3)
numbers // [2, 6]

// 모든 요소 삭제
numbers.removeAll()
numbers // []

// 앞에서 n개 요소를 삭제한 배열 반환
numbers = [1, 2, 3, 4, 5, 6, 7]
numbers.dropFirst(2) // [3, 4, 5, 6, 7]
numbers // [1, 2, 3, 4, 5, 6, 7]

// 뒤에서 n개 요소를 삭제한 배열 반환
numbers = [1, 2, 3, 4, 5, 6, 7]
numbers.dropLast(2) // [1, 2, 3, 4, 5]
numbers // [1, 2, 3, 4, 5]
```

### 요소 인덱스 찾기

```swift
var numbers = [1, 2, 3, 4, 5, 6, 7, 1, 2, 3, 4]

numbers.firstIndex(of: 1) // 0
numbers.lastIndex(of: 1) // 7
```

### 요소 포함 여부

```swift
var numbers = [1, 2, 3, 4]

numbers.contains(1) // true
numbers.contains(5) // false
```

### 배열 크기

```swift
var numbers = [1, 2, 3, 4]

numbers.count // 4

// 빈 배열인지 여부
numbers.isEmpty // false
```

### 배열 뒤집기

```swift
var numbers = [1, 2, 3, 4]

numbers.reverse()
numbers // [4, 3, 2, 1]

// 기존 배열은 그대로 두고 뒤집힌 배열을 반환
var numbers = [1, 2, 3, 4]

numbers.reversed() // [4, 3, 2, 1]
numbers // [1, 2, 3, 4]
```

### 배열 정렬

```swift
var numbers = [2, 3, 1, 4]

numbers.sort()
numbers // [1, 2, 3, 4]

// 기존 배열은 그대로 두고 정렬된 배열을 반환
var numbers = [2, 3, 1, 4]

numbers.sorted() // [1, 2, 3, 4]
numbers = [2, 3, 1, 4]

// 내림차순 정렬
var numbers = [2, 3, 1, 4]

numbers.sort(by: >)
numbers // [4, 3, 2, 1]
```

### 배열 요소의 최대, 최소

```swift
var numbers = [1, 2, 3, 4, 5]

numbers.min() // 1, Optional
numbers.max() // 5, Optional
```

### 배열의 인덱스

```swift
var numbers = [1, 2, 3, 4, 6]

numbers.startIndex // 0
numbers.endIndex // 5
```

### 고차함수

```swift
// map
var numbers = [1, 2, 3, 4, 5]

numbers.map { $0 * 10 }
numbers // [1, 2, 3, 4, 5]
numbers = numbers.map { $0 * 10 }
numbers // [10, 20, 30, 40, 50]

// reduce
var numbers = [10, 20, 30, 40, 50]

let elementsSum = numbers.reduce(0) { $0 + $1 }
elementsSum = 150

// filter
var numbers = [10, 20, 30, 40, 50]

let twenty = numbers.filter { $0 == 20 }
twenty // [20]
```

---

## 딕셔너리

### 요소 접근

```swift
var dict = [1: "Cat", 2: "Dog", 3: "Otter"]

dict[1] // "Cat"
```

### 요소 변경

```swift
var dict = [1: "Cat", 2: "Dog", 3: "Otter"]

dict[1] = "Duck"

dict // [1: "Bat", 2: "Dog", 3: "Otter"}
```

### 요소 추가

```swift
var dict = [1: "Cat", 2: "Dog", 3: "Otter"]

dict[4] = "Duck"

dict // [1: "Cat", 2: "Dog", 3: "Otter", 4: "Duck"]
```

### 요소 삭제

```swift
var dict = [1: "Cat", 2: "Dog", 3: "Otter"]

dict.removeValue(forKey: 3)

dict // [1: "Cat", 2: "Dog"]

dict.removeAll()

dict // [:]
```

### 반복문으로 딕셔너리 접근

```swift
var dict = [1: "Cat", 2: "Dog", 3: "Otter"]

for i in dict {
    print(i)
}

// (key: 1, value: "Cat")
// (key: 2, value: "Dog")
// (key: 3, value: "Otter")

for (key, value) in dict {
    print(key)
}

// 0
// 1
// 2

for (key, value) in dict {
    print(value)
}

// "Cat"
// "Dog"
// "Otter"

for (key, value) in dict {
    print(key, value)
}

// 0 Cat
// 1 Dog
// 2 Otter
```

### 딕셔너리 크기

```swift
var dict = [1: "Cat", 2: "Dog", 3: "Otter"]

dict.count // 3

// 빈 배열인지 여부
numbers.isEmpty // false
```

### 딕셔너리 키 조회

```swift
var dict = [1: "Cat", 2: "Dog", 3: "Otter"]

dict.keys // 1, 2, 3
```

### 딕셔너리 값 조회

```swift
var dict = [1: "Cat", 2: "Dog", 3: "Otter"]

dict.values // "Cat", "Dog", "Otter"
```
