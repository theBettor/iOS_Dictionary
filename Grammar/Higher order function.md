# Higher order function(map, filter, reduce)

> 고차함수를 완전히 이해할때까지 친절하게 적어보자.

고차함수는 다른 함수를 전달인자로 받거나 함수실행의 결과를 함수로 반환하는 함수

1. Map(변형) : 기존 데이터를 변형하여 새로운 컨테이너를 만드는데, 기존 데이터는 변형되지 않습니다. [코드 간결성, 재사용 용이, 컴파일러 최적화 성능 좋음]
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
<br>

2. Filter(데이터 추출) : 기존 컨테이너에서 내부의 값을 걸러 새로운 컨테이너를 만듭니다.

```swift
array.filter(isIncluded: T throws -> T) // T타입의 isIncluded를 받아 새로운 T형태의 컨테이너를 생성
```
<br>

for - in
```swift
let stringArray = ["제발", "취업", "시켜주세요", "어디든", "열심히", "기한", "지킬게요"]
var threeCountArray = [String]()
for st in stringArray {
    if st.count == 3 {
        threeCountArray.append(st)
    }
}
print(threeCountArray) // ["어디든", "열심히"]
```
<br>

filter(매개변수, 반환 타입, 반환 키워드(return)를 생략한 후행 클로저)
```swift
let stringAttay = ["제발", "취업", "시켜주세요", "어디든", "열심히", "기한", "지킬게요"]
let threeCountArray = stringAttay.filter { $0.count == 3 }
print(threeCountArray) // ["어디든", "열심히"]
```
<br>

filter
```swift
let stringArray = ["제발", "취업", "시켜주세요", "어디든", "열심히", "기한", "지킬게요"]
let threeCountArray = stringArray.filter({ (value: String) -> Bool in
    return value.count == 3
})
print(threeCountArray) // ["어디든", "열심히"]
```
<br>

3. reduce : 기존 컨테이너에서 내부의 값들을 결합하여 새로운 값을 만든다.

for - in
```swift
let numberArray = [1,2,3,4,5,6,7,8,9,10]
var sum = 0
for number in numberArray {
    sum += number
}
print(sum) // 55

```
<br>

reduce(매개변수, 반환 타입, 반환 키워드(return)를 생략한 후행 클로저)
```swift
let numberArray = [1,2,3,4,5,6,7,8,9,10]
let sum = numberArray.reduce(0) { $0 + $1 }
print(sum) // 55
```
<br>

> 전부터 어려웠던 개념... 도대체 $0, $1은 뭐냐?
>> 아래 블럭을 보면 return first + second 하는 것을 볼 수 있다.
>> 1 + 2를해서 sum에 3을 넣고 second에 3이 들어가 6이 되어 마지막에 55가 되는 것 같다. 아직은 더 익숙해져야 하는 것 같다. 

reduce
```swift
let numberArray = [1,2,3,4,5,6,7,8,9,10]
let sum = numberArray.reduce(0, { (first: Int, second: Int) -> Int in
    return first + second
})
print(sum) // 55
```

