# For문
 
반복문
 
## 1. 다양한 For문의 사용법

```swift 
for i in 0...5 { // repeat 6 times(range)
    print("코딩 i : \(i)")
}
for i2 in 0..<5 { // "i2" use in general(iterate), repeat 5 times
    print("코딩 i2 : \(i2)")
}
for index in 0..<5 where index % 2 == 0 {
    print("코딩 even number index : \(index)") // 0, 2, 4
} 
``` 

## 2. 짝수인걸 5미만까지 하겠다.
```swift 
//var randomInts : [Int] = [] //1p
var randomInts : [Int] = [Int]() //2p

for _ in 0..<25 { // _ : repeat without var
    let randomNumber = Int.random(in : 0...100) // randomnumber has random number(0to100)
    randomInts.append(randomNumber)
}
print("randomInts : \(randomInts)") //printed 25 random numbers(0to100)
// randomInts : [2, 91, 51, 47, 99, 54, 1, 74, 18, 31, 58, 81, 73, 2, 14, 68, 73, 8, 61, 78, 7, 93, 65, 92, 67]
``` 

randomInts라는 새로운 변수에 배열을 만들고 숫자를 받을 수 있게 그 안에 Int를 넣어주고,
변수없이 25미만까지 시도할건데 randomNumber라는 새로운 상수에 랜덤한하게 Int할 수 있게 해줄건데 0부터 100까지 넣을수 있고, randomInts 배열에 randomNumber를 추가하라하니 이 뜻은 0부터 100까지의 랜덤한 수 중에 25개를 randomInts 배열에 넣어서 배열을 출력하겠다는 뜻이다.



