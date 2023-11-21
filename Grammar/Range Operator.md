참고 : https://babbab2.tistory.com/165

# 1. 범위 연산자
## 1-1. 닫힌 범위 연산자(Closed Range Operator) 
> 시작과 끝이 정해져 있는 범위 연산자(점 세개를 표시) a…b a이상 b이하
<br>

## 1-2. 반 닫힌 범위 연산자(Half-Open Range Operator) 
> 시작과 끝이 정해져 있는 범위 연산자 a..<b a이상 b미만
> 보통 배열의 마지막 인덱스까지 순회할때, 배열은 인덱스가 0부터이기때문에 배열의 크키 -1 만큼 돌아야하기 때문에 반 닫힌 범위 연산자는 배열을 다룰때 용이하다.
<br>

```swift
let array: [Int] = [1, 2, 3, 4, 5]
 
for index in 2..<array.count {
    print(array[index]) // 3, 4, 5
}
```
<br>

1-3. 단방향 범위(One-Side Ranges)
이전에 배운 두 연산자를 쓸 때 시작과 끝 범위 중 하나만 정해주는 연산자
<br>

```swift
let array: [Int] = [1, 2, 3, 4, 5]
 
for element in array[...3] {
    print(element)                    // 1, 2, 3, 4
}
 
for element in array[3...] {
    print(element)                    // 4, 5
}
 
for element in array[..<3] {
    print(element)                    // 1, 2, 3
}
```

```swift
for i in ...5 {
    print(i)
}
```

> 이처럼 설정할 경우 시작 범위가 없어 어디서부터 범위가 시작되어야할지를 알 수가 없다. 배열의 경우는 무조건 0번이 시작 범위이기 때문
반대로 5… 이라면 시작 범위는 잡혀서 에러 뜨지는 않지만 끝 범위가 정해져 있찌 않아 5~무한대로 잡힌다.
<br>

2. ~= : 범위 안에 값이 속하는지 확인하는 연산자(리턴 값은 Bool이다.)
<br>

```swift
let range = 1..<5
 
range ~= 1      // true
range ~= 5      // false
```

