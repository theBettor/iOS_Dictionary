# Protocol

생성 일시: 2024년 1월 12일 오후 4:10
그룹: 개발
상위 항목: 알고리즘 (https://www.notion.so/8a50d12a4508410c99135f503a869b58?pvs=21)
상태: 시작 전

어떤 기능에 적합한 특정 메서드, 프로퍼티 및 기타 요구 사항의 청사진(Bluprint)을 의미

클래스, 구조체, 열거형에 의해 채택되며, 프로토콜에 정의된 요구사항의 실제 구현을 제공한다.

프로토콜의 요구 사항을 모두 충족하는 모든 유형(클래스/구조체/열거형)은 해당 프로토콜에 부합하다고 한다.

위는 애플에서 말하는 protocol의 정의인데

 음악 밴드를 예로 들어보면 구성요소인 속성들 vocal, guitar, piano들은 프로퍼티, 이들이 연주를 하는 행위는 메서드라고 할 수 있다.

실제 보컬이 누구고 어떤 곡을 연주할 것인지 지정(구현)하는 것이 아니라, 이런 프로퍼티가 꼭 필요하고 이런 메서드가 꼭 필요하다고 해당 기능에 필요한 요구 사항을 선언해 두는 것을 protocol이라 함.

밴드를 만들고자 할때 미리 정의된 Band라는 프로토콜을 채택해서 만들 경우, 보컬 기타 피아노라는 속성을 필수적으로 필요하며 연주하는 기능도 필수적인 것.

> 프로퍼티를 선언하여 값을 직접 정의하고, 메서드를 직접 구현하는 것이 아닌, 이 프로토콜을 따르려면 이러한 것들이 필요하다라는 약속을 정의(선언)만 해두는 것.
> 

> 1. Protocol을 채택하는 방법
> 

클래스, 구조체, 열거형이 채택하여 사용할 수 있게끔 만들 수 있다.

```swift
protocol Band {
    var drum: String   { get set }
    var vocal: String  { get set }
    var piano: String  { get set }
    var guitar: String { get set }

    func play()
}

struct Aband: Band { // Type 'Aband' does not conform to protocol 'Band', 프로토콜에 있는 프로퍼티와 메서드를 Aband 안에도 정의하지 않아서 에러가 뜬다.
//    var drum:   String = "A"
//    var vocal:  String = "B"
//    var piano:  String = "C"
//    var guitar: String = "D"
//
//    func play() {
//        print("day6 예뻤어 연주 중!")
//    }
}
//Aband().play()

class Bband: Band {
    var drum:   String = "A"
    var vocal:  String = "B"
    var piano:  String = "C"
    var guitar: String = "D"
        
    func play() {
        print("day6 예뻤어 연주 중!")
    }
}
Bband().play() // day6 예뻤어 연주 중!
```

프로토콜은 제공만, 실제 구현은 Bband와 같은 채택한 곳에서 한다.

> 2. Optional이 필요한 경우
> 

```swift
@objc protocol Band {
    var drum: String   { get set }
    var vocal: String  { get set }
    var piano: String  { get set }
    var guitar: String { get set }
    @objc optional var bass: String { get set }

    func play()
}

struct Aband: Band { // Non-class type 'Aband' cannot conform to class protocol 'Band'
    var drum:   String = "A"
    var vocal:  String = "B"
    var piano:  String = "C"
    var guitar: String = "D"
// bass를 선언해주지 않아도 에러가 안나고 있다.(아래 설명에 있음)

    func play() {
        print("day6 예뻤어 연주 중!")
    }
}
```

1. bass는 희귀하다. 채택하는 곳에서 정의를 할지 안할지 모르지만 프로토콜에 선언해두고 싶다면 optional로 선언할 수 있는데, protocol 앞에도 @ojbc를, 해당 변수 앞에도 optional은 물론 @objc를 붙여주자.
2. 1번의 사례와 같이 채택해주는 곳에서 선언하지 않아도 에러가 안 난다.
    1. 그런데도 위의 코드블럭처럼 에러가 나는 이유는 위의 채택하는 대상이 “구조체”이기 때문이다. → Class로 바꿔주면 에러가 안난다!!!
    2. → 디테일한 설명: @objc라는 문법을 붙이는 순간 Objective-C에서도 사용될 수 있다는 뜻인데, Objective-C에서 프로토콜은 오로지 “클래스 전용”에서만 채택할 수 있기 때문이다.
3. 해결 안됨x
    1. 따라서 호환성을 위해 @objc가 붙는 순간 자동으로 클래스 전용일 때 사용하는 AnyObject가 자동으로 채택된다고 보면 된단다(자동으로 안되던데? 일단 붙여줘야한다는 뜻으로 이해해보자.)
    2. Optional인 만큼, 채택하는 곳에서 선언 했을지 안 했을지 여부를 알 수 없기에, 만약 Band라는 프로토콜 타입을 통해 bass에 접근할 경우, 이때 bass는 String? 즉, Optional(String) 타입으로 접근해야한다.
    3. bass가 String?으로 잡히는걸 보니 잘 따라가고 있는 것 같다.
        
        ![스크린샷 2024-01-15 오후 4.44.53.png](Protocol%20d53b8ef76c174efc9af07a74f41ff93b/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2024-01-15_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_4.44.53.png)
        

> 3. 프로토콜에서 프로퍼티 선언하기
> 

```swift
class ABand: Band {
    var piano: String = "bettor"    // piano 프로퍼티를 저장 프로퍼티로 정의
}
 
class BBand: Band {
    var piano: String {             // piano 프로퍼티를 연산 프로퍼티로 정의
        return "bettor"
    }
}
```

#1. 프로토콜을 채택해서 선언된 프로퍼티를 구현할 경우, 저장 프로퍼티로 구현하든, 연산 프로퍼티로 구현하든 상관 없다.

```swift
protocol Band {
    var piano: String { get set }
}
```

#2. 프로토콜에 선언되는 프로퍼티는 항상 var로 선언 되어야 한다

채택하는 곳에서 연산 프로퍼티는 반드시 var로 선언해야한다.(연산 프로퍼티의 경우 let 선언 자체가 불가)

만약 let으로 선언한다한들 구현하는 곳에서 사용할 수가 없다. var가 필수로 요구되는 이유가 아닐까

그럼 프로토콜에 선언을 다 var로 해야되냐? No

저장 프로퍼티의 경우, 타입 뒤에 달려 있는 { get set }에 따라 달려있다. 아래로 내려가보자.

#3. { get set } 속성에 따라 달라지는 let / var 속성

> - { get }
저장 프로퍼티 : let, var 다 가능
연산 프로퍼티 : getter(get-only) / getter & setter 선언 모두 가능
> 

```swift
// 저장 프로퍼티

protocol Band {
    var piano: String { get }
}

class ABand: Band {
    let piano: String = "bettor"          
}
 
class BBand: Band {
    var piano: String = "bettor"          
}
```

위에도 말했듯, 프로토콜에서 프로퍼티 선언은 let, var다 된다고 했다. 다만 연산 프로퍼티는 let을 쓸 수 없기에 프로토콜에서부터 var로 바꾸라고 미리 에러를 주는게 아닌가?! 라고!

```swift
// 연산 프로퍼티

class ABand: Band {
    var random: String = ""
    var piano: String {
        get {
            return "bettor" // getter(get-only)
        }
    }
}
 
class BBand: Band {
    var random: String = ""
    var piano: String {
        get {
            return "bettor" // getter
        }
        set {
            self.random = newValue // setter
        }
    }
}
```

!중요! 여기에는 protocol 코드가 없는데, 이미 위에 있기도하고 중요한 내용이 아니라 없는 것도 있지만, protocol에는 var만 가능하다고 인지하면 되겠다.

> - { get set }
저장 프로퍼티 : var
연산 프로퍼티 : getter, setter
> 

```swift
// 저장 프로퍼티

protocol Band {
    var piano: String { get set }
}

class ABand: Band {
    let piano: String = "bettor"          // error! Type 'ABand' does not conform to protocol 'Band'
}
 
class BBand: Band {
    var piano: String = "bettor"          
}
```

```swift
// 연산 프로퍼티

class ABand: Band {     
    var random: String = ""
    var piano: String {      // error! Type 'ABand' does not conform to protocol 'Band'
        get {
            return "bettor"
        }
    }
}
 
class BBand: Band {
    var random: String = ""
    var piano: String {
        get {
            return "bettor"
        }
        set {
            self.random = newValue
        }
    }
}
```

위의 에러는 getter(get-only)만 제공하기 때문에 에러가 발생했고

그 아래는 getter, setter 같이 있기에 정상적으로 작동한다!

(미완) - 소들이 2번 프로토콜에서 메서드 선언하기 부터
