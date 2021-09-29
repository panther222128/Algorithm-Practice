Source: <https://leetcode.com/problems/minimize-maximum-pair-sum-in-array/>



Difficulty: Medium



\```swift

func minPairSum(_ nums: [Int]) -> Int {



  let halfCount = (nums.count+1)/2

  let num = nums.sorted()

  let firstHalf = num[0..<halfCount].sorted()

  let secondHalf = num[halfCount..<nums.count].sorted(by: >)



  var temp = [Int]()

   

  for i in 0..<halfCount {

​    temp.append(firstHalf[i] + secondHalf[i])

  }

​     

  return temp.max()!

​     

}

\```