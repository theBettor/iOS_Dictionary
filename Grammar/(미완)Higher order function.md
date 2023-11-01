# (미완Higher order function(map, filter, reduce)

> 고차함수를 완전히 이해할때까지 친절하게 적어보자.

고차함수는 다른 함수를 전달인자로 받거나 함수실행의 결과를 함수로 반환하는 함수

1. Map(변형) : 코드 간결성, 재사용 용이, 컴파일러 최적화 성능 좋음
```swift
array.map(transform: T throws -> T) //  T타입의 transform을 받아 새로운 T타입의 컨테이너를 생성
```
<br>
  
for-in
```swift
let numArray = [1,3,5,7,9]
var multiArray = [Int]()
for num in numArray {
    multiArray.append(num * 2)
}
print(multiArray)  // [2, 6, 10, 14, 18]
```
<br>

map(매개변수, 반환 타입, 반환 키워드(return)를 생략(축약)한 후행 클로저))
```swift
let numArray = [1,3,5,7,9]
let multiArray = numArray.map { $0 * 2 }
print(multiArray)  // [2, 6, 10, 14, 18]
```
<br>

map
```swift
let numArray = [1,3,5,7,9]
let multiArray = numArray.map({ (number: Int) -> Int in
    return number * 2
})
print(multiArray)  // [2, 6, 10, 14, 18]
```
