# GENERIC

생성 일시: 2024년 1월 18일 오전 10:37
그룹: Routine
상위 항목: 알고리즘 (https://www.notion.so/8a50d12a4508410c99135f503a869b58?pvs=21)
상태: 시작 전

GENERIC - 범용 타입

타입에 의존하지 않는 범용 코드를 작성할 때 사용하고, 중복을 피하고 코드를 유연하게 작성할 수 있다.

<aside>
💡 Swift에서 가장 강력한 기능 중 하나로, Swift 표준 라이브러리의 대다수는 제네릭으로 선언되어 있다고 함.

Array와 Dictionary 또한 제네릭 타입!

</aside>

> 1. Generic Function
> 

파라미터로 오는 두 Int 타입의 값을 swap하는 함수를 만들었다.

근데 위 코드처럼 파라미터 모두 Int형일 경우엔 문제 없이 돌아가지만, Swift는 타입에 민감한 언어라 Double, String일 경우엔 사용할 수 없다.

```swift
func swapTwoInts(_ a: inout Int, _ b: inout Int) {
   let tempA = a
   a = b
   b = tempA
}

func swapTwoDoubles(_ a: inout Double, _ b: inout Double) {
   let tempA = a
   a = b
   b = tempA
}

func swapTwoStrings(_ a: inout String, _ b: inout String) {
   let tempA = a
   a = b
   b = tempA
}
```

double과 string도 swap할 수 있는 함수들도 넣어놨다.

해당 형식에 맞게끔 함수를 오버로딩 할 수 있는데 번거롭다..

```swift
func swapTwoValues<T>(_ a: inout T, _ b: inout T) {
   let tempA = a
   a = b
   b = tempA
}
```

이렇게 타입에 제한을 두지 않는 코드를 사용하고 싶을때 제네릭을 쓴다.

<>를 이용해서 안에 타입처럼 사용할 이름(T)를 선언해주면, 그 뒤로 해당 이름(T)을 타입처럼 사용할 수 있다.

여기서 T는 Type Parameter로, T라는 새로운 형식이 생성되는 것이 아니라, 실제 함수가 호출될 때 해당 매개변수의 타입으로 대체되는 placeholder이다.

<aside>
💡 <>로 T를 감싸는 이유는 새로운 형식이 아닌 placeholder이기 때문에, Swift한테는 T는 새로운 타입이 아닌, 존재하지 않는 타입이 아닌 자리 타입이라고 말해주기 위함.

</aside>

```swift
func swapTwoValues<T>(_ a: inout T, _ b: inout T) {
  let tempA = a
  a = b
  b = tempA
}

var someInt = 1
var anotherInt = 2
swapTwoValues(&someInt,  &anotherInt)          // 함수 호출 시 T는 Int 타입으로 결정됨
 
 
var someString = "Hi"
var anotherString = "Bye"
swapTwoValues(&someString, &anotherString)     // 함수 호출 시 T는 String 타입으로 결정됨
```

주석에 적어놓은것 처럼, 제네릭으로 선언해주면 실제 함수를 호출할 때, T의 타입이 결정된다.

```swift
swapTwoValues(&someInt, &aotherString)       // Cannot convert value of type 'String' to expected argument type 'Int'
```

반면 여기서 파라미터 a,b 모두 같은 타입 파라미터인 T로 선언되어 있기 때문에 만약 서로 다른 타입을 파라미터로 전달하면

첫 번째 someInt를 통해 타입 T가 Int로 결정됐기 때문에, 두번째 파라미터인 anotherString의 타입이 Int가 아니라며 에러가 난다.

<aside>
💡 똑같은 내용의 함수를 오버로딩 할 필요 없이 제네릭을 사용하면 코드 중복을 피하고 유연하게 코드를 짤 수 있다.

</aside>

```swift
func swapTwoValues<One, Two> { ... }
```

타입 파라미터는 굳이 T가 아니라 마음대로 정해도 되고, 한개 말고 여러개를 comma(,)를 이용해서 선언할 수 있다. 보통은 가독성을 위해 T나 V 같은 단일 문자, 혹은 Upper Camel Case를 사용한다.

> 2. Generic Type
> 

제네릭을 이용한 함수를 제네릭 함수라고 하는데 구조체, 클래스, 열거형 타입에도 선언할 수 있어 이것을 Generic Type이라고 한다.

```swift
// Stack을 제네릭으로 만든 경우

struct Stack<T> {
    let items: [T] = []
 
    mutating func push(_ item: T) { ... }
    mutating func pop() -> T { ... }
}
```

```swift
// 제네릭 타입의 인스턴스를 생성하는 방법

let stack1: Stack<Int> = .init()
let stack2 = Stack<Int>.init()
// 선언과 마찬가지로 <>를 통해 어떤 타입으로 사용할 것인지를 반드시 명시

let array1: Array<Int> = .init()
let array2 = Array<Int>.init()
```

배열 생성할 때랑 똑같다(타입 추론 X)

Swift에서는 Array가 제네릭 타입이기 때문이다.

> 3. Type Constraints
> 

제네릭 함수와 타입을 사용할 때 특정 클래스의 하위 클래스나, 특정 프로토콜을 준수하는 타입만 받을 수 있게 제약을 둘 수 있다.

3 - 1. 프로토콜 제약

```swift
func isSameValues<T>(_ a: T, _ b: T) -> Bool {
    return a == b               // Binary operator '==' cannot be applied to two 'T' operands
}
 
func isSameValues<T: Equatable>(_ a: T, _ b: T) -> Bool {
    return a == b
}
```

위 두 코드의 큰 차이점은 없지만 자세히 들여다보면,

파라미터로 두 개의 값을 받아서 두 값이 같으면 true, 다르면 false를 반환하는 함수를 제네릭으로 선언했다. 

그냥 될 것 같지만 에러가 난다. == 이라는 연산자는, a와 b의 타입이 Equatable이라는 프로토콜을 준수할 때만 사용할 수 있는데

여기에 선언된 T는 a와 b가 Equatable 프로토콜을 준수하는 타입일 수도, 아닐수도 있는데 아니면 어쩌려고 ==를 쓰냐고 에러를 내는 것이다.

그래서 비슷한 아래 코드처럼 Equatable이라는 제약을 줌으로서 해당함수에 들어올 파라미터는 Equatable이란 프로토콜을 준수하는 파라미터만 들어갈 수 있다.

3 - 2. 클래스 제약

클래스 제약은 프로토콜 제약과 똑같지만, 해당 자리에 프로토콜이 아닌 클래스 이름이 온다.

```swift
class Bird { }
class Human { }
class Teacher: Human { }
 
func printName<T: Human>(_ a: T) { }

let bird = Bird.init()
let human = Human.init()
let teacher = Teacher.init()
 
printName(bird)                  // Global function 'printName' requires that 'Bird' inherit from 'Human'
printName(human)
printName(teacher)
```

천천히 보면 이해할 수 있다. Human 클래스의 서브 클래스가 아닌 bird 인스턴스는 실행할 수 없다.

> 4. 제네릭 확장하기
> 

```swift
extension Array {
    mutating func pop() -> Element {
        return self.removeLast()
    }
}
```

제네릭 타입인 Array를 확장해볼까?

제네릭 타입을  확장하면서 구현부에서 타입 파라미터를 사용할 경우,

실제 Array 구현부에서 타입 파라미터는 Element이기 때문에 위 코드에서도 Element를 사용하는것으로 보인다.

![스크린샷 2024-01-18 오후 3.33.18.png](GENERIC%20f55103b55cd74935bbfc48be17d36a4c/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2024-01-18_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_3.33.18.png)

만약 확장에서 새로운 제네릭을 선언하거나, 다른 타입 파라미터를 사용하면 에러가 뜬다.

```swift
extension Array where Element: FixedWidthInteger {
    mutating func pop() -> Element { return self.removeLast() }
}

let nums = [1, 2, 3]
let strs = ["a", "b", "c"]
 
nums.pop()              // O
strs.pop()              // X
```

where을 통해 확장 또는 제약을 줄 수 있는데 element가 FixedWidthInteger라는 프로토콜을 준수해야 한다고 제약을 주면, FixedWidthInteger를 준수하는 Array<Int>형인 nums는 extension에서 구현된 pop이라는 메서드를 사용할 수 있지만,

준수하지 않는 Array<String>형인 strs는 pop을 사용할 수 없다.

![스크린샷 2024-01-18 오후 3.49.37.png](GENERIC%20f55103b55cd74935bbfc48be17d36a4c/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2024-01-18_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_3.49.37.png)

이런 에러가 뜨긴하는데 나중에 해결해보자.. var로 바꾸라고 권유함..

strs를 어차피 프로토콜을 준수하지 않아 에러가 뜨지만, nums는 print를 앞에 붙이면 정상적으로 출력된다.

> 5. 제네릭 함수와 오버로딩
> 

```swift
func swapValues<T>(_ a: inout T, _ b: inout T) {
    print("generic func")
    let tempA = a
    a = b
    b = tempA
}
 
func swapValues(_ a: inout Int, _ b: inout Int) {
    print("specialized func")
    let tempA = a
    a = b
    b = tempA
}
var a = 1
var b = 2
swapValues(&a, &b)          //"specialized func"
 
 
var c = "Hi"
var d = "Bettor!"
swapValues(&c, &d)          //"generic func"
```

보통은 타입에 관계없이 동일하게 실행되는 제네릭이지만,

만약 특정 타입일 경우, 제네릭 말고 다른 함수로 구현하고 싶다면 제네릭 함수를 오버로딩하면 된다.

위 두 함수를 보면, 타입이 지정된 함수(아래)가 제네릭 함수보다 우선순위가 높기 때문에

Int 타입으로 swapValue를 실행할 경우, 타입이 지정된 함수가 실행되고, String 타입으로 swapValue를 실행할 경우, 제네릭 함수가 실행된다.
