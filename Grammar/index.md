```swift
import Foundation

let a = "abcdef"
let b = a[a.index(a.startIndex, offsetBy: 3)]	// "d" 시작 지점부터 떨어진 정수 값만큼을 더한 위치를 반환
// b의 타입은 String이 아닌 Character

// 배열과 문자열의 인덱스 접근법 비교
let arr = [0, 1, 2, 3, 4]
let str = "abcde"

// 배열은 편하게 인덱스 접근 가능
let arr2 = arr[0..<3]

// 문자열은 편하게 인덱스 접근 불가능. String.Index 형으로 접근해야 함
let i = str.startIndex
let j = str.index(i, offsetBy: 3)
let str2 = str[i..<j]

print(arr2) // [0, 1, 2]
print(str2) // abc
```
