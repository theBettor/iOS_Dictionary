All about 
Optional -> Optional Unwrapping -> Guard

Optional

스위프트가 가지는 대표적인 특징으로는 안정성이 있다. 옵셔널은 바로 안정성을 제공하는 기능으로
우리가 String, Int, Double 등 일반적인 타입을 지정할때, 스위프트의 타입들은 모두 nil이 불가하게 되어 있다. nil은 ‘값이 없음’을 뜻하고 0과는 다른 개념이다.
참고 : https://seolhee2750.tistory.com/10

옵셔널은 직역하면 ‘선택적인’이라는 뜻이 되는데, 말 그대로 값이 없을 수도 있고(nil), 있을 수도 있게 해주는 것이 바로 옵셔널이다.
- nil을 저장하기 위해서는 옵셔널 필수!
- 저장 가능한 범위가 다르기에 당연히 옵셔널인 타입과 그냥 타입은 아예 다른 타입이다.(Int! != Int)

Non-Optional Type : 옵셔널이 적용되지 않은 타입, 무조건 값이 존재해야하며 값이 존재하지 않을 경우(선언만 해주고 값을 대입하지 않았거나 등의 상황) 오류가 발생한다.
- Type Annotaion이나 Type Inference를 이용 

// 변수 생성
var a1: Int
var a2: Int = 0 // var [변수명]: [데이터 타입] = [값]

// 상수 생성
let b1: Int
let b2: Int = 0 // let [상수명]: [데이터 타입] = [값]

// Type Inference를 사용하면 데이터 타입의 명시 없이도 생성이 가능하다.
// 변수 생성
var a1 = 0
var a2 = "hello"

// 상수 생성
let b1 = 0
let b2 = "hi"

// 데이터 타입의 지정 없이도 입력도니 값을 증거로 컴파일러가 타입을 추론하여 지정해주는 것이다.
// 주의할 점
// 1. 변수나 상수 선언 시, 꼭 초기값을 지정해주어야한다. 주어진 초기값만 가지고 컴파일러가 추론하여 지정해주는 것이기에 초기값 없이는 annotation 오류가 발생한다.
// 2. 타입 추론으로 변수나 상수를 생성했어도, 타입 캐스팅 없이 다른 타입으로 바꾸어 사용하는 것은 불가하다. 예를들어, 처음 초기값을 Int로 주었다면 그 변수나 상수는 Int로 지정된 것이기에 이후 다른 타입의 값을 저장하는 것은 불가능하다.

정리 : 
Type annotation은 변수나 상수의 생성시 테이터 타입을 지정해주는 것, Type Inference은 지정 안해주는 것. 타입 추론시 꼭 초기값 지정해주기.



Optional Type : 옵셔널을 적용한 자료형
Type Annotation으로 선언한 논 옵셔널 타입에 ?를 추가해준 모양.

이 옵셔널 타입도 Type Inference를 이용할 수 있는데
var test1: Int? = 1
var test2 = test1
test2를 옵셔널로 선언된 test1을 이용하여 초기화하는 모습이다. 이렇게 옵셔널 자료형의 변수 혹은 상수를 이용하면 옵셔널로도 추론하여 지정할 수 있다.

하지만 Type Inference를 사용하여 옵셔널을 지정할때는 주의할 점이 있다.
var test = nil
논 옵셔널 타입 선언할때 하듯 이렇게 해주면 안된다.
이 추론 방법의 경우 컴파일러는 뒤에 오는 값만 보고 그 자료형을 유추해야 하는데 nil은 그야말로 ‘값이 없을’뿐 어떤 자료형인지 알 수 없다.
따라서 이렇게 옵셔널을 지정하려고하면 당연히 에러가 나올 수 밖에 없다.

정리
옵셔널은 type annotation 뒤에 ?를 붙임으로써 일반적인 자료형이 nil 값을 가질 수 있게 해준다.(값이 있을 수도 없을 수도!)
옵셔널 타입과 논 옵셔널 타입은 아예 다른 타입이다!


Optional Unwrapping

옵셔널인 값을 옵셔널이 아닌 값으로 추출.
스위프트는 타입들을 철저히 구분하여 처리하기에 논 옵셔널 타입이 필요할때는 꼭 옵셔널 추출 과정이 필요하다.

wrapping : 옵셔널 -  nil까지 담을 수 있게 해줄게 ~
unwrapping : 옵셔널 추출 - 감싸놓은 옵셔널 값을 다시 꺼내줄게~

- 강제 추출(Forced Unwrapping)
옵셔널의 값을 추출하는 가장 간단한 방법
var num1: Int? = 1
var num2: Int = num1!

print(num1, num2)
// Optional(1) 1
num2의 경우 옵셔널이 아니기 때문에 옵셔널 타입인 num1의 값을 저장할 수 없다.
따라서 num1 뒤에 !를 붙여서 강제 추출하여 값을 할당해주었다.

이렇게 강제 추출의 경우 ! 하나로 쉽게 옵셔널을 추출할 수 있지만, 강제 추출 방식의 사용은 가장 간단하면서 가장 위험한 방법으로 지양하는 것이 좋다.
강제 추출은 안에 값이 있는지, 없는지 확인도 안하고 걍제로 값을 꺼내오는 방법이라 값을 꺼냈을때 안에 실제 값이 존재했다면 다행이지만, 꺼냈는데 값이 없다면(nil 이라면) 바로 런타임 오류가 발생하게 된다. 언제나 런타임 오류의 가능성을 갖고 있기 때문에 로직상 nil 때문에 오류가 발생할 가능성이 100% 없다고 판단될때만 사용해야 한다.(하지만 실제 프로젝트용 프로그래밍 중에는 그럴 일이 드물다.)
안전한 추출 방법으로는 옵셔널 바인딩과 옵셔널 체이닝 이렇게 두 가지 방식이 있다.

- Optional Binding
추출하려는 값이 nil인지 먼저 확인하고 추출하는 방식(보통 if 또는 while 구문 등과 결합하여 사용)
var num: Int? = nil

if var number = num {
    number = 2
    print(number)
}
else {
    print("num is nil")
}

// num is nil
보통 if문에 var를 사용할 수 없지만, 옵셔널 바인딩에서는 if var 혹은 if let을 사용할 수 있다.
위의 if var number = num의 의미는 ‘만약 옵셔널이 아닌 number 변수에 옵셔널인 num 값을 할당 할 수 있으면’ 이라는 뜻
num 값에 현재 nil이 저장되어 있으므로 else에 해당하는 동작을 수행한다.
만약 값이 존재했다면 옵셔널에서 추출한 값을 상수나 변수로 할당하여 옵셔널이 아닌 형태로 사용할 수 있게 해준다.

- Optional Chaining
옵셔널을 반복사용하여 옵셔널이 체인처럼 꼬리에 꼬리를 물고 있는 모양(체인처럼 서로 이어져 있어 중간에 하나라도 값이 존재하지 않으면(nil 이면) 바로 nil을 반환한다.
class Person {
    var name: String
    var info: Info?
    
    init(name: String) {
        self.name = name
    }
}

class Info {
    var phoneNum: Int
    var address: Address?
    
    init(phoneNum: Int) {
        self.phoneNum = phoneNum
    }
}

class Address {
    var city: String
    var street: String?
    
    init(city: String) {
        self.city = city
    }
}

let bettor: Person = Person(name: "bettor")

// 옵셔널 체이닝을 통한 추출
let bettorInfo: String? = bettor.info?.address?.street
// nil, 먼저 bettor의 info가 nil인지 검사하는데, 현재 info 변수에는 아무 값도 저장되지 않았기 때문에 그 뒤를 검사할 필요없이 바로 nil을 반환하는 모습.
위의 코드 맨 마지막 줄에서 프로퍼티를 통해 체인처럼 이어져있는 옵셔널 체이닝을 확인할 수 있다.
옵셔널 체이닝은 보다시피 info부터 차례대로 nil값인지 아닌지를 검사하여 결과를 반환하고 nil이 반환될 수도 있다는 점을 고려해 프로퍼티마다 ?를 붙여주었다.

여기서 새롭게 알게 된 점은 강제 추출과 옵셔널 체이닝의 차이점이다.
강제추출은 nil 값을 반환할 수 없기 때문에 위의 코드를 강제 추출로 진행했따면 분명 오류를 만들었을 것인데,
옵셔널 체이닝은 반환을 옵셔널 값으로 해주기 때문에 nil 값이 저장되어있어도 추출이 가능하다.

// 옵셔널 체이닝으로 값 할당
bettor.info = Info(phoneNum: 010)
bettor.info?.address = Address(city: "미국")
bettor.info?.address?.street = "텍사스"

// 옵셔널 체이닝
let bettorInfo: String? = bettor.info?.address?.street
// "텍사스" 라는데 print로 출력하려니까 출력이 안된다. 어떻게 하지?
값을 다 할당해 주었기에 info부터 차례대로 검사했을때 nil 값이 없었고, street에 저장된 값을 성공적으로 반환했다.


위, 아래 코드의 주석을 비교해보면 특이한 점을 발견할 수 있는데 옵셔널 체이닝은 반대로, 값의 할당도 가능하다는 것이다.
물론 여기서도 추출할때와 마찬가지로, 이어지는 다른 프로퍼티들에 값이 할당되어있지 않다면 옵셔널 체이닝 동작은 중간에 중단된다.

또한 옵셔널 체이닝은 옵셔널 바인딩과 결합할 수 있다.

let bettor: Person = Person(name: "bettor")

// 옵셔널 체이닝으로 값 할당
bettor.info = Info(phoneNum: 010)
bettor.info?.address = Address(city: "미국")
bettor.info?.address?.street = "텍사스"

// 옵셔널 바인딩과 체이닝의 결합
if let information: String = bettor.info?.address?.street { // 바인딩을 통해 bettor.info.address.street의 결과값이 nil이 아님을 확인하는 동시에 information이라는 상수로 받아올 수 있다.
    print(information)
}
else {
    print("Can not find")
}

// "텍사스"

정리 : 
옵셔널 추출에는 강제 추출, 옵셔널 바인딩, 체이닝이 있는데
강제 추출은 nil인지 확인하지 않고 바로 추출하는 것이고
바인딩은 확인하고 추출, 그리고 체이닝은 연속해서 확인하며 추출하는 방식이다.
강제 추출은 오류 발생 가능성이 높으니 바인딩과 체이닝 위주로 연습하자!





guard의 핵심 키워드는 ‘빠른 종료’이다.

if 구문은 “~면 해라!” 라는 의미지만
guard 구문은 “~아니면 끝내라!” 라는 의미기 때문이다.

- guard 구문의 기본형태
// 함수나 메서드, 반복문 등 블록 내부에 선언
guard (Bool 타입 값) else {
    (예외사항 실행문)
    (제어문 전환 명령어)
}
guard는 if와 같이 Bool 타입의 값을 조건으로 받는다는 것을 알 수 있다.
다른 점은 해당 조건 뒤에 바로 else가 붙는다는 점인데, 예외 처리를 위해서는 else 구문을 따로 추가해야하는 if와 달리 guard는 한 구문에서 바로 예외를 다룬다.
조건이 false면 else에 해당되는 코드가 실행되고, 그 코드에는 반드시 해당 코드 블록을 종료하는 제어문 전환 명령어가 포함되어 있어야한다.
(여기서 코드 블록을 종료하는 코드가 필수라는 의미는, guard의 한계를 보여주는 부분이다

guad의 한계, if와의 차이점
// if 구문 활용
for i in 0...3 {
    if i == 1 { print(i) }
    else { continue }
}

// guard 구문 활용
for i in 0...3 {
    guard i == 1 else { continue }
    print(i)
}
0부터 3까지 반복하여 i가 1일때 1을 출력하도록 하는 내용이다. 이처럼 다양한 조건이 존재하지 않고 한 가지의 예외만 처리해주면 되니, 이렇게 예외 사항만을 처리하고 싶을때는 guard가 적절하다.
주목해야할 점 한가지는 else에 해당하는 coutinue 코드로, for 반복문 안에 guard 구문이 있는 곳은 continue를 이용하여 해당 코드 블록 반복의 종료를 선언할 수 있고 또한 else 블록에 제어문 전환 명령어로 return, break, throw 등을 사용할 수 있다.
하지만 함수나 메서드 혹은 반복문 안에 사용하는 것이 아니라면 제어문 전환 명령어를 사용할 수 없기 때문에 guard 명령어 또한 사용할 수 없게 된다.

조금 더 내 식으로 이야기하자면 위의 설명처럼
guard는 한 구문에서 바로 예외처리해야하지만 if 구문은 따로 추가해야하기때문에 예외처리에 유리한 방법인거같다?라는 생각.

guard let 구문을 ~부터~









