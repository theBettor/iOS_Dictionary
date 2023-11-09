Variadic parameter는 0개 ~ 다수의 특정 타입 인수를 받을 수 있는 매개변수라고 할 수 있다.
- Variadic 매개변수는 특정 타입을 명시해서 메서드가 호출될 때 전달되어 사용될 수 있다.
- Variadic 매개변수를 사용하기 위해서는 해당 매개변수의 타입 이름 뒤에 "..."를 붙여주어 사용합니다. ex) Int.../Double...
- 전달 되는 매개변수는 메서드 블럭 내에서 적절한 타입의 배열로서 만들어질 수 있다. 예를들어 가변인자(Variadic parameter)는 Double..., Int... 등의 타입으로서 명시될 수 있으며 이는 메서드 블럭 내에서 각각 [Double], [Int] 상수 배열(constant array)로서 만들어질 수 있다.
- 아래의 예시는 임의의 가변 기이를 가진 배열 리스트 값의 평균 값을 산출하는 산수 목적의 메서드를 사용할 때 Variadic 매개변수를 사용하는 예시가 된다.

```swift
// 임의의 인수로 이루어진 매개변수, Int... 와 같은 방식으로 사용되어진다.

func calculateAverage(_ numbers: Double...) -> Double { // 다수의 Double 타입 인수를 받아 인수들의 평균값을 산출하는 메서드, 해당 매개변수는 [] 일수도, [3, 14]일 수도, [1, 2, 3]이 될 수도 있는데 매개변수의 총합을 구하고 매개변수로 나눈 평균값을 반환하고 있다.
    var total: Double = 0
    for number in numbers {
        total += number
    }
    
    return total / max(1, Double(numbers.count))
    // 단, Variadic 매개변수는 위의 코드에서 볼 수 있듯이, 인자값이 없을 수도 있다. 이 경우, 평균값 연산 시 NaN(Not a Number)가 될 수 있으므로, 값이 없을 경우 1로 나눌 수 있도록 max 메서드를 사용했다.)
}


calculateAverage(1, 2, 3, 4, 5) // 3
calculateAverage() // 0
 
// 하나의 Variadic 매개변수 자체가 다수의 인수가 될 수 있기 때문에, 하나의 메서드에서 Variadic 매개변수는 단 한개만 사용될 수 있다.

import Foundation

func printNumbers(_ numbers: Int...) {
    for number in numbers {
        print(number)
    }
}

printNumbers(0, 1, 2, 3, 4, 5)

// 한 줄 요약 : 함수 파라미터 개수를 정적으로 정하지 않고 가변적으로 넘길 수 있게 해주고 매개변수는 함수 내부에서 array 형태로 쓰이며 함수의 중복성을 줄여주고 함수마다 가변매개 변수는 하나만 가질 수 있다.
```
