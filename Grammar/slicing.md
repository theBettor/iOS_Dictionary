# slicing

슬라이싱

```swift
let a = "abcdef"
let a5 = a[a.startIndex ..< a.index(a.startIndex, offsetBy: 3)] // "abc"

// Swift 의 Index 로 자른 결과는 String 이 아닌 SubString 타입.
var stringList = [String]()
stringList.append(String(a5))    // 타입 변환 필요
```
