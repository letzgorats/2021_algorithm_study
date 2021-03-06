**구현(Implementation)이란 ?**

**: 머릿속에 있는 알고리즘을 소스코드로 바꾸는 과정**으로, 어떤 문제를 풀든 간에 소스코드를 작성하는 과정은 필수이므로 구현 문제 유형은 모든 범위의 코딩 테스트 문제 유형을 포함하는 개념이다.

우리는 알고리즘 문제를 해결할 때, 문제를 읽고 문제 풀이 방법을 고민한다. 이 때, '구현' 유형이란 풀이를 떠올리는 것은 쉽지만 소스코드로 옮기기 어려운 문제를 의미한다. 흔히들, 프로그래밍 언어의 문법에 능숙하고 코드 작성 속도가 빠른 것을 피지컬이 좋다라고 얘기하는데, 구현 문제에서는 이런 피지컬을 요구하기도 한다.

실제 코딩 테스트에서 구현 문제를 만나면 당황할 수 있다. 어떻게 풀지 감은 오는데, 쉽게 코드로 옮겨지지는 않기 때문이다. 프로그래밍 문법을 정확하게 숙지하고, 라이브러리 사용 경험을 늘림으로써 해결할 수 밖에 없다.

대표적으로 구현에 속하는 유형이 '완전 탐색' 과 '시뮬레이션' 유형이다.

**완전 탐색** : 모든 경우의 수를 주저 없이 다 계산하는 해결 방법

**시뮬레이션** : 문제에서 제시한 알고리즘을 한 단계씩 차례대로 직접 수행해야 하는 문제 유형

※ 구현 시 고려해야 할 메모리 제약 사항

1. C/C++에서 변수의 표현 범위

: 전통적으로 정수형을 표현할 때는 int 자료형을 주로 사용하는데, 이 자료형의 크기는 4byte이다. 기본 int 자료형의 표현 범위는 -2147483648 ~ 2147438647 인데, 이 말은 int 자료형으로 처리하면 2147438647 보다 큰 수를 처리할 수 없다는 의미이다. 이럴 때는, 크기가 8bytes인 long long 과 같은 자료형을 사용하는데, 이 또한, 9223372036854775907 보다 큰 수를 처리할 수 없다. 따라서 훨씬 큰 수를 담을 변수를 만들 때는 BigInteger 클래스를 구현하거나 이용한다.

자바의 경우, BigInteger를 표준 라이브러리로 지원하지만, C++의 경우, 표준 라이브러리에 포함되어 있지 않아, 인터넷에서 외부 라이브러리 형태 그대로 가져와 사용한다. ( 하지만, 이건 검색과 외부 라이브러리 사용이 가능한 코딩 테스트 환경일 때만 쓸 수 있으므로, 대체로 long long 보다 더 큰 정수를 처리하는 문제는 잘 출제되지 않는다.)

**2. 파이썬**

: **기본적으로 프로그래머가 직접 자료형을 지정할 필요가 없고, 매우 큰 수의 연산을 지원해준다.** 파이썬에서의 실수형 변수는 다른 언어와 마찬가지로 유효숫자에 따라서 연산 결과가 원하는 값이 나오지 않을 수 있다는 점만 주의하자.

( 딱히, 정수형 변수에 대해서 고민할 필요 없는 언어가 파이썬! )

▶ 파이썬에서의 리스트 크기

: 대체로 코딩 테스트에서 128~512 MB 로 메모리를 제한하는데, 알고리즘 문제 중 때로는 수백만 개 이상의 데이터를 처리해야 하는 문제가 출제되곤 한다.

(ex)  int 자료형 데이터의 개수에 따른 메모리 사용량

-> 데이터의 개수(리스트의 길이)가 1000 일 때, 메모리 사용량 : 약 4KB

-> 데이터의 개수(리스트의 길이)가 1000000 일 때, 메모리 사용량 : 약 4MB

-> 데이터의 개수(리스트의 길이)가 10000000 일 때, 메모리 사용량 : 약 40MB

**파이썬은 다른 언어에 비해 구현의 복잡함은 적은 편이지만, 데이터 처리량이 많을 때는 반드시 메모리 제한을 고려해야 한다**. 리스트를 여러 개 선언하고, 그 중에서 크기가 천만개 이상인 리스트가 있다면 메모리 제한에 걸릴 수도 있다는 뜻이다. ( 물론 이런 경우는 드물다 )

※ 채점 환경

: **파이썬은 C/C++ 에 비해 동작 속도가 느리다**. 일반적인 기업 코딩 테스트 환경에서는 파이썬으로 제출한 코드가 **1초에 2000만번의 연산을 수행한다고 가정**하면, 크게 무리가 없다는 점만 기억하자. 알고리즘 문제를 풀 때, 시간 제한과 데이터의 개수를 먼저 확인하고 이 문제를 어느 정도의 시간복잡고의 알고리즘으로 작성해야 하는지 예측하는 능력을 길러야 한다.

※ 구현 문제에 접근하는 방법

: 문제의 길이가 비교적 긴 편인데 반해, 문법에 익숙하다면 오히려 쉽게 풀 수 있다. 파이썬은 다른 언어에 비해 문자열 처리가 쉽고, 큰 정수 처리도 수월하기 때문에, 상대적으로 구현 문제를 쉽게 해결할 수 있다. 또, 최근 기업에서는 Python3 뿐만 아니라 PyPy3 채점환경도 지원해주기 때문에, 실행 속도에 대한 부담을 약간은 덜 수 있다. API 개발 문제 또한 구현 유형과 상당히 밀접해 있다. 예를 들어 카카오 공채 때, API 개발 문제가 출제된 적이 있는데, 이 때 카카오 문제 풀이 서버와 통신하는 프로그램 모듈을 작성해야 했다. 이는 알고리즘 문제와 별개로 웹 서버나 데이터 분석에 대한 기초 지식도 필요한 셈이다. 이런 기능을 구현해야 할 때, 파이썬은 다른 언어에 비해 강력한 무기가 될 수 있다.

< 문제 풀다가 계속 오류나서 고생했던 점>

    : 어떤 맵이나 지도등을 구현하기 위해, 2차원 리스트를 만들 때, 계속 TypeError: 'list' object is not callable 가 났었다. 

**오류가 났던 원인**    

**위에서 선언한 변수를 함수처럼 사용하려고 할 때 발생.(map이라는 변수를 사용해버렸다.ㅠ)**

![https://i.loli.net/2020/10/16/W92njDoLdI74iKx.png](https://i.loli.net/2020/10/16/W92njDoLdI74iKx.png)

문제가 되는 부분은 **map이라는 변수를 선언**하고,

밑에서 **파이썬이 내장된 map함수를 이용할 때 발생하는 문제**이다.

여기서 ___의 내용은 내가 선언한 변수의 타입이 나오게 된다.

변수를 함수처럼 사용하려고 해서 **is not callable**이 나오게 된 것.

**결론**

함수 명으로 자주 쓰이는 단어나 파이썬의 내장 함수의 이름으로는 변수의 이름을 쓰지 않는 것이 좋다. 위 같은 에러가 나오면 같은 이름의 변수가 선언된 건 아닌지 확인해보자!

지도,맵 2차원 리스트 90도 회전(행렬)

규칙이 있음 (오른쪽으로 90도 회전하는 경우)

1. 회전 후 배열의 X 인덱스 == 회전하기 전 배열의 Y 인덱스
2. 회전 후 배열의 Y 인덱스 == (배열 크기 - 1) - 회전하기 전 배열의 X 인덱스
