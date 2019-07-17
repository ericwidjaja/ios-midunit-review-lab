## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`
```swift
var str = "Hello, there"
print(str.uppercased())

```
2. **Given a String, return a String alternating between uppercase and lowercase letters**

Input: `Hello, there`

Output: `HeLlO, tHeRe`
```swift
for (index, element) in strArray.enumerated () {
    if index % 2 == 0 {
    answer.append(String(element.uppercased()))
    } else {
    answer.append(String(element).lowercased())
    }
}

print(answer.joined())
```

3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

``print(str.replacingOccurrences(of: "e", with: ""))``

## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

```swift

let arr = [1,5,2,4,1,4]
var biggestNum = 0
    for num in arr {
        if num > biggestNum {
        biggestNum = num
        }   
    }

print(biggestNum)

```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`


Output: `1`
```
var smallestNum = Int.max
    for num in arr {
        if num < smallestNum {
        smallestNum = num
        }
    }
    
print(smallestNum)
```

3. **Given an array of type [Int], return its sum**

In put: `[1,5,2,4,1,4]`

Output: `17`
```
var sumArr = 0
for num in arr {
    sumArr += num
    }

print(sumArr)
//or
print(arr.reduce(0, +))
```

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`
Output: `3.6`
```
print(arr.reduce(0, +)/Double(arr.count))

//OR
var sum = 0.0
var numbersTotal = 0.0
for numbers in arr {
    sum += numbers
    numbersTotal += 1.0
}

print(sum)
print(numbersTotal)
print(sum/numbersTotal)
```
5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`
Output: `12`
```
var sum = 0.0

for numbers in array {
    if numbers > 3.0 {
    sum += numbers
    }
}

print(sum)
```

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`
```
var product = 1.0

    for numbers in array {
    product *= numbers
    }

print(product)
```

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`
```
let numbersArray = [3,6,1,9,4,8, 1, 1, 3, 6]
var numArr: [Int] = []

//The problem is that array has repeated numbers. So using index 1 (as the second smallest numbers in an array), the second element, may not actually be the second smallest numbers. How do we fix it?

let setNumbers = Set(numbersArray)

//Set is a 'random', so we need to sort it.
print(setNumbers.sorted()[1])

//OR

for number in numbersArray where numArr.contains(number) == false {
    numArr.append(number)
}

print(numArr.sorted()[1])
```
## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`
```
for word in givenWords {
    if let wordUnwrapped = word { // Looks at "word" (which are nil, "We", "come", nil, "in", "peace" and says, "okay, if word contains an ACTUAL value (ie: NOT nil), save it to the new variable 'wordUnwrapped'
    print(wordUnwrapped)
    sentence.append(wordUnwrapped)
    }
}

print(sentence)
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`
```
let optionalArray: [String?]? = nil
var newStringArray: [String] = []

if let arrayUnwrapped = optionalArray { // If 'optionalArray' is not a nil and is an actual array, let's save it to a new variable called 'arrayUnwrapped' that we just created.

for stuff in arrayUnwrapped { // This is now looking at all the elements in the newly made arrayUnwrapped. The stuff inside arrayUnwrapped can still be nil because it is of the type '[String?]'
    if let stuffUnwrapped = stuff {// Now, if the stuff/elements in the new arrayUnwrapped are NOT nil and actually have values, let's save all of that to another variable called stuffUnwrapped.

        newStringArray.append(stuffUnwrapped) //Now, we have our variable, 'stuffUnwrapped', that we know contains real string and no nils. Let us append these to the empty [String] array and print it.
        }
    }
}

print(newStringArray)
```

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`


## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`


## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`


## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
Input: `[1,2,3,4,5,6], NumberType.odd`
Output: `[1,3,5]`
```
```
let number = [1,2,3,4,5,6]

enum NumberType {

case even
// Even numbers can be found by using the argument, "Number % 2 == 0"
case odd
// Odd numbers can be found by using the argument, "Number % 2 != 0"

func evenOrOdd(arr: [Int]) -> [Int] {
var numArr: [Int] = [] //This array will have the numbers appended to it depending on the case
switch self { //Refers to instance of NumberType. Looks at its own value. In this case, it would be even or odd.
case .even: //Conditions to check for even numbers + append
for numbers in arr {
if numbers % 2 == 0 {
numArr.append(numbers)
}

}

case .odd: //Conditions to check for odd numbers + append
for numbers in arr {
if numbers % 2 != 0 {
numArr.append(numbers)
}
}
}
return numArr //returns the array with the appeneded numbers
}
}
let even = NumberType.even //Instance of NumberType that has the member value, 'even'.
print(even.evenOrOdd(arr: number))
```

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
