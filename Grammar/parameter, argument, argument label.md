



```swift
// MARK: - 매개변수와 전달인자의 이름을 일치시킨 경우.

func greeting(to: String, from: String) { // to, from이 매개변수
    print("\(to)님 안녕하세요 제 이름은 \(from)입니다.") // to, from이 전달인자
}

greeting(to: "Recruiter", from: "Bettor") // Recruiter님 안녕하세요 제 이름은 Bettor입니다.

// MARK: - 전달인자 레이블과 매개변수 명을 일치시킨 경우
func greetingNoLabel(receiver: String, giver: String) { // 전달인자 레이블을 사용하지 않은 경우
    print("\(receiver) <- \(giver)")
}

// 중복 정의로 사용. 함수 호출시 매개변수의 역할을 명확히 하기위해 재정의 가능.
func greetingWithLabel(receiver to: String, giver from: String) { // 전달인자 레이블은 매개변수 이름 앞에 붙는다.(함수 안에 어떤 전달인자 값을 가져오는지 명시하기 위해 사용하는데, 값이 여러개인 경우 전달인자의 순서와 매개변수 순서가 같다면 생략해도 상관이 없다.) 전달인자 레이블을 적어준 경우, receiver와 giver가 전달인자 레이블
    print("\(to) <- \(from)")
}

greetingNoLabel(receiver: "Bettor", giver: "Timcook") // Bettor <- Timcook
greetingWithLabel(receiver: "Bettor", giver: "Elon") // Bettor <- Elon

// MARK: - 함수 오버로딩
func greeting2(to: String, from: String) {
    print("\(to) <- \(from)")
}

func greeting2(receiver to: String, giver from: String) {
    print("\(to) <- \(from)")
}

greeting2(to: "Bettor2", from: "Timmcook2")
greeting2(receiver: "Bettor2", giver: "Timmcook2")
// greeting이라는 이름이 같은 두 함수가 있지만, 전달인자의 이름에 따라 각각 다른 함수로 값을 보내도록한 것(함수 오버로딩)인데, 함수의 호출 부분에서 전달인자 이름을 receiver, giver로 보낼 시 두번 째 함수가 실행됨.

// MARK: - 두 함수 모두 전달인자 레이블을 사용한 경우

func callfriend(someone: String, boy other: String) {
    print("\(someone)는 \(other) 소년을 불렀다.")
}

func callfriend(someone: String, girl other: String) {
    print("\(someone)는 \(other) 소녀를 불렀다.")
}

callfriend(someone: "Bettor", boy: "양치기") // Bettor는 양치기 소년을 불렀다.
callfriend(someone: "Bettor", girl: "히메") // Bettor는 히메 소녀를 불렀다.

```


> 매개변수 : 어떤 이름으로 함수 내부에서 사용할 것인지를 명시하기 위함.
> 전달인자 : 어떤 이름으로 함수에 값을 보내줄 것인지를 위함.
> 전달인자 레이블 : 함수 정의부에 매개변수와 함께 사용하고 생략이 가능
>   와일드 카드 패턴(_)으로 생략 가능
>   함수 밖에서 함수 안으로 어떤 값을 가져왔는지, 이 값을 어떤 이름을 붙여 매개변수로 사용할 것인지를 명시 가능.
>   함수 오버로딩 가능
>
> 매개변수 == 파라미터 == 인자
> 전달인자 == 아규먼트 == 인수

  
