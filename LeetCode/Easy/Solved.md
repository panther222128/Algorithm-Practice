### 1920. Build Array from Permutation

Source: <https://leetcode.com/problems/build-array-from-permutation/>

Difficulty: Easy

```swift
func buildArray(_ nums: [Int]) -> [Int] {
        
    var stack = [Int]()
    var result = [Int]()
    
    for i in 0..<nums.count {
        stack.append(nums[i])
    }

    for j in stack {
        result.append(nums[j])
    }
    
    return result
    
}
```

### 1929. Concatenation of Array

Source: <https://leetcode.com/problems/concatenation-of-array/>

Difficulty: Easy

```swift
func getConcatenation(_ nums: [Int]) -> [Int] {

    var stack = [Int]()
    
    for i in 0..<nums.count {
        stack.append(nums[i])
    }
    
    for i in 0..<nums.count {
        stack.append(nums[i])
    }
    
    return stack
    
}
```

### 1480. Running Sum of 1d Array

Source: <https://leetcode.com/problems/running-sum-of-1d-array/>

Difficulty: Easy

```swift
func runningSum(_ nums: [Int]) -> [Int] {

    var stack = [Int]()
    
    func sum(index: Int) -> Int {
        var temp = 0
        for i in 0...index {
            temp += nums[i]
        }
        return temp
    }
    
    for i in 0..<nums.count {
        stack.append(sum(index: i))
    }
    
    return stack
    
}
```

### 1108. Defanging an IP Address

Source: <https://leetcode.com/problems/defanging-an-ip-address/>

Difficulty: Easy

```swift
func defangIPaddr(_ address: String) -> String {

    var charArray = [String]()
        
    for i in address {
        charArray.append(String(i))
    }
        
    for i in 0..<charArray.count {
        if charArray[i] == "." {
            charArray[i] = String("[.]")
        }
    }
        
    var result = ""
    for i in 0..<charArray.count {
        result += String(charArray[i])
    }
    
    return result
    
}
```

### 1672. Richest Customer Wealth

Source: <https://leetcode.com/problems/richest-customer-wealth/>

Difficulty: Easy

```swift
func maximumWealth(_ accounts: [[Int]]) -> Int {
        
    var stack = [Int]()
    for i in accounts {
        let wealth = i.reduce(0) { $0 + $1 }
        stack.append(wealth)
    }
    
    return stack.max()!
    
}
```

### 1470. Shuffle the Array

Source: <https://leetcode.com/problems/shuffle-the-array/>

Difficulty: Easy

```swift
func shuffle(_ nums: [Int], _ n: Int) -> [Int] {
        
    let separator = nums.count / 2 - 1
    
    var firstHalf = [Int]()
    var lastHalf = [Int]()
    var result = [Int]()
    
    for i in 0...separator {
        firstHalf.append(nums[i])
    }
    
    for i in (separator + 1)..<nums.count {
        lastHalf.append(nums[i])
    }
    
    for i in 0..<first.count {
        result.append(firstHalf[i])
        result.append(lastHalf[i])
    }
    
    return result
    
}
```

### 1431. Kids With the Greatest Number of Candies

Source: <https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/>

Difficulty: Easy

```swift
func kidsWithCandies(_ candies: [Int], _ extraCandies: Int) -> [Bool] {

    var result = [Bool]()
    var can = candies
    
    for i in 0..<can.count {
        can[i] += extraCandies
        if can[i] == can.max()! {
            result.append(true)
        } else {
            result.append(false)
        }
        can[i] -= extraCandies
    }
    
    return result
}
```

### 1512. Number of Good Pairs

Source: <https://leetcode.com/problems/number-of-good-pairs/>

Difficulty: Easy

```swift
func numIdenticalPairs(_ nums: [Int]) -> Int {

    var count = 0
        
    for i in 0..<nums.count {
        for j in 0..<nums.count {
            if i < j && nums[i] == nums[j] {
                count += 1
            }
        }
    }
        
    return count
        
    }
```

### 771. Jewels and Stones

Source: <https://leetcode.com/problems/jewels-and-stones/>

Difficulty: Easy

```swift
func numJewelsInStones(_ jewels: String, _ stones: String) -> Int {
        
    var count = 0
        
    for i in jewels {
        count += stones.filter { $0 == i }.count
    }
        
    return count
    
}
```

### 1365. How Many Numbers Are Smaller Than the Current Number

Source: <https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/>

Difficulty: Easy

```swift
func smallerNumbersThanCurrent(_ nums: [Int]) -> [Int] {
        
    var result = [Int]()
        
    for i in nums {
        let smallerCount = nums.filter { $0 < i }.count
        result.append(smallerCount)
    }
        
    return result
}
```

### 1528. Shuffle String

Source: <https://leetcode.com/problems/shuffle-string/>

Difficulty: Easy

```swift
func restoreString(_ s: String, _ indices: [Int]) -> String {

    var temp = [(String, Int)]()
        
    for i in s {
        temp.append((String(i), 0))
    }
        
    for i in 0..<indices.count {
        temp[i].1 = indices[i]
    }
        
    var result = ""
        
    for i in 0..<temp.count {
        let a = temp.filter { $0.1 == i }[0].0
        result.append(a)
    }
    
    return result
    
}
```

### 1281. Subtract the Product and Sum of Digits of an Integer

Source: <https://leetcode.com/problems/subtract-the-product-and-sum-of-digits-of-an-integer/>

Difficulty: Easy

```swift
func subtractProductAndSum(_ n: Int) -> Int {

    var str = String(n)
    var temp = [String]()
    
    for i in str {
        temp.append(String(i))
    }
        
    var sum = 0
    var s = 1
    
    for i in temp {
        sum = sum + Int(i)!
    }
    
    for i in temp {
        s = s * Int(i)!
    }
        
    return s - sum
        
}
```

### 1313. Decompress Run-Length Encoded List

Source: <https://leetcode.com/problems/decompress-run-length-encoded-list/>

Difficulty: Easy

```swift
func decompressRLElist(_ nums: [Int]) -> [Int] {

    var result = [Int]()
    var num = nums
    
    while !num.isEmpty {
        for _ in 1...num[0] {
            result.append(num[1])
        }
        num.removeFirst()
        num.removeFirst()
    }
    
    return result
    
}
```

### 1342. Number of Steps to Reduce a Number to Zero

Source: <https://leetcode.com/problems/number-of-steps-to-reduce-a-number-to-zero/>

Difficulty: Easy

```swift
func numberOfSteps(_ num: Int) -> Int {

    var a = num
    var count = 0
    
    while a != 0 {
        if a % 2 == 0 {
            a = a / 2
            count += 1
        } else {
            a = a - 1
            count += 1
        }
    }
    
    return count
    
}
```

### 1389. Create Target Array in the Given Order

Source: <https://leetcode.com/problems/create-target-array-in-the-given-order/>

Difficulty: Easy

```swift
func createTargetArray(_ nums: [Int], _ index: [Int]) -> [Int] {

    var target = [Int]()
    
    for i in 0..<nums.count {
        target.insert(nums[i], at: index[i])
    }
    
    return target
    
}
```

### Count Items Matching a Rule

Source: <https://leetcode.com/problems/count-items-matching-a-rule/>

Difficulty: Easy

```swift
func countMatches(_ items: [[String]], _ ruleKey: String, _ ruleValue: String) -> Int {

    var index = 0
    var count = 0
        
    if ruleKey == "type" {
        index = 0
    } else if ruleKey == "color" {
        index = 1
    } else if ruleKey == "name" {
        index = 2
    }
        
    for i in items {
        if i[index] == ruleValue {
            count += 1
        } else {
                
        }
    }
    return count
}
```

### 1221. Split a String in Balanced Strings

Source: <https://leetcode.com/problems/split-a-string-in-balanced-strings/>

Difficulty: Easy

```swift
func balancedStringSplit(_ s: String) -> Int {

    var count = 0
    var temp = 0
    
    for i in s {
        if i == "L" {
            count += 1
            if count == 0 {
                temp += 1
            } else {
                
            }
        } else if i == "R" {
            count -= 1
            if count == 0 {
                temp += 1
            } else {
                    
            }
        } else {
                
        }
    }
    return temp
}
```

### 1791. Find Center of Star Graph

Source: <https://leetcode.com/problems/find-center-of-star-graph/>

Difficulty: Easy

```swift
func findCenter(_ edges: [[Int]]) -> Int {

    let first = edges[0].sorted()
    let second = edges[1].sorted()
        
    if first[0] == second[0] {
        return first[0]
    } else {
        return first[1]
    }
    
}
```

### 1859. Sorting the Sentence

Source: <https://leetcode.com/problems/sorting-the-sentence/>

Difficulty: Easy

```swift
func sortSentence(_ s: String) -> String {
        
    var stringArray = s.components(separatedBy: " ")

    var index = [(Int, String)]()

    for i in stringArray {
        let range = i.index(i.startIndex, offsetBy: 0)...i.index(i.endIndex, offsetBy: -2)
        index.append((Int(i.suffix(1))!, String(i[range])))
    }
        
    var result = ""
        
    for i in 1...index.count {
        let filter = index.filter { $0.0 == i }[0].1
        result.append(filter)
        if i != index.count {
            result.append(" ")
        }
    }
        
    return result
        
}
```

### 1688. Count of Matches in Tournament

Source: <https://leetcode.com/problems/count-of-matches-in-tournament/>

Difficulty: Easy

```swift
func numberOfMatches(_ n: Int) -> Int {
        
    var teams = n
    var count = 0
        
    func cal(input: Int) {
        if teams % 2 == 0 {
            count += teams / 2
            teams = teams / 2
        } else if teams % 2 == 1 {
            count += (teams - 1) / 2
            teams = teams / 2 + 1
        }
    }
        
    while teams != 1 {
        cal(input: teams)
    }
        
    return count
    
}
```

### 1662. Check If Two String Arrays are Equivalent

Source: <https://leetcode.com/problems/check-if-two-string-arrays-are-equivalent/>

Difficulty: Easy

```swift
func arrayStringsAreEqual(_ word1: [String], _ word2: [String]) -> Bool {

    var one = ""
    var two = ""
        
    for i in word1 {
        one += i
    }
        
    for i in word2 {
        two += i
    }
        
    return one == two
    
}
```

### 1832. Check if the Sentence Is Pangram

Source: <https://leetcode.com/problems/check-if-the-sentence-is-pangram/>

Difficulty: Easy

```swift
func checkIfPangram(_ sentence: String) -> Bool {
    
    var set = Set<Character>()
    
    for i in sentence {
        set.insert(i)
    }
        
    if set.count < 26 {
        return false
    } else {
        return true
    }
    
}
```

### 1684. Count the Number of Consistent Strings

Source: <https://leetcode.com/problems/count-the-number-of-consistent-strings/>

Difficulty: Easy

```swift
func countConsistentStrings(_ allowed: String, _ words: [String]) -> Int {

    var allowedArray = Array(allowed)
    var allowedSet = Set(allowedArray)
    var result = 0
        
    for i in words {
        let wordsCount = i.count
        var count = 0
        for j in i {
            for k in allowedSet {
                if j == k {
                    count += 1
                }
            }
        }
        if count == wordsCount {
            result += 1
        }
    }
        
    return result
        
}
```

### 1913. Maximum Product Difference Between Two Pairs

Source: <https://leetcode.com/problems/maximum-product-difference-between-two-pairs/>

Difficulty: Easy

```swift
func maxProductDifference(_ nums: [Int]) -> Int {
        
    let ordered = nums.sorted(by: < )
    let min = ordered[0] * ordered[1]
    let max = ordered[ordered.count-2] * ordered[ordered.count-1]
        
    return max - min
        
}
```

### 709. To Lower Case

Source: <https://leetcode.com/problems/to-lower-case/>

Difficulty: Easy

```swift
func toLowerCase(_ s: String) -> String {

    return s.lowercased()
    
}
```

### 1979. Find Greatest Common Divisor of Array

Source: <https://leetcode.com/problems/find-greatest-common-divisor-of-array/>

Difficulty: Easy

```swift
func findGCD(_ nums: [Int]) -> Int {

    let maxValue = nums.max()!
    let minValue = nums.min()!
    
    var value = Int()        
    var maxGCD = [Int]()
    var minGCD = [Int]()
        
    for i in 1...maxValue {
        if maxValue % i == 0 {
            maxGCD.append(i)
        }
    }
        
    for i in 1...minValue {
        if minValue % i == 0 {
            minGCD.append(i)
        }
    }
        
    for i in maxGCD {
        for j in minGCD {
            if i == j {
                value = max(i, value)
            }
        }
    }
        
    return value
    
}
```

### 1816. Truncate Sentence

Source: <https://leetcode.com/problems/truncate-sentence/>

Difficulty: Easy

```swift
func truncateSentence(_ s: String, _ k: Int) -> String {

    let str = s.components(separatedBy: " ")
    var result = ""
        
    for i in 0..<k {
        result.append(String(str[i]))
        result.append(" ")
    }
    
    result.removeLast()
    
    return result
    
}
```

### 1844. Replace All Digits with Characters

Source: <https://leetcode.com/problems/replace-all-digits-with-characters/>

Difficulty: Easy

```swift
func replaceDigits(_ s: String) -> String {

    let dict: [(Int, Character)] = [(0, "a"), (1, "b"), (2, "c"), (3, "d"), (4, "e"),
                                    (5, "f"), (6, "g"), (7, "h"), (8, "i"), (9, "j"),
                                    (10, "k"), (11, "l"), (12, "m"), (13, "n"), (14, "o"),
                                    (15, "p"), (16, "q"), (17, "r"), (18, "s"), (19, "t"),
                                    (20, "u"), (21, "v"), (22, "w"), (23, "x"), (24, "y"),
                                    (25, "z")]

    var temp = [Character]()
    
    for i in s {
        if i.isLetter {
            temp.append(i)
        } else {
            let leftInt = dict.filter { $0.1 == temp.last }[0].0
            let index = leftInt + Int(String(i))!
            let filter = dict.filter { $0.0 == index }[0].1
            temp.append(filter)
        }
    }
    
    return String(temp)
    
}
```

### 2000. Reverse Prefix of Word

Source: <https://leetcode.com/problems/reverse-prefix-of-word/>

Difficulty: Easy

```swift
func reversePrefix(_ word: String, _ ch: Character) -> String {

    let charArr = Array(word)
        
    if !charArr.contains(ch) {
        return word
    } else {
        let firstInd = charArr.firstIndex(of: ch)!
        let left = charArr[0...firstInd].reversed()
        let right = charArr[(firstInd + 1)...]
        return String(left) + String(right)
    }
        
}
```

### 1572. Matrix Diagonal Sum

Source: <https://leetcode.com/problems/matrix-diagonal-sum/>

Difficulty: Easy

```swift
func diagonalSum(_ mat: [[Int]]) -> Int {

    var value = 0
    
    for i in 0..<mat.count {
        value += mat[i][i]
    }
    
    for i in 0..<mat.count {
        value += mat[mat.count - 1 - i][i]
    }
    
    if mat.count % 2 == 1 {
        value -= mat[mat.count / 2][mat.count / 2]
        return value
    } else {
        return value
    }
    
}
```

### 1295. Find Numbers with Even Number of Digits

Source: <https://leetcode.com/problems/find-numbers-with-even-number-of-digits/>

Difficulty: Easy

```swift
func findNumbers(_ nums: [Int]) -> Int {

    let strNums = nums.map { String($0) }
    var count = 0
    
    for i in strNums {
        if i.count % 2 == 0 {
            count += 1
        } else {
            count += 0
        }
    }
    
    return count
    
}
```

### 1464. Maximum Product of Two Elements in an Array

Source: <https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/>

Difficulty: Easy

```swift
func maxProduct(_ nums: [Int]) -> Int {

    let ordered = nums.sorted(by: < )
    let max = ordered[ordered.count - 1]
    let maxLagged = ordered[ordered.count - 2]
        
    return (max - 1) * (maxLagged - 1)
    
}
```

### 1967. Number of Strings That Appear as Substrings in Word

Source: <https://leetcode.com/problems/number-of-strings-that-appear-as-substrings-in-word/>

Difficulty: Easy

```swift
func numOfStrings(_ patterns: [String], _ word: String) -> Int {

    var count = 0
    
    for i in patterns {
      if word.contains(i) {
            count += 1
        }
    }
    
    return count
    
}
```

### 1436. Destination City

Source: <https://leetcode.com/problems/destination-city/>

Difficulty: Easy

```swift
func destCity(_ paths: [[String]]) -> String {

    var dict = [String:String]()
    var current = paths[0][0]
    
    for i in paths {
        dict[i[0]] = i[1]
    }
        
    while dict.keys.contains(current) {
        current = dict[current]!
    }
        
    return current
    
}
```

### 1941. Check if All Characters Have Equal Number of Occurrences

Source: <https://leetcode.com/problems/check-if-all-characters-have-equal-number-of-occurrences/>

Difficulty: Easy

```swift
func areOccurrencesEqual(_ s: String) -> Bool {

    var dict = [String:Int]()
        
    for i in s {
        dict[String(i), default: 0] += 1
    }
        
    var count = [Int]()
        
    for (key, value) in dict {
        count.append(value)
    }
        
    if count.filter { $0 == count[0] }.count == count.count {
        return true
    } else {
        return false
    }
    
}
```

### 1450. Number of Students Doing Homework at a Given Time

Source: <https://leetcode.com/problems/number-of-students-doing-homework-at-a-given-time/>

Difficulty: Easy

```swift
func busyStudent(_ startTime: [Int], _ endTime: [Int], _ queryTime: Int) -> Int {

    var count = 0
    
    for i in 0..<startTime.count {
        if startTime[i] <= queryTime && endTime[i] >= queryTime {
            count += 1
        }
    }
    
    return count
    
}
```

### 728. Self Dividing Numbers

Source: <https://leetcode.com/problems/self-dividing-numbers/>

Difficulty: Easy

```swift
func isSelfDivi(input: Int) -> Bool {

    let temp = Array(String(input))
    var stack = [Character]()
    var ind = 0
        
    if temp.contains("0") {
        return false
    }
        
    while ind < temp.count {
        if input % Int(String(temp[ind]))! == 0 {
            stack.append(temp[ind])
        }
        ind += 1
    }
    
    return stack.count == temp.count
    
}
    
func selfDividingNumbers(_ left: Int, _ right: Int) -> [Int] {

    var result = [Int]()
        
    for i in left...right {
        if isSelfDivi(input: i) {
            result.append(i)
        }
    }
    
    return result
    
}
```

### 1837. Sum of Digits in Base K

Source: <https://leetcode.com/problems/sum-of-digits-in-base-k/>

Difficulty: Easy

```swift
func sumBase(_ n: Int, _ k: Int) -> Int {

    var temp = n
    var str = ""
    
    while temp != 0 {
            str += String(temp % k)
            temp = temp / k
    }
        
    var result = 0
        
    for i in str {
        result += Int(String(i))!
    }
    return result
    
}
```

### 1351. Count Negative Numbers in a Sorted Matrix

Source: <https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/>

Difficulty: Easy

```swift
func countNegatives(_ grid: [[Int]]) -> Int {

    var count = 0
    
    for i in 0..<grid.count {
        for j in 0..<grid[0].count {
            if grid[i][j] < 0 {
                count += 1
            }
        }
    }
    
    return count
        
}
```

### 961. N-Repeated Element in Size 2N Array

Source: <https://leetcode.com/problems/n-repeated-element-in-size-2n-array/>

Difficulty: Easy

```swift
func repeatedNTimes(_ nums: [Int]) -> Int {
        
    var count = 0
    var sorted = nums.sorted()
    var left = sorted[count]
    var right = sorted[count+1]
        
    while left != right {
        count += 1
        left = sorted[count]
        right = sorted[count+1]
    }
    
    return left
        
}
```

### 905. Sort Array By Parity

Source: <https://leetcode.com/problems/sort-array-by-parity/>

Difficulty: Easy

```swift
func sortArrayByParity(_ nums: [Int]) -> [Int] {

    let even = nums.filter { $0 % 2 == 0 }
    let odd = nums.filter { $0 % 2 == 1 }
    var result = [Int]()
    
    for i in even {
        result.append(i)
    }
        
    for i in odd {
        result.append(i)
    }
    
    return result
        
}
```

### 1748. Sum of Unique Elements

Source: <https://leetcode.com/problems/sum-of-unique-elements/>

Difficulty: Easy

```swift
func sumOfUnique(_ nums: [Int]) -> Int {

    var dict = [Int:Int]()
    
    for i in nums {
        dict[i, default: 0] += 1
    }
    
    var result = 0
    
    for (key, value) in dict {
        if value == 1 {
            result += key
        }
    }
    
    return result
    
}
```

### 1475. Final Prices With a Special Discount in a Shop

Source: <https://leetcode.com/problems/final-prices-with-a-special-discount-in-a-shop/>

Difficulty: Easy

```swift
func finalPrices(_ prices: [Int]) -> [Int] {

    var result = [Int]()
    
    for i in 0..<prices.count {
        let filter = prices[(i + 1)...].filter { $0 <= prices[i] }
        if filter.isEmpty {
            result.append(prices[i])
        } else {
            result.append(prices[i] - filter.first!)
        }
    }
    
    return result
    
}
```

### 657. Robot Return to Origin

Source: <https://leetcode.com/problems/robot-return-to-origin/>

Difficulty: Easy

```swift
func judgeCircle(_ moves: String) -> Bool {

    let uCount = moves.filter { $0 == "U" }.count
    let dCount = moves.filter { $0 == "D" }.count * -1
    let rCount = moves.filter { $0 == "R" }.count
    let lCount = moves.filter { $0 == "L" }.count * -1
        
    if uCount + dCount == 0 && rCount + lCount == 0 {
        return true
    } else {
        return false
    }
        
}
```

### 561. Array Partition I

Source: <https://leetcode.com/problems/array-partition-i/>

Difficulty: Easy

```swift
func arrayPairSum(_ nums: [Int]) -> Int {

    let sorted = nums.sorted(by: >)
    var i = 1
    var result = 0
    
    while i < sorted.count {
        result += sorted[i]
        i += 2
    }
    
    return result
    
}
```

### 557. Reverse Words in a String III

Source: <https://leetcode.com/problems/reverse-words-in-a-string-iii/>

Difficulty: Easy

```swift
func reverseWords(_ s: String) -> String {

    let strArr = s.components(separatedBy: " ").map { $0.reversed() }
    var result = ""
        
    for i in strArr {
        result += i
        result
        += " "
    }
    result.removeLast()
    
    return result
    
}
```

### 1051. Height Checker

Source: <https://leetcode.com/problems/height-checker/>

Difficulty: Easy

```swift
func heightChecker(_ heights: [Int]) -> Int {

    var sorted = heights.sorted(by: <)
    var count = 0
    
    for i in 0..<sorted.count {
        if heights[i] != sorted[i] {
            count += 1
        } else {
            
        }
    }
    
    return count
    
}
```

### 1742. Maximum Number of Balls in a Box

Source: <https://leetcode.com/problems/maximum-number-of-balls-in-a-box/>

Difficulty: Easy

```swift
func digits(value: Int) -> Int {
        
    let charInt = Array(String(value))
        
    return charInt.map { Int(String($0))! }.reduce(0) { $0 + $1 }
        
}
    
func countBalls(_ lowLimit: Int, _ highLimit: Int) -> Int {
        
    var dict = [Int:Int]()
    var result = 0
        
    for i in lowLimit...highLimit {
        dict[digits(value: i), default: 0] += 1
    }
        
    for (key, value) in dict {
        result = max(result, value)
    }
        
    return result
        
}
```

### 1935. Maximum Number of Words You Can Type

Source: <https://leetcode.com/problems/maximum-number-of-words-you-can-type/>

Difficulty: Easy

```swift
func canBeTypedWords(_ text: String, _ brokenLetters: String) -> Int {

    let brkLetters = Array(brokenLetters)
    var wordArr = text.components(separatedBy: " ")
    
    for i in brkLetters {
        for j in 0..<wordArr.count {
            if wordArr[j].contains(i) {
                wordArr[j] = ""
            }
        }
    }
        
    return wordArr.filter { $0 != "" }.count
    
}
```

### 1207. Unique Number of Occurrences

Source: <https://leetcode.com/problems/unique-number-of-occurrences/>

Difficulty: Easy

```swift
func uniqueOccurrences(_ arr: [Int]) -> Bool {

    var dict = [Int:Int]()
    var set = Set<Int>()
    var array = [Int]()
    
    for i in arr {
        dict[i, default: 0] += 1
    }
    
    for (key, value) in dict {
        set.insert(value)
        array.append(value)
    }
    
    return set.count == array.count
    
}
```

### 1880. Check if Word Equals Summation of Two Words

Source: <https://leetcode.com/problems/check-if-word-equals-summation-of-two-words/>

Difficulty: Easy

```swift
func isSumEqual(_ firstWord: String, _ secondWord: String, _ targetWord: String) -> Bool {

    let dict: [Character:String] = ["a":"0", "b":"1", "c":"2", "d":"3", "e": "4",
               "f":"5", "g":"6", "h":"7", "i":"8", "j":"9",
               "k":"10", "l":"11", "m":"12", "n":"13", "o":"14",
               "p":"15", "q":"16", "r":"17", "s":"18", "t":"19",
               "u":"20", "v":"21", "w":"22", "x":"23", "y":"24",
               "z":"25"]
    var first = ""
    var second = ""
    var target = ""
    
    for i in firstWord {
        first += dict[i]!
    }
    
    for i in secondWord {
        second += dict[i]!
    }
    
    for i in targetWord {
        target += dict[i]!
    }
        
    return Int(first)! + Int(second)! == Int(target)
        
}
```

### 344. Reverse String

Source: <https://leetcode.com/problems/reverse-string/>

Difficulty: Easy

```swift
func reverseString(_ s: inout [Character]) {

    var left = 0
    var right = s.count - 1
    
    while left < right {
         s.swapAt(left, right)
        left += 1
        right -= 1
    }
    
}
```

### 1337. The K Weakest Rows in a Matrix

Source: <https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/>

Difficulty: Easy

```swift
func kWeakestRows(_ mat: [[Int]], _ k: Int) -> [Int] {

    var dict = [(Int, Int)]()
    var result = [Int]()
    
    for i in 0..<mat.count {
        dict.append((i, mat[i].reduce(0) { $0 + $1 }))
    }
    
    dict.sort { $0.1 < $1.1 || $0.0 < $1.0 }
    
    for i in 0..<k {
        result.append(dict[i].0)
    }
    
    return result
    
}
```

### 1403. Minimum Subsequence in Non-Increasing Order

Source: <https://leetcode.com/problems/minimum-subsequence-in-non-increasing-order/>

Difficulty: Easy

```swift
func minSubsequence(_ nums: [Int]) -> [Int] {

    var ordered = nums.sorted(by: > )
    var result = [Int]()
        
    if nums.count == 1 {
        result = nums
    } else if nums.isEmpty {
        result = []
    }
        
    for i in 0..<nums.count - 1 {
        let left = ordered[0...i].reduce(0) { $0 + $1 }
        let right = ordered[(i + 1)...(nums.count - 1)].reduce(0) { $0 + $1 }
        if left > right {
            for i in ordered[0...i] {
                result.append(i)
            }
            break
        }
    }
        
    if Set(nums).count == 1 {
        return nums
    }
        
    return result
        
}
```

### 977. Squares of a Sorted Array

Source: <https://leetcode.com/problems/squares-of-a-sorted-array/>

Difficulty: Easy

```swift
func sortedSquares(_ nums: [Int]) -> [Int] {

    var result = [Int]()
        
    for i in nums {
        result.append(i * i)
    }
    
    return result.sorted(by: < )
    
}
```

### 852. Peak Index in a Mountain Array

Source: <https://leetcode.com/problems/peak-index-in-a-mountain-array/>

Difficulty: Easy

```swift
func peakIndexInMountainArray(_ arr: [Int]) -> Int {

    var left = 0
    var right = 1
    
    while right < arr.count {
        if arr[left] <= arr[right] {
            left += 1
            right += 1
        } else {
            break
        }
    }
    
    return right - 1
    
}
```

### 1047. Remove All Adjacent Duplicates In String

Source: <https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/>

Difficulty: Easy

```swift
func removeDuplicates(_ s: String) -> String {

    var stack = [Character]()
        
    for i in s {
        if stack.isEmpty || i != stack.last {
            stack.append(i)
        } else if !stack.isEmpty || i == stack.last {
            stack.removeLast()
        }
    }
        
    return String(stack)
    
}
```

### 1356. Sort Integers by The Number of 1 Bits

Source: <https://leetcode.com/problems/sort-integers-by-the-number-of-1-bits/>

Difficulty: Easy

```swift
func sortByBits(_ arr: [Int]) -> [Int] {

    var dict = [(Int, Int)]()
    var result = [Int]()
    
    for i in arr {
        var temp = i
        var count = 0
        while temp != 0 {
            if temp % 2 == 1 {
                count += 1
            }
            temp = temp / 2
        }
        dict.append((i, count))
    }
    
    dict.sort { $0.0 < $1.0 }
    dict.sort { $0.1 < $1.1 }
     
    for i in dict {
        result.append(i.0)
    }
    
    return result
    
}
```

### 922. Sort Array By Parity II

Source: <https://leetcode.com/problems/sort-array-by-parity-ii/>

Difficulty: Easy

```swift
func sortArrayByParityII(_ nums: [Int]) -> [Int] {
        
    var result = Array(repeating: 0, count: nums.count)
    var odd = [Int]()
    var even = [Int]()
        
    for i in nums {
        if i % 2 == 0 {
            even.append(i)
        } else if i % 2 == 1 {
            odd.append(i)
        }
    }
        
    for i in 0..<odd.count {
        result[i * 2 + 1] = odd[i]
    }
        
    for i in 0..<even.count {
        result[i * 2] = even[i]
    }
        
    return result
        
}
```

### 1441. Build an Array With Stack Operations

Source: <https://leetcode.com/problems/build-an-array-with-stack-operations/>

Difficulty: Easy

```swift
func buildArray(_ target: [Int], _ n: Int) -> [String] {

    var index = 0
    var temp = 1
    var result = [String]()
    
    while index < target.count {
        if target[index] == temp {
            result.append("Push")
            index += 1
        } else {
            result.append("Push")
            result.append("Pop")
        }
        temp += 1
    }
    
    return result

}
```

### 821. Shortest Distance to a Character

Source: <https://leetcode.com/problems/shortest-distance-to-a-character/>

Difficulty: Easy

```swift
func shortestToChar(_ s: String, _ c: Character) -> [Int] {

    var result = Array(repeating:0, count: s.count)
    
    for i in 0..<s.count {
        result[i] = i
    }
        
    var cIndice = [Int]()
    var index = 0
    
    for i in s {
        if i == c {
            cIndice.append(index)
        }
        index += 1
    }
        
    for i in 0..<result.count {
        var temp = s.count
        for j in cIndice {
            temp = min(temp, abs(i - j))
        }
        result[i] = temp
    }
        
    return result
        
}
```

### 1502. Can Make Arithmetic Progression From Sequence

Source: <https://leetcode.com/problems/can-make-arithmetic-progression-from-sequence/>

Difficulty: Easy

```swift
func canMakeArithmeticProgression(_ arr: [Int]) -> Bool {
        
    let sorted = arr.sorted(by: < )
    let val = sorted[1] - sorted[0]
    var left = 0
    var right = 1
        
    while right < sorted.count {
        if sorted[left] + val == sorted[right] {
            left += 1
            right += 1
        } else {
            return false
        }
    }
        
    return right == sorted.count
    
}
```

### 1876. Substrings of Size Three with Distinct Characters

Source: <https://leetcode.com/problems/substrings-of-size-three-with-distinct-characters/>

Difficulty: Easy

```swift
func countGoodSubstrings(_ s: String) -> Int {
        
    let char = Array(s)
        
    var startInd = 0
    var rangeInd = 2
    var str = [String]()
    var count = 0
        
    while rangeInd < s.count {
        let temp = char[startInd...rangeInd]
        str.append(String(temp))
        startInd += 1
        rangeInd += 1
    }
        
    for i in str {
        let temp = Set(Array(i))
        if temp.count == 3 {
            count += 1
        }
    }
        
    return count
        
}
```

### 682. Baseball Game

Source: <https://leetcode.com/problems/baseball-game/>

Difficulty: Easy

```swift
func isInt(_ input: String) -> Bool {

    if let value = Int(input) {
        return true
    }
    
    return false
    
}
    
func isC(_ input: String) -> Bool {

    if input == "C" {
        return true
    } else {
        return false
    }
    
}
    
func isD(_ input: String) -> Bool {

    if input == "D" {
        return true
    } else {
        return false
    }
    
}
    
func isPlus(_ input: String) -> Bool {

    if input == "+" {
        return true
    } else {
        return false
    }
    
}
    
func calPoints(_ ops: [String]) -> Int {

    var stack = [Int]()
        
    for i in ops {
        if isInt(i) {
            stack.append(Int(i)!)
        } else if isC(i) {
            stack.removeLast()
        } else if isD(i) {
            stack.append(stack[stack.count - 1] * 2)
        } else if isPlus(i) {
            stack.append(stack[stack.count - 1] + stack[stack.count - 2])
        } else {
            
        }
    }
    
    return stack.reduce(0) { $0 + $1 }
    
}
```

### 1160. Find Words That Can Be Formed by Characters

Source: <https://leetcode.com/problems/find-words-that-can-be-formed-by-characters/>

Difficulty: Easy

```swift
func countCharacters(_ words: [String], _ chars: String) -> Int {
        
    var count = 0
        
    for i in words {
        var char = Array(chars)
        var temp = ""
        for j in i {
            if char.contains(j) {
                temp.append(char.remove(at: char.firstIndex(of: j)!))
            } else {
                
            }
        }
        if temp.count == i.count {
            count += i.count
        }
    }
        
    return count
        
}
```

### 1636. Sort Array by Increasing Frequency

Source: <https://leetcode.com/problems/sort-array-by-increasing-frequency/>

Difficulty: Easy

```swift
func frequencySort(_ nums: [Int]) -> [Int] {
        
    var dict = [(Int, Int)]()
        
    for i in nums {
        dict.append((i, nums.filter { $0 == i }.count))
    }
        
    var result = [Int]()
        
    dict.sort { $0.0 > $1.0 }
        
    for i in dict.sorted { $0.1 < $1.1 } {
        result.append(i.0)
    }
        
    return result
        
}
```

### 1700. Number of Students Unable to Eat Lunch

Source: <https://leetcode.com/problems/number-of-students-unable-to-eat-lunch/>

Difficulty: Easy

```swift
func countStudents(_ students: [Int], _ sandwiches: [Int]) -> Int {
        
    var queue = students
    var stack = sandwiches
        
    if queue.reduce(0) { $0 + $1 } == stack.reduce(0) { $0 + $1 } {
        return 0
    }
        
    while !(queue.reduce(0) { $0 + $1 } == queue.count && stack.first! == 0) && !(queue.reduce(0) { $0 + $1 } == 0 && stack.first! == 1) {
        if queue.first == stack.first {
            queue.removeFirst()
            stack.removeFirst()
        } else {
            queue.append(queue.removeFirst())
        }
    }
        
    return queue.count
    
}
```

### 136. Single Number

Source: <https://leetcode.com/problems/single-number/>

Difficulty: Easy

```swift
func singleNumber(_ nums: [Int]) -> Int {
        
    var dict = [Int:Int]()
        
    for i in nums {
        dict[i, default: 0] += 1
    }
        
    var result = Int()
        
    for (key, value) in dict {
        if value == 1 {
            result = key
        }
    }
        
    return result
        
}
```

### 1200. Minimum Absolute Difference

Source: <https://leetcode.com/problems/minimum-absolute-difference/>

Difficulty: Easy

```swift
func minimumAbsDifference(_ arr: [Int]) -> [[Int]] {
        
    let sorted = arr.sorted(by: < )
        
    var left = 0
    var right = 1
    var minValue = arr.max()!
    var leftValue = 0
    var rightValue = 1
    var result = [[Int]]()
        
    while right < sorted.count {
        minValue = min(minValue, abs(sorted[right] - sorted[left]))
        left += 1
        right += 1
    }
    
    while rightValue < sorted.count {
        if abs(sorted[rightValue] - sorted[leftValue]) == minValue {
            result.append([sorted[leftValue], sorted[rightValue]])
        }
        leftValue += 1
        rightValue += 1
    }
        
    return result
        
}
```

### 496. Next Greater Element I

Source: <https://leetcode.com/problems/next-greater-element-i/>

Difficulty: Easy

```swift
func nextGreaterElement(_ nums1: [Int], _ nums2: [Int]) -> [Int] {
        
    var result = [Int]()
        
    for i in nums1 {
        let index = nums2.firstIndex(of: i)!
        if nums2[index...].filter { $0 > i }.count != 0 {
            result.append(nums2[index...].filter { $0 > i }[0])
        } else {
            result.append(-1)
        }
    }
    
    return result
    
}
```

### 824. Goat Latin

Source: <https://leetcode.com/problems/goat-latin/>

Difficulty: Easy

```swift
func toGoatLatin(_ sentence: String) -> String {
        
    let compo = sentence.components(separatedBy: " ")
    let condition: [Character] = ["a", "e", "i", "o", "u", "A", "E", "I", "O", "U"]
    var charArr = compo.map { Array($0) }
        
    for i in 0..<charArr.count {
        if condition.contains(charArr[i][0]) {
            charArr[i].append("m")
            charArr[i].append("a")
        } else {
            charArr[i].append(charArr[i].removeFirst())
            charArr[i].append("m")
            charArr[i].append("a")
        }
    }
        
    for i in 0..<charArr.count {
        charArr[i] += Array(repeating: "a", count: i + 1)
    }
        
    var result = ""
        
    for i in charArr {
        result.append(String(i))
        result.append(" ")
    }
        
    result.removeLast()
        
    return result
    
}
```

### 349. Intersection of Two Arrays

Source: <https://leetcode.com/problems/intersection-of-two-arrays/>

Difficulty: Easy

```swift
func intersection(_ nums1: [Int], _ nums2: [Int]) -> [Int] {
        
    var set = Set<Int>()
        
    for i in nums1 {
        if nums2.contains(i) {
            set.insert(i)
        }
    }
        
    return Array(set)
        
}
```

### 500. Keyboard Row

Source: <https://leetcode.com/problems/keyboard-row/>

Difficulty: Easy

```swift
func findWords(_ words: [String]) -> [String] {
        
    let firstRow = Array("qwertyuiopQWERTYUIOP")
    let secondRow = Array("asdfghjklASDFGHJKL")
    let thirdRow = Array("zxcvbnmZXCVBNM")
        
    var result = [String]()
        
    for i in words {
        var firstCount = 0
        var secondCount = 0
        var thirdCount = 0
        for j in i {
            if firstRow.contains(j) {
                firstCount += 1
            } else if secondRow.contains(j) {
                secondCount += 1
            } else if thirdRow.contains(j) {
                thirdCount += 1
            }
        }
        if firstCount == i.count || secondCount == i.count || thirdCount == i.count {
            result.append(i)
        }
    }
        
    return result
        
}
```

### 1399. Count Largest Group

Source: <https://leetcode.com/problems/count-largest-group/>

Difficulty: Easy

```swift
func digitsSum(_ input: Int) -> Int {
        
    let str = String(input)
    var result = 0
        
    for i in str {
        result += Int(String(i))!
    }
        
    return result
        
}
    
func countLargestGroup(_ n: Int) -> Int {
        
    var dict = [Int:Int]()
        
    for i in 1...n {
        dict[digitsSum(i), default: 0] += 1
    }
        
    let result = dict.sorted { $0.1 > $1.1 }
        
    return result.filter { $0.1 == result[0].1 }.count
        
```

### 762. Prime Number of Set Bits in Binary Representation

Source: <https://leetcode.com/problems/prime-number-of-set-bits-in-binary-representation/>

Difficulty: Easy

```swift
func transformBinary(_ input: Int) -> String {

    var temp = input
    var result = ""
    
    while temp != 0 {
        let str = String(temp % 2)
        result.append(str)
        temp = temp / 2
    }
    
    return result
    
}
    
func countOne(_ input: String) -> Int {
    
    var result = 0
    
    for i in input {
        if i == "1" {
            result += 1
        }
    }
    
    return result
    
}
    
func isPrime(_ input: Int) -> Bool {

    var count = 0
    
    for i in 1...input {
        if input % i == 0 {
            count += 1
        }
    }
    
    if count == 2 {
        return true
    } else {
        return false
    }
}
    
func countPrimeSetBits(_ left: Int, _ right: Int) -> Int {

    var count = 0
    
    for i in left...right {
        let binary = transformBinary(i)
        let one = countOne(binary)
        let primeBool = isPrime(one)
        if primeBool == true {
            count += 1
        }
    }
    
    return count
    
}
```

### 476. Number Complement

Source: <https://leetcode.com/problems/number-complement/>

Difficulty: Easy

```swift
func transformBinary(_ input: Int) -> String {

    var temp = input
    var result = ""
    
    while temp != 0 {
        let str = String(temp % 2)
        if str == "0" {
            result.append("1")
        } else if str == "1" {
            result.append("0")
        }
        temp = temp / 2
    }
    
    return result
    
}
    
func po(_ input: Int, _ count: Int) -> Int {
        
    var result = 1
    
    if count == 0 {
        return result
    }
    
    for _ in 1...count {
        result *= 2
    }
    
    return result
        
}
    
func transformInt(_ input: String) -> Int {
    
    var result = 0
    var arr = Array(input)
        
    for i in 0..<input.count {
        result += Int(String(arr[i]))! * po(2, i)
    }
        
    return result
    
}
    
func findComplement(_ num: Int) -> Int {
        
    let binary = transformBinary(num)
        
    return transformInt(binary)
        
}
```

### 412. Fizz Buzz

Source: <https://leetcode.com/problems/fizz-buzz/>

Difficulty: Easy

```swift
func three(_ input: Int) -> Bool {
        
    if input % 3 == 0 && input % 5 != 0 {
        return true
    } else {
        return false
    }
        
}
    
func five(_ input: Int) -> Bool {
        
    if input % 3 != 0 && input % 5 == 0 {
        return true
    } else {
        return false
    }
        
}
    
func threeFive(_ input: Int) -> Bool {
        
    if input % 3 == 0 && input % 5 == 0 {
        return true
    } else {
        return false
    }
        
}
    
func fizzBuzz(_ n: Int) -> [String] {
        
    var result = [String]()
        
    for i in 1...n {
        if three(i) {
            result.append("Fizz")
        } else if five(i) {
            result.append("Buzz")
        } else if threeFive(i) {
            result.append("FizzBuzz")
        } else {
            result.append("\(i)")
        }
    }
        
    return result
        
}
```

### 706. Design HashMap

Source: <https://leetcode.com/problems/design-hashmap/>

Difficulty: Easy

```swift
var myHashMap: [Int:Int]
    
/** Initialize your data structure here. */
init() {
    myHashMap = [:]
}
    
/** value will always be non-negative. */
func put(_ key: Int, _ value: Int) {
    myHashMap[key] = value
}
    
/** Returns the value to which the specified key is mapped, or -1 if this map contains no mapping for the key */
func get(_ key: Int) -> Int {
    return myHashMap.keys.contains(key) ? myHashMap[key]! : -1
}
    
/** Removes the mapping of the specified value key if this map contains a mapping for the key */
func remove(_ key: Int) {
    myHashMap.removeValue(forKey: key)
}
```

### 1408. String Matching in an Array

Source: <https://leetcode.com/problems/string-matching-in-an-array/>

Difficulty: Easy

```swift
func stringMatching(_ words: [String]) -> [String] {

    var set = Set<String>()
    
    for i in 0..<words.count {
        let filter = words.filter { $0 != words[i] }
        for j in filter {
            if j.contains(words[i]) {
                set.insert(words[i])
            }
        }
            
    }
    
    return Array(set)
    
}
```

### 1394. Find Lucky Integer in an Array

Source: <https://leetcode.com/problems/find-lucky-integer-in-an-array/>

Difficulty: Easy

```swift
func findLucky(_ arr: [Int]) -> Int {
        
    var dict = [Int:Int]()
    var result = -1
        
    for i in arr {
        dict[i] = arr.filter { $0 == i }.count
    }
        
    for (key, value) in dict {
        if key == value {
            result = max(result, key)
        }
    }
        
    return result
        
}
```

### 1046. Last Stone Weight

Source: <https://leetcode.com/problems/last-stone-weight/>

Difficulty: Easy

```swift
func lastStoneWeight(_ stones: [Int]) -> Int {
        
    var temp = stones
        
    while temp.count > 1 {
        let maximum = temp.remove(at: temp.firstIndex(of: temp.max()!)!)
        let secondMaximum = temp.remove(at: temp.firstIndex(of: temp.max()!)!)
        temp.append(maximum - secondMaximum)
    }
        
    return temp[0]
        
}
```

### 1945. Sum of Digits of String After Convert

Source: <https://leetcode.com/problems/sum-of-digits-of-string-after-convert/>

Difficulty: Easy

```swift
func sToString(_ input: String) -> String {
        
    let dict: [Character:String] = ["a":"1", "b":"2", "c":"3", "d":"4", "e":"5",
                "f":"6", "g":"7", "h":"8", "i":"9", "j":"10",
                "k":"11", "l":"12", "m":"13", "n":"14", "o":"15",
                "p":"16", "q":"17", "r":"18", "s":"19", "t":"20",
                "u":"21", "v":"22", "w":"23", "x":"24", "y":"25",
                "z":"26"]
        
    var str = ""
        
    for i in input {
        str.append(dict[i]!)
    }
        
    return str
        
}
    
func compress(_ input: String) -> String {

    var intResult = 0
    for i in input {
        intResult += Int(String(i))!
    }
    
    return String(intResult)
    
}
    
func getLucky(_ s: String, _ k: Int) -> Int {
        
    if k == 1 {
        let temp = sToString(s)
        var result = 0
        for i in temp {
            result += Int(String(i))!
        }
        return result
    } else {
        var firstStep = sToString(s)
        for i in 1...k {
            firstStep = compress(firstStep)
        }
        return Int(firstStep)!
    }
        
}
```

### 242. Valid Anagram

Source: <https://leetcode.com/problems/valid-anagram/>

Difficulty: Easy

```swift
func isAnagram(_ s: String, _ t: String) -> Bool {

    return String(s.sorted()) == String(t.sorted())
    
}
```

### 1848. Minimum Distance to the Target Element

Source: <https://leetcode.com/problems/minimum-distance-to-the-target-element/>

Difficulty: Easy

```swift
func getMinDistance(_ nums: [Int], _ target: Int, _ start: Int) -> Int {
        
    var candidate = [Int]()
        
    for i in 0..<nums.count {
        if nums[i] == target {
            candidate.append(abs(i - start))
        }
    }
        
    return candidate.min()!
    
}
```

### 1287. Element Appearing More Than 25% In Sorted Array

Source: <https://leetcode.com/problems/element-appearing-more-than-25-in-sorted-array/>

Difficulty: Easy

```swift
func findSpecialInteger(_ arr: [Int]) -> Int {
        
    var dictCount = [Int:Int]()
        
    for i in arr {
        dictCount[i, default: 0] += 1
    }
        
    let sorted = dictCount.sorted { $0.1 > $1.1 }
        
    return sorted[0].0
        
}
```

### 704. Binary Search

Source: <https://leetcode.com/problems/binary-search/>

Difficulty: Easy

```swift
func search(_ nums: [Int], _ target: Int) -> Int {
        
    var result = -1
        
    for i in 0..<nums.count {
        if nums[i] == target {
            result = i
        }
    }
    
    return result
    
}
```

### 121. Best Time to Buy and Sell Stock

Source: <https://leetcode.com/problems/best-time-to-buy-and-sell-stock/>

Difficulty: Easy

```swift
func maxProfit(_ prices: [Int]) -> Int {

    var a = 0
    var minP = prices.max()!
    
    for i in prices {
        minP = min(minP, i)
        a = max(a, i - minP)
    }
    
    return a
    
}
```

### 225. Implement Stack using Queues

Source: <https://leetcode.com/problems/implement-stack-using-queues/>

Difficulty: Easy

```swift
var stack = [Int]()
    
/** Initialize your data structure here. */
init() {
    stack = []
}
    
/** Push element x onto stack. */
func push(_ x: Int) {
    stack.append(x)
}
    
/** Removes the element on top of the stack and returns that element. */
func pop() -> Int {
    return stack.isEmpty ? -1 : stack.removeLast()
}
    
/** Get the top element. */
func top() -> Int {
    return stack.isEmpty ? -1 : stack.last!
}
    
/** Returns whether the stack is empty. */
func empty() -> Bool {
    return stack.isEmpty
}
```

### 1. Two Sum

Source: <https://leetcode.com/problems/two-sum/>

Difficulty: Easy

```swift
func twoSum(_ nums: [Int], _ target: Int) -> [Int] {

    var result = [Int]()
    
    for i in 0..<nums.count {
        for j in (i+1)..<nums.count {
            if nums[i] + nums[j] == target {
                result = [i, j]
            }
        }
    }
    
    return result
}
```

### 819. Most Common Word

Source: <https://leetcode.com/problems/most-common-word/>

Difficulty: Easy

```swift
func mostCommonWord(_ paragraph: String, _ banned: [String]) -> String {
        
    var separate = paragraph.lowercased().split { !$0.isLetter }
    var arr = [String]()
        
    for i in separate {
        arr.append(String(i))
    }
        
    var setForKey = Set(arr)
    var dict = [(String, Int)]()
    
    for i in setForKey {
        dict.append((i, arr.filter { $0 == i }.count))
    }
    
    for i in banned {
        dict = dict.filter { $0.0 != i }
    }
    
    return dict.sorted { $0.1 > $1.1 }[0].0
        
}
```

### 234. Palindrome Linked List

Source: <https://leetcode.com/problems/palindrome-linked-list/>

Difficulty: Easy

```swift
func isPalindrome(_ head: ListNode?) -> Bool {

    if head == nil {
        return true
    }
        
    var head = head
    var array = [Int]()
        
    while head != nil {
        array.append(head!.val)
        head = head!.next
    }
    
    if array != array.reversed() {
        return false
    }
    
    return true
    
}
```

### 342. Power of Four

Source: <https://leetcode.com/problems/power-of-four/>

Difficulty: Easy

```swift
func isPowerOfFour(_ n: Int) -> Bool  {

    if n <= 0 {
        return false
    }
        
    var num = n
    var rem = 0
    
    while (num > 1) {
        rem = num % 4
        if rem != 0 {
            return false
        }
        num = num/4
    }
    
    return true
    
}
```

### 20. Valid Parentheses

Source: <https://leetcode.com/problems/valid-parentheses/>

Difficulty: Easy

```swift
func isValid(_ s: String) -> Bool {
        
    let dict: [Character:Character] = ["(":")", "{":"}", "[":"]"]
    var stack = [Character]()
        
    for i in s {
        if dict.keys.contains(i) {
            stack.append(i)
        } else if stack.isEmpty || i != dict[stack.removeLast()] {
            return false
        }
    }
        
    return stack.isEmpty
    
}
```

### 125. Valid Palindrome

Source: <https://leetcode.com/problems/valid-palindrome/>

Difficulty: Easy

```swift
func isPalindrome(_ s: String) -> Bool {

    let charArray = s.lowercased().filter { $0.isLetter == true || $0.isNumber == true }
    
    if String(charArray) == String(charArray.reversed()) {
        return true
    } else {
        return false
    }
    
}
```
