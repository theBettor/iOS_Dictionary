# Closure

> 클로저 : 일정 기능을 하는 코드를 하나의 블록으로 모아놓은 것, 함수는 클로저의 한 형태이다.
<br>

>> 클로저는 함수의 모습이 아닌 하나의 블록의 모습으로 표현할 수 있다. 

- 클로저의 위치를 기준으로 크게 기본 클로저와 후행 클로저 표현이 있다. 또 각 표현 내에서 가독성을 해치지 않는 선에서 표현을 생략하거나 축약할 수 있는 방법이 있다.
- 클로징 : 변수나 상수가 선언된 위치에서 참조를 획득하고 저장할 수 있다.
<br>

- 3가지 형태
    - 이름이 있고 어떤값도 획득하지 않는 전역함수의 형태
    - 이름이 있고 다른 함수 내부의 값을 획득할 수 있는 중첩된 함수의 형태
    - 이름이 없고 주변 문맥에 따라 값을 획득할 수 없는 축양 문법으로 작성된 형태
- 특징
    - 매개변수와 반환 값의 타입을 문맥을 통해 유추할 수 있기 때문에 매개변수와 반환 값의 타입을 생략할 수 있다.
    - 클로저에 단 한 줄의 표현만 들어있다면 암시적으로 이를 반환 값으로 취급합니다.
    - 축약된 전달인자 이름을 사용할 수 있습니다.
    - 후행 클로저 문법을 사용할 수 있습니다.

## 1. 기본 클로저
```swift
func sorted(by areInIncreasingOrder: (Self.Element, Self.Element) throws -> Bool) rethrows -> [Self.Element]
```
> sorted(by)는 내림차순으로 (배열의 타입과 같은 두 개의 매개변수를 가지며 Bool타입을 반환하는) 클로저를 전달인자로 받을 수 있다. 반환하는 Bool 값은 첫 번째 전달인자 값이 새로 생성되는 배열에서 두 번째 전달인자 값보다 먼저 배치되어야 하는지에 대한 결과값이다. true를 반환하면 첫 번째 전달인자가 두 번째 전달인자보다 앞에 온다.

```swift
func backwards(first: String, second: String) -> Bool {
    print("\(first) \(second) 비교중~")
    return first > second
}

let names: [String] = ["Bettor", "Chris", "Elly", "Justin"]
let reversed: [String] = names.sorted(by: backwards)
print(reversed)
```
<br>
전달받는 두 전달인자는 정렬에 참고할 값이고, 반환될 값은 첫 번째 전달인자가 앞으로 배치될지 뒤로 배치될지에 대한 Bool 타입 값이다.
<br>


```swift
Chris Bettor 비교중 // 2와 1 비교중, 1이 더 앞으로
Elly Bettor 비교중 // 1이 된 Bettor와 2인 Elly, 또 Bettor가 앞이라 Elly와 Chris의 결전
Elly Chris 비교중 // 2와 3인 그들이 1과 2가 되어 대결, Chris 승, Elly 패
Justin Bettor 비교중 // 1등 Bettor와 나머지 Justin의 대결, Bettor 1등 확정
Justin Chris 비교중 // 나머지 순위 결정전, 배열에서 Bettor빼고 앞에 있는 Chris와 대결, Chris 승 
Justin Elly 비교중 // 3번 다 이긴 Bettor, 2번 이긴 Chris, 꼴지 대전, Elly 승, Justin 패
["Justin", "Elly", "Chris", "Bettor"] // 이제 sorted(by)해서 reversed 되면 이렇게 되겠지?

```
> 비교 순서가 왜 저렇게 되는지 심각하게 고민하면서 논리를 주석을 적어보았다. 나름 이해했는데 100퍼센트는 아닌듯 좀 더 익숙해져야...
<br>

이거보다 더 간결하게 표현 할 수 있단다!

```swift
{(매개변수들) -> 반환 타입 in
    실행 코드
}
```

함수와 마찬가지로 입출력 매개변수를 사용하고, 매개변수 이름을 지정하면 가변 매개변수로도 사용 가능하다.

```swift
let names: [String] = ["Bettor", "Chris", "Elly", "Justin"]
let reversed: [String] = names.sorted(by: {(first: String, second: String) -> Bool in
    return first > second
})

print(reversed)
```
> sorted(by)안에 위의 backwards 함수를 녹여서 간결해지고 직관적으로 바뀌었다. 이런 장점도 있지만 다른 코드에도 같은 기능을 사용하려면 위처럼 따로 함수로 구현해 두는것도 나쁘지 않겠다!

## 2. 후행 클로저<br>
보다 조금 더 클로저를 읽기 쉽게 바꿀 수 있다. 함수나 메서드의 마지막 전달인자로 위치하는 클로저는 함수나 메서드의 소괄호를 닫은 후 작성해도 된다. 클로저가 조금 길어지거나 가독성이 조금 떨어진다 싶으면 후행 클로저 기능을 사용하면 좋다.

단, 후행 클로저는 맨 마지막 전달인자로 전달되는 클로저에만 해당되므로 전달인자로 클로저 여러개를 전달할때는 맨 마지막 클로저만 후행 클로저로 사용할 수 있다. 또한 sorted(by: )메서드 처럼 단 하나의 클로저만 전달인자로 전달하는 경우에는 소괄호를 생략해줄 수 잇다.

또 매개변수에 클로저가 여러개 있는 경우, 다중 후행 클로저 문법을 사용할 수 있다. 다중 후행 클로저를 사용하는 경우, 중괄호를 열고 닫음으로써 클로저를 표현하며, 첫 번째 클로저의 전달인자 레이블은 생략한다.

```swift
let names: [String] = ["Bettor", "Peter", "Chris" "Tom"]

// 후행 클로저의 사용
let reversed: [String] = names.sorted() { (first: String. second: String) -> Bool in return first > second 
}

// sorted(by: ) 메서드의 소괄호까지 생략 가능
let reversed: [String] = names.sorted { (first: String, second: String) -> Bool in return first > second
}

func doSomething(do: (String) -> Void, onSuccess: (Any) -> Void, onFailure: (Error) -> Void) {
// do something
}

doSomething { (someString: String) in
// do closure
} onSuccess: { (result: Any) in
// succcess closure
} onFailure: { (error: Error) in
// failure closure
}

print(reversed)
```
