# prefix(), suffix(), dropFirst(), dropLast()

접두사, 접미사

```swift 
let a = "abcdef"
let a1 = a.prefix(3)        // "abc" 접두사
let a2 = a.suffix(3)        // "def" 접미사
let a3 = a.dropFirst(3)        // "def" 주어진 수만큼의 초기 요소를 제외한 모든 요소를 포함하는 SubSequence를 반환
let a4 = a.dropLast(3)        // "abc"

// 범위를 넘어간다면 알아서 조절
let a5 = a.prefix(100)        // "abc"
``` 

이 메서드들은 Array 에도 똑같이 적용된다.
