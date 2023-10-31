'''swift
import Foundation

let s = "abcdef"
let x = s[s.index(s.startIndex, offsetBy: 3)]	// "d"
// x 의 타입은 String 이 아닌 Character

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
'''swift
