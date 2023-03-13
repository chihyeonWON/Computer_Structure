# Computer_Structure
컴퓨터공학과 컴퓨터구조 정리입니다.

## 이진수 표기법(시험에쓰이는 단위)
```
시간 오름차순 Time Faster

10-3  밀리
10-6  마이크로
10-9  나노  
10-12 피코 

공간 오름차순 capacity,memory Space

10 3  킬로 
10 6  메가
10 9  기가  
10 12 테라
10 15 페타

외우기 밀마나피 KMGTPB
```

## High Level Language & Machine Language
```
High Level Language(사람이 이해하기 쉬운) C, JAVA
Low Level Language(기계가 이해하기 쉬운) Assembly

고급 언어는 있지만 저급 언어라는 단어가 없는 이유?

고급 언어 High Level Language는 High Quality가 아닌 Human Being을 뜻하고
Low Level Language는 Low Quality가 아닌 Machine Language를 뜻하기 때문입니다.
```

## 컴파일러와 어셈블러
```
C언어(High Level Language)로 작성된 프로그램을 swap.c라 하면

프로그램을 컴파일하는 과정(high level -> Machine language) 
cc -c swap.c (컴파일러가 컴파일) -> swap.o 목적프로그램이 생김(Machine) 사람이 이해할 수 없습니다.
이 swap.o 파일을 cc -o swap swap.o -> swap이라는 실행파일이 생깁니다.

프로그램을 어셈블하는 과정(high level -> Assembly language)
cc -S swap.c (어셈블러가 어셈블) -> swap.s (바로 목적프로그램이 생기지 않고 이진 기계어(어셈블리언어로 작성된 프로그램) -> as -o swap.o swap.s -> 목적프로그램 swap.o가 생김 -> cc -c swap swap.o 컴파일하면 최종적으로 실행파일이 생깁니다.

컴파일러와 비교하면 어셈블하는 과정은 어셈블리 프로그램을 작성하는 과정을 거친후에 목적프로그램을 생성하므로 과정이 추가된 것처럼 보입니다.
```

## 성능 
```
성능의 두 가지 관점 : 사용자 관점과 관리자(설계자) 관점

사용자 관점에서 성능은 응답시간(실행시간) 즉 컴퓨터가 작업을 완료하기까지 걸리는 시간을 포함하지만
관리자 관점에서의 성능은 처리량(대역폭) 즉 컴퓨터가 단위 시간당 완료하는 작업의 수가 더 중요합니다.

CPU를 더 빠른 버전으로 바꾸면 응답시간을 단축시켜서 처리량이 좋아진다.
하지만 CPU를 여러 개 설치한다 해서 응답시간이 단축되는 것은 아니고 처리량만이 개선된다.

가령 같은 작업을 하는데 A는 10초가 걸리고 B는 15초가 걸린다고 하고
A가 B보다 얼마나 빠르냐고 묻는다면 이 질문은 얼마나 성능이 좋은 지를 묻는 질문이며

1/10 / 1/15 가되어 1.5배 빠르다고 할 수 있다.(정량적인 답변)
시간은 10/15 초가 빠르다.
```

## 성능의 측정
```
시간은 컴퓨터 성능의 가장 기본적인 척도이다.
컴퓨터 성능의 시간이라 하면 사용자 CPU 시간(user CPU time)와 시스템 CPU 시간(system CPU time)으로 나눌 수 있다.
user cpu time은 cpu가 프로그램 실행에 소요된 시간이라 하면 system cpu time은 운영체제가 이 프로그램을 위한 작업을 하기 위해
소비한 시간으로 볼 수 있다.

가령 예를 들어 a+b를 계산하여 c에 저장하고 이 c를 출력하는 프로그램이 있다고 한다면 사용자 cpu 시간은 이 프로그램이 실행되어
c가 출력되는 데까지 걸리는 시간이라 한다면 시스템 cpu 시간은 c를 입출력 명령어를 해석하기 위해 운영체제에 올려져서 운영체제가 소비한 
시간이 되는 것이다. (운영체제 : cpu -> 운영체제 -> memory 창구와 같은 역할을 함)
```

## 클럭사이클
```
클럭의 시간 간격을 클럭 사이클(Clock cycle)이라고 하며 클럭 사이클, 클럭 주기, 클럭 틱, 틱 이라 한다.
클럭 사이클은 한 클럭 사이클에 걸리는 시간이(250ps)나 클럭 속도(4GHz)로 표시한다.
```

## CPU 성능과 성능 인자
```
CPU 성능에만 관심을 갖기로 했으므로 성능 척도는 CPU 실행시간이다.
프로그램 CPU 실행시간 = 프로그램의 cpu 클럭 사이클 수 * 클럭 사이클 시간 = 프로그램의 cpu 클럭 사이클 수 * 1/클럭 속도
```

