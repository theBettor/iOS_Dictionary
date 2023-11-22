1. 컴퓨팅 사고
- 1) 2진법
- 컴퓨터 과학은 문제 해결에 대한 학문
문제 해결은 입력을 전달받아 출력을 만들어내는 과정이다. 그 중간에 있는 과정이 바로 컴퓨터 과학 입니다.

표현 방법은 2진법이다. 
2진법은 전기를 통해 연산하는, 즉 전기를 켜고 끄는 방식으로 작동하는 컴퓨터에게 적합한 방법입니다.
컴퓨터는 2진법에서 하나의 자릿수를 표현하는 단위를 bit라고 합니다.

비트
정보를 저장하고 연산을 수행하기 위해 컴퓨터는 비트(bit)라는 측정 단위를 씁니다. 비트는 이진 숫자라는 뜻을 가진 “binary digit”의 줄임말이며, 0과 1, 두 가지 값만 가질 수 있는 측정 단위입니다. 디지털 데이터를 여러 비트들로 나타냄으로써 두 가지 값만을 가지고도 많은 양의 정보를 저장할 수 있습니다. 또한 컴퓨터는 저장되어 있는 데이터를 수정하기 위해 비트에 수학적 연산을 수행할 수 있습니다.

비트열
하나의 비트는 0과 1, 이 두 가지의 값만 저장할 수 있습니다. 컴퓨터 내부에서 물리적 표현될 때는, 켜고 끌 수 있는 스위치라고 생각할 수 있겠습니다. (켜기=1, 끄기=0)
하지만 비트 한 개는 많은 양의 데이터를 나타내기에 턱없이 부족합니다. 그렇기 때문에 여러 숫자 조합을 컴퓨터에 나타내기 위해 비트열을 사용합니다. 바이트(byte)는 여덟 개의 비트가 모여 만들어진 것입니다. 하나의 바이트에 여덟 개의 비트가 있고, 비트 하나는 0과 1로 표현될 수 있기 때문에 2^8 = 256 개의 서로 다른 바이트가 존재할 수 있습니다.
바이트가 모이면 더 큰 단위가 될 수 있습니다. 킬로바이트는 1,000 바이트, 메가바이트는 1,000 킬로바이트(100만 바이트), 기가바이트는 1,000 메가바이트(10억 바이트)입니다. 테라바이트는 1,000 기가바이트(1조 바이트)이며, 심지어 페타바이트와 엑사바이트와 같은 더 큰 단위도 존재합니다.

￼
￼

트랜지스터는
50으로 예를들면 트랜지스터인 3개의 스위치를 켜고 전기를 저장해서 50을 나타냄

- 2) 정보의 표현

- 문자의 표현
1. 문자를 숫자로 표현할 수 있도록 정해진 표준 : ASCII(128개의 부호)

2. Unicode : 더 많은 비트를 사용하여 더 다양한 다른 문자들도 표현가능, ascii로는 충분하지 않아서..

- 그림, 영상, 음악의 표현
우리가 스크린을 통해 보는 그림을 자세히 살펴 보면 수많은 작은 점들이 빨간색, 초록색, 파란색을 띄고 있다. 이런 작은 점을 픽셀이라고 부른다. 각각의 픽셀은 세 가지 색을 서로 다른 비율로 조합하여 특정한 색을 갖게 된다(빨간색 72, 초록색 72, 파란색 33을 섞게 되면 노란색이 되는 것과 같은 방식).
이 숫자들을 표현하는 방식을 RGB라고 한다.
이런 방법들로 모든것이 0,1로 표현이 가능하다

- 3) 알고리즘
컴퓨팅은 입력을 받아 그 입력을 처리한 후 출력하는 과정이다
알고리즘은 입력에서 받은 자료를 출력형태로 만드는 처리 과정을 뜻한다.
(입력값을 출력값의 형태로 바꾸기 위해 어떤 명령들이 수행되어야 하는지에 대한 규칙들의 순서적 나열이다). 이러한 일련의 순서적 규칙들을 어떻게 나열하는지에 따라 알고리즘의 종류가 달라진다. 같은 출력값이라도 알고리즘에 따라 출력을 하기까지의 시간이 다를 수 있다.

알고리즘을 평가할 때는 정확성도 중요하지만, 효율성도 중요하다 효율성은 작업을 완료하기까지 얼마나 시간과 노력을 덜 들일 수 있는지에 대한 것이다.

- 의사코드
의사코드는 필요한 행동이나 조건을 잘 설정하여 컴퓨터가 수행해야 하는 일을 절차적으로 파악할 수 있게 도와준다.

fuctions, 조건, boolean, loop

* 4, 5 스크래치 부분은 스킵
퀴즈 풀어야함

2. C언어
- 1) C 기초
￼


컴파일러
우리가 직접 작성한 코드는 “소스 코드”라고 불립니다. 이를 2진수로 작성된 “머신 코드”로 변환해야 컴퓨터가 이해할 수 있스빈다. 이런 작업을 컴파일러라는 프로그램이 수행해줍니다.

- 나머지들 스킵(C의 2345챕터)
- 6) 하드웨어의 한계

컴퓨터는 RAM(랜덤 액세스 메모리)이라는 물리적 저장장치를 포함하고 있습니다. 우리가 작성한 프로그램은 구동 중에 RAM에 저장되는데요, RAM은 유한한 크기의 비트만 저장할 수 있기 때문에 때때로 부정확한 결과를 내기도 합니다.(ex. 부동 소수점 부정확성, 정수 오버플로우)

3. 배열
- 1) 컴파일링
프로그램을 실행할때는 아래 네 개의 단계를 거친다.
* 전처리(Precompile)
    * 컴파일의 전체 과정은 네 단계로 나누어볼 수 있다. 그 중 첫 번째 단계는 전처리인데, 전처리기에 의해 수행된다. # 으로 시작되는 C 소스 코드는 전처리기에게 실질적인 컴파일이 이루어지기 전에 무언가를 실행하라고 알려준다.
    * 예를 들어, #include 는 전처리기에게 다른 파일의 내용을 포함시키라고 알려준다. 프로그램의 소스 코드에 #include 와 같은 줄을 포함하면, 전처리기는 새로운 파일을 생성하는데 이 파일은 여전히 C 소스 코드 형태이며 stdio.h 파일의 내용이 #include 부분에 포함된다.
* 컴파일링(Compile)
    * 전처리기가 전처리한 소스 코드를 생성하고 나면 그 다음 단계는 컴파일입니다. 컴파일러라고 불리는 프로그램은 C 코드를 어셈블리어라는 저수준 프로그래밍 언어로 컴파일합니다.
    * 어셈블리는 C보다 연산의 종류가 훨씬 적지만, 여러 연산들이 함께 사용되면 C에서 할 수 있는 모든 것들을 수행할 수 있습니다. C 코드를 어셈블리 코드로 변환 시켜줌으로써 컴파일러는 컴퓨터가 이해할 수 있는 언어와 최대한 가까운 프로그램으로 만들어 줍니다. 컴파일이라는 용어는 소스 코드에서 오브젝트 코드로 변환하는 전체 과정을 통틀어 일컫기도 하지만, 구체적으로 전처리한 소스 코드를 어셈블리 코드로 변환시키는 단계를 말하기도 합니다.
* 어셈블링(Assemble)
    * 소스 코드가 어셈블리 코드로 변환되면, 다음 단계인 어셈블 단계로 어셈블리 코드를 오브젝트 코드로 변환시키는 것입니다. 컴퓨터의 중앙처리장치가 프로그램을 어떻게 수행해야 하는지 알 수 잇는 명령어 형태인 연속된 0과 1들로 바꿔주는 작업이죠. 이 변환작업은 어셈블리라는 프로그램이 수행합니다. 소스 코드에서 오브젝트 코드로 컴파일 되어야 할 파일이 딱 한 개라면, 컴파일 작업은 여기서 끝이 납니다. 그러나 그렇지 않은 경우에는 링크라 불리는 단계가 추가됩니다.
* 링킹(Link)
    * 만약 프로그램이 (math.h나 cs50.h와 같은 라이브러리를 포함해) 여러 개의 파일로 이루어져 있어 하나의 오브젝트 파일로 합쳐져야 한다면 링크라는 컴파일의 마지막 단계가 필요합니다. 링커는 여러 개의 다른 오브젝트 코드 파일을 실행 가능한 하나의 오브젝트 토크 파일로 합쳐줍니다. 예를 들어, 컴파일 하는 동안에 CS50 라이브러리를 링크하면 오브젝트 코드는 GetInt()나 GetString() 같은 함수를 어떻게 실행할 지 알 수 있게 됩니다.

이 네 단계를 거치면 최종적으로 실행 가능한 파일이 완성됩니다.

- 2) 디버깅
우리가 소스코드를 작성하다보면, 때때로 우리 의도와는 다른 오류나 결과를 맞닥뜨리게 됩니다. 이를 “버그”라고 한다.
버그는 코드에 들어있는 오류.
버그로 인해 프로그램의 실행에 실패하거나 프로그래머가 원하는 대로 동작하지 않게 됩니다. 버그를 만들고 싶지 않겠지만 모든 프로그래머들은 버그와 마주하게 되어있습니다. 디버깅은 코드에 있는 버그를 식별하고 고치는 과정입니다. 프로그래머는 디버거라고 불리는 프로그램을 사용하여 디버깅을 한다.

프로그램은 일반적으로 인간보다 훨씬 빠르게 연산을 수행합니다. 그래서 프로그램을 실행시켜보는 것만으로는 무엇이 잘못됐는지 찾아내기 어렵습니다. 디버거는 프로그램을 특정 행에서 멈출 수 있게 해주기 때문에 버그를 찾는데 도움이 됩니다. 프로그래머는 멈춰진 그 지점에서 무슨 일이 일어나는지 볼 수 있습니다. 프로그램이 멈추는 특정 지점을 중지점이라고 합니다. 또한 프로그래머가 프로그램을 한번에 한 행씩 실행할 수 있게 해줍니다. 이로써 프로그래머는 프로그램이 내리는 모든 결정들을 단계별로 따라갈 수 있게 됩니다.

- help50
help50 make 파일이름
- debug50
cs50 ide를 사용하면 debug50이라는 프로그램도 사용할 수 있다.
소스 코드에 직접 브레이크포인트를 지정하고 소스파일을 컴파일한 후에 “debug50 파일명”으로 실행하면, 오른쪽 패널을 통해 변수의 값을 확인하거나 브레이크포인트부터 한 줄씩 코드를 실행해 볼 수 있습니다.

- 3) 코드의 디자인
- check50 : 여러 사람들이 각자 한 부분을 맡아 코드를 작성할때 각자가 수정한 코드가 전체 프로그램의 정확성을 해치지 않는지 쉽게 확인 가능

- style50 : 코드를 작성하는 사람들이 코드를 읽고 이해하는데 영향을 준다.

- 고무 오리 : 무언가 대상이 되는 물체를 앞에 두고, 내가 작성한 코드를 한 줄 한 줄 말로 설명해주는 과정으로 논리적 오류를 찾아낼 수 있다.

- 4) 배열(1)
같은 자료형의 데이터를 메모리상에 연이어서 저장하고 이를 하나의 변수로 관리하기 위해 사용

- 5) 배열(2)
* 전역 변수
* 배열의 동적 선언 및 저장

- 6) 문자열과 배열
우리가 여지껏 사용한 문자열(string) 자료형의 데이터는 사실 문자(char) 자료형의 데이터들의 배열이었습니다.

* 널 종단 문자가 필요한 이유 : string은 배열이 끝난다는걸 알려주어야하고 string으로 선언된 변수의 사이즈를 알 수 없어서 문자열과 다음 문자열을 구별할 수 없기 때문에 필요하다.

- 7) 문자열의 활용 : 스킵
- 8) 명령행 인자 : 스킵

4. 알고리즘
- 1) 검색 알고리즘
배열은 한 자료형의 여러 값들이 메모리상에 모여 있는 구조입니다. 컴퓨터는 이 값들에 접근할 때 배열의 인덱스 하나하나를 접근합니다. 만약 어떤 값이 배열 안에 속해 있는지를 찾아 보기 위해서는 배열이 정렬되어 있는지 여부에 따라 아래와 같은 방법을 사용할 수 있습니다.

* 선형 검색
배열의 인덱스를 처음부터 끝까지 하나씩 증가시키면서 방문하여 그 값이 속하는지를 검사합니다.
* 이진 검색
만약 배열이 정렬되어 있다면, 배열 중간 인데스부터 시작하여 찾고자 하는 값과 비교하며 그보다 작은(작은 값이 저장되어 있는) 인덱스 또는 큰(큰 값이 저장되어 있는) 인덱스로 이동을 반복하면 됩니다.

* 정렬되지 않는 배열의 경우 어디에 원하는 숫자가 있는지 모르기 때문에 하나씩 선형 검색을 통하여 확인해야 합니다. 이진 검색의 경우 정렬 되어 있는 숫자를 탐색할 때 유리한 알고리즘 입니다.

- 2) 알고리즘 표기법
￼
위와 같은 그림을 공식으로 표기한 것이 Big O 표기법이다.
여기서 O는 “on the order of”의 약자로, 쉽게 생각하면 “~만큼의 정도로 커지는” 것이라고 볼 수 있다.
O(n)은 n만큼 커지는 것이므로 n이 늘어날수록 선형적으로 증가하게 됩니다. O(n/2)도 결국 n이 매우 커지면 1/2은 큰 의미가 없어지므로 O(n)이라고 볼 수 있다.
주로 아래 목록과 같은 Big O 표기가 실행 시간을 나타내기 위해 많이 사용된다.
* O(n^2)
* O(n log n)
* O(n) - 선형 검색
* O(log n) - 이진 검색
* O(1)

Big O가 알고리즘 실행 시간의 상한을 나타낸 것이라면, 반대로 Big Ω(빅 오메가)는 알고리즘 실행 시간의 하한을 나타내는 것입니다.
예를들어 선형 검색에서는 n개의 항목이 있을때 최대 n번의 검색을 해야 하므로 상한이 O(n)이 되지만 운이 좋다면 한 번만에 검색을 끝낼수도 있으므로 하한은 Ω(1)이 됩니다.
역시 아래 목록과 같은 Big Ω 표기가 많이 사용됩니다.
* Ω(n^2)
* Ω(n log n)
* Ω(n) - 배열 안에 존재하는 값의 개수 세기
* Ω(log n)
* Ω(1) - 선형 검색, 이진 검색

Q. 실행시간의 상한이 낮은 알고리즘이 더 좋을까, 하한이 낮은 알고리즘이 더 좋을까?
A. 실행 시간의 하한(최선의 경우)은 input에 좌우되고, 상한(최악의 경우)은 알고리즘의 설계에 좌우된다. 따라서 모든 겨웅에 대해 일관되게 알고리즘의 복잡도를 판단하고자 한다면 상한이 낮은 알고리즘이 더 좋다.

- 3) 선형 검색
찾고자 하은 자료를 검색하는데 사용되는 다양한 알고리즘이 있다. 그 중 하나가 선형 검색
원하는 원소가 발견될때까지 처음부터 마지막 자료까지 차례대로 검섹(찾고자 하는 자료를 찾을때까지 모든 자료를 확인한다)

_ 효율성 그리고 비효율성
선형 검색 알고리즘은 정확히지만 아주 효율적이지 못한 방법이다.
리스트의 길이가 n이라고 했을 때, 최악의 경우 리스트의 모든 원소를 확인해야 하므로 n번만큼 실행됩니다.
여기서 최악의 상황은 찾고자 하는 자료가 맨 마지막에 잇거나 리스트 안에 없는 경우를 말한다.
만약 100만개의 원소가 있는 리스트라고 가정해본다면 효율성이 매우 떨어짐을 느낄 수 있다.
반대로 최선의 상황은 처음 시도했을때 찾고자 하는 값이 있는 경우입니다.
평균적으로 선형 검색이 최악의 상황에서 종료되는 것에 가깝다고 가정할 수 있다.
선형 검색은 자료가 정렬되어 있지 않거나 그 어떤 정보도 없어 하나씩 찾아야 하는 경우에 유용하다.
이러한 경우 무작위로 탐색하는 것보다 순서대로 탐색하는 것이 더 효율적이다.
이제 왜 검색 이전에 정렬해줘야 하는지 알 수 있을 것이다. 정렬은 시간이 오래 걸리고 공간을 더 차지한다. 
하지만 이 추가적인 과정을 진행하면 여러번 리스트를 검색해야 하거나 매우 큰 리스트를 검색해야 할 경우 시간을 단축할 수 있다.

- 4) 버블 정렬
정렬되지 않은 리스트를 탐색하는것 보다 정렬한 뒤 탐색하는 것이 더 효율적이다.
정렬 알고리즘 중 하나는 버블 정렬이다.
버블 정렬은 두 개의 인접한 자료 값을 비교하면서 위치를 교환하는 방식으로 정렬하는 방법을 말하며, 앞에 있는 데이터가 뒤에 있는 데이터보다 크면 둘의 자리를 바꿔준다. 단, 한번의 스캔으로 정렬이 안되면 배열 전체가 정렬될 때까지 스캔을 반복해야한다. 
버블 정렬은 단 두개의 요소만 정렬해주는 좁은 범위의 정렬에 집중한다.
이 접근법은 간단하지만 단 하나의 요소를 정렬하기 위해 너무 많이 교환하는 낭비가 발생할 수도 있다.
참고 : https://babbab2.tistory.com/96

￼

Q. 인접 데이터를 비교하고 swap하는 작업은, 하나의 배열에서 몇 번 반복해야 끝나는가?
A. 배열의 요소가 3개일 경우 2번의 작업으로, 4개일 경우엔 3번의 작업으로 비교 및 swap이 가능했다. 결론은 총 (탐색하는 요소의 개수 - 1)만큼 진행하면 끝난다.


￼
Q. 스캔 작업을 몇 번 반복해야 배열 전체가 정렬이 될까?
A. 배열의 요소고 3개일 경우 2번의 스캔으로, 4개일 경우엔 3번의 스캔으로 배열 전체 정렬이 가능했다.

표를 보면 가장 큰 수부터(맨 마지박부터) 하나씩 정렬이 된다는 것을 알 수 있다. 1번 스캔시 가장 마지막 요소는 가장 큰 값으로 정렬, 2번 스캔 시 마지막에서 2번째 요소는 2번째 큰 값으로 정렬되었음을 알 수 있음.

정리하면 스캔작업을 한번 할때마다 큰 값부터 하나씩 정렬될테니 스캔 작업을 최대 (배열 요소의 개수 - 1)만큼 진해앟면 전체 배열이 정렬된다.
(count에서 - 1을 하는 이유는, 만약 10개 요소 중 9개를 큰 값부터 정렬하면 나머지 1개는 가장 작은 값으로 자동으로 0번 index에 들어 있게 되어있을것이여서)

또한 스캔 작업의 실행 횟수에 따라, 스캔 작업시 탐색하는 요소의 수가 줄어든다.(1번째에 마지막 인덱스는 정렬됫으니 마지막껀 다음에 탐색할 필요없고 2번째때에도 맨마지막에서 2번째 인덱스도 동일하게 탐색할 필요없어짐)

func bubbleSort(_ array: inout [Int]) {
    for index1 in 0..<(array.count - 1) {                // 스캔 작업 반복
        var isSwap = false
        for index2 in 0..<((array.count - index1) - 1) { // 스캔 작업(인접 인덱스 비교 및 swap 반복) : (탐색하려는 요소의 갯수) - 1 => 탐색하려는 요소의 갯수는 스캔 횟수에 따라 차감됨(스캔 횟수만큼 정렬되어 있을테니)
            if array[index2] > array[index2 + 1] {
               array.swapAt(index2, (index2 + 1))
                isSwap = true
            }
        }
        if isSwap == false { return }
    }
}
배열중엔 이미 정렬된 배열이 있을 수도 있다.
이런 경우 스캔 작업중에서 크고 작은지의 여부를 먼저 확인하기 때문에 아무런 swap도 일어나지 않을것이다. 
따라서 이땐 작업해주지 않고 끝내버리기 위해 false를 담은 isSwap이라는 변수를 선언해준다.

+ ) 버블 정렬의 시간 복잡도
요소 개수만큼 도는 반복문 안에, 요소 개수(- 상수)만큼 도는 반복문이 돌기 때문에 작성한 버블 정렬 실행 시간의 상한은 O(n^2)이며 하한도 여전히 Ω(n^2)이므로 구현이 쉽고 간단한 장점이 있지만 느린 알고리즘이다!

Q. 버블 정렬이 효율적인 경우는 어떤 경우이며 반대로 어떤 경우에 비효율적일까?
A. 한 배열에서 찾아야 하는 값이 여러 개일 때 이진 탐색을 활용하면 좋은데, 이진 탐색의 경우 정렬되어 있는 배열을 필요로 한다. 즉, 정렬된 배열을 여러 번 필요로 할 때 효율적이다. 하지만, 배열에서 하나의 값을 찾기 위해 이진 탐색을 하게 되면, 이진 탐색을 위해 O(n^2)의 시간 복잡도를 가지는 연산을 필요로 하므로, 비효율적으로 정렬을 수행하게 된다.

참고 : https://babbab2.tistory.com/96
나중에 소들이껄 정독해야겠다 최고의 블로그

- 5) 선택 정렬
배열 안의 자료 중 가장 작은 수(혹은 가장 큰 수)를 찾아 첫 번째 위치(혹은 갖아 마지막 위치)의 수와 교환해주는 방식의 정렬, 교환 횟수를 최소화하는 반면 각 자료를 비교하는 횟수는 증가한다.

Q. 기준 index의 다음 index부터 최소값을 찾기 위해서 몇 번 비교해야할까?
A. 0번째 index가 기준일 경우 배열 요소개 3개인 배열에서는 1~2번째 index중 최소값을 찾았고 4개일 경우에도 1~3번째 index 중 최소값을 찾았다.
결론 : (기준 index + 1 ..< 배열 요소의 수.count)만큼 반복하면 된다.

이제는 최소값을 찾았으니 그 다음으로 작은 값을 놓기 위해 기준 index를 1씩 늘려가며 반복해야되겠다.

Q. 스캔 작업을 몇 번 반복해야 배열 전체가 정렬이 될까?
A. 배열 요소가 3개일 경우 2번의 스캔으로, 4개일 경우에는 3번의 스캔으로 배열 전체 정렬이 가능했다.
위처럼 스캔 잡업을할때마다 작은 값이 하나씩 정렬될테니 스캔 작업을 (배열 요소의 개수 - 1)만큼 반복하면 된다.


func selectionSort(_ array: inout [Int]) {
    for stand in 0..<(array.count - 1) {                // 스캔 작업 반복
        var minIndex = stand
        for index in (stand + 1)..<array.count {        // 스캔 작업 (stand가 0이면 1번 index부터 마지막 Index까지 돌며 최소값을 찾아야 하니까)
            if array[index] < array[minIndex] {
                minIndex = index
            }
        }
        array.swapAt(stand, minIndex)
    }
}
시간 복잡도도 버블 정렬과 동일

Q. 선택 정렬을 좀 더 효율적으로 바꿀 수 있을까?
A. 가능한 최대 숫자 + 1 길이의 bool 형 배열을 선언한 후, 숫자를 하나씩 선형 탐색하면서 숫자의 값을 인덱스로하는 배열을 true로 둡니다. 이 후 모든 배열을 탐색하면서, true인 index만 추출합니다. 이는 O(N)에 가능하지만, 만약 최대 숫자가 매우 크고, 탐색할 숫자가 적다면 공간 복잡도 측면에서 비효율적일 수 있습니다.