# map

> map 의 결과는 Array 형태이기 때문에 다음과 같은 방법으로 정수 → 배열 변환을 할 수 있다.

```swift
import Foundation

var x: Int = 12345
var arr = String(x).map{ Int(String($0))! }

print(arr) //[1, 2, 3, 4, 5]
```
