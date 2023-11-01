# How to initialize array in swift

> 배열 초기화하는 여러가지 방법들

```swift
let N = 5
let a = [Int](repeating: 0, count: N)
let b = [Int](0..<N)
let c = [Int](0..<N).map{2*($0)}
let d = [Int](0..<N).filter{$0%2 == 0}

print(a)    //[0, 0, 0, 0, 0]
print(b)    //[0, 1, 2, 3, 4]
print(c)    //[0, 2, 4, 6, 8]
print(d)    //[0, 2, 4]
```
