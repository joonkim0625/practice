# 모두의 알고리즘 with 자바스크립트

위 제목의 책을 보고 공부합니다!

---

하노이의 탑 구현해보기. 

하노이의 탑은 일단
  - 한 번에 하나의 원반만 옮길 수 있다.
  - 작은 원반 위에 큰 원반을 놓을 수 없다.


---

## 알고리즘이 만족해야 하는 조건 1: 범용성, 정당성, 결정성 

1. 범용성 
  - 작업자가 누구든(그것이 기계라도) 어떤 환경에서도 같은 결과를 얻을 수 있는 것, 즉 범용성이 있어야 올바른 알고리즘.

2. 정당성 
  - 주어진 과제에 대하여 올바른 결과(=출력)을 얻을 수 있는 것, 즉 정당성도 알고리즘의 중요한 조건.

3. 결정성 
  - 알고리즘은 같은 입력을 했을 때 반드시 같은 결과가 나와야 한다. 


## 알고리즘이 만족해야 하는 조건 2: 유한성과 정지성 

4. 유한성 
  - 알고리즘은 유한해야 한다. 정지하지 않는 알고리즘은 결과를 출력할 수 없는 '즉 문제를 해결할 수 없다는 것'이기 때문이다.

5. 정지성 
  - 알고리즘을 정지 시키려면 정지 판정 알고리즘을 넣어야 하는데, 이렇게 되면 그에 관한 판정을 한 알고리즘이 작동한 뒤에 무조건 정지가 된다. 이러한 이유로 정지 판정 알고리즘은 만들 수가 없다. 

알고리즘의 실행 시간
  - 알고리즘이 유한성을 만족하더라도 실행하는 데 시간이 너무 걸리면 실질적으로 도움이 되지 않을 수 있다.
  - 알고리즘의 실행 시간을 판단하기 위해 '계산량'이라는 지표를 사용하기도 한다.
    - 계산량은 엄밀히 분류하면 시간 계산량과 공간 계산량으로 나눌 수 있다.
    - 알고리즘의 계산량 = 스텝 개수(종료하기까지 몇 개의 스텝이 필요한가?)

시간 계산량과 공간 계산량 
  - 시간 계산량은 얼마만큼의 처리 시간이 필요한지를 뜻한다. 
  - 공간 계산량은 어느 정도의 기억 용량(메모리)가 필요한지를 뜻한다. 

계산량의 기준?
  - 계샨량은 스텝의 개수(명령의 개수)를 기준으로 한다. 
    - 어떤 스텝을 실행하는데 걸리는 시간이 컴퓨터마다 다르더라도, 스텝의 개수는 바뀌지 않기 때문이다.

조합적 확산이란?
  - 처리할 데이터의 조합이 방대해져 스텝의 개수가 너무 많아지는 경우가 있는데, 이를 조합적 확산(combinatorial explosion) 이라고 한다. 
  - 조합적 확산이 발생할 때는 다른 알고리즘을 사용하여 현실적인 시간내에 알고리즘을 해결해야 한다. 

계산량을 표현하는 O 표기법 
  - 알고리즘의 계산량은 일반적으로 O 표기법(오 표기법, 빅오 표기법 등으로 읽는다)으로 표기한다. 이 방법에서는 계산량을 O(n)이나 O(n^2)같은 형식으로 쓴다. 표에서는 위쪽에 있는 O 표기법이 일반적으로 계산량이 적은, 즉 효율적인 알고리즘이다.

    | 기법 | 설명 |
    | ----------- | ----------- |
    | O(n) | 데이터의 개수가 n일 때 스텝의 개수가 데이터의 개수에 비례 |
    | O(log n) | 데이터의 개수가 n일 때 스텝의 개수가 2를 스텝의 개수만큼 제곱한 값의 정수 배라는 뜻 |
    | O(n log n) | 스텝의 개수가 n 로그에 비례한다는 뜻 |
    | O(n^2) | 스텝의 개수가 데이터의 개수의 제곱에 비례한다는 뜻 |
    | O(2^n) | 스텝의 개수가 2의 n 제곱에 비례한다는 뜻 |

위의 내용들을 종합하자면...
  - 알고리즘은 문제를 풀기 위한 절차이다. 
  - 알고리즘은 주어진 입력에서 필요한 출력을 얻는 방법을 간단한 조작이나 절차를 조합해서 명확히 정의한 것이다. 
  - 프로그램은 프로그래밍 언어로 쓰여진 알고리즘의 작업 지시서이며 알고리즘 그 자체가 아니다. 
  - 필요한 결과를 얻기 위해 사용할 수 있는 알고리즘이 하나만 있는 것은 아니다. 
  - 알고리즘은 작업자와 상관없이 어떤 환경에서도 같은 결과를 낼 수 있어야 한다. 
  - 알고리즘은 컴퓨터만의 것이 아니다. 
  - 알고리즘은 **범용성, 정당성, 결정성, 유한성, 정지성**을 갖춰야 한다. 
  - 조합적 확산이 일어나면 실행하는 데 엄청난 시간이 걸린다. 
  - 알고리즘은 정지해야 한다. 


---

## 검색 알고리즘의 체험 

검색은 대표적인 알고리즘 중 하나로써, 우리가 흔히 접하는 검색 사이트에서는 검색 알고리즘을 통해 사용자의 요청을 수행한다. 

### 구글에서 키워드를 검색해보자!

검색에는 여러 가지 테크닉이 존재한다. 예를 들어 'A and B'처럼 키워드 두개를 and로 연결해 검색하면 양쪽 키워드를 포함하는 웹 페이지가 표시된다(and 대신 공백을 넣어도 같은 결과가 나온다). 또 'A or B'처럼 키워드 두 개를 or로 연결하여 검색하면 A와 B 중 하나 이상을 포함하는 웹 페이지가 표시된다.

'A and -B'와 같이 검색을 하면 A는 포함하지만 B는 포함하지 않는다는 뜻이 되고, 키워드를 `""`로 감싸면 이 키워드와 완전히 일치하는 웹 페이지를 검색할 수 있다. 

### 빙에서 검색해보자!

빙에서 똑같은 키워드를 입력해도 결과 건수나 표시 순서가 다르게 나온다. 이것은 빙이 구글과는 다른 검색 알고리즘을 사용하기 때문이다. 같은 출력을 해도 알고리즘에 따라 출력 결과가 다르다는 것을 알 수 있다.

### 알고리즘의 대표 '검색'

검색은 대량의 데이터 중에서 원하는 데이터를 찾는 것이다. 구글 같이 뛰어난 검색 알고리즘을 만들고 소유하고 있어야 방대한 자료들 속에서도 사용자에게 그들이 원하는 정보를 빠른 시간 내에 제공할 수 있다.

### SEO 대책과 알고리즘 

검색 결과가 위쪽에 표시되도록 웹 페이지를 최적화하는 작업을 가리켜 SEO(Search Engine Optimization, 검색 엔진 최적화)라고 한다. 알고리즘은 검색 엔진을 운영하는 기업이 자체적으로 만든다. 기본적으로는 이용자가 입력한 키워드와 최대한 일치하는, 즉 이용자가 원하는 웹 페이지를 상위에 표시해야 한다. 다만, 이용자가 원하는 웹 페이지를 판단하려면 접속 수, 정보량, 링크 수, 업데이트 빈도, 이용자의 거주 지역 등 다양한 측면을 고려해야 한다. 

이러한 이유 때문에 기업들이 검색 결과가 이용자들이 원하는 순서대로 표시되도록 알고리즘을 자주 개선하며 검색에 고려하는 요소를 추가하기도 한다. 알고리즘이 개편되면 표시 순서도 바뀌기 때문에 지금 유효한 대책이 1년 후에도 효과적이라고 할 수는 없다. 

### 처리 속도와 하드웨어의 관계 

검색 시간을 단축하는 데는 검색 알고리즘만 영향을 미치는 것이 아니다. 당연히 하드웨어의 처리 성능도 관련이 있다. 입력받은 데이터를 정해진 알고리즘에 따라 유익한 정보로 변환 및 출력하는 것을 데이터 프로세싱(data processing)이라고 하는데, 컴퓨터가 바로 프로그램으로 구현된 알고리즘에 따라 데이터를 처리하는 '데이터 프로세싱 머신'이다. 

알고리즘의 유한성을 만족하려면 더욱 효율적인 알고리즘을 만들거나(그 알고리즘을 구현한 프로그램의 개발) 하드웨어의 성능을 더 좋게 해야 한다.

### 무어의 법칙 

무어의 법칙은 반도체 소자 브랜드인 인텔 사의 창업자 중 한 명인 고든 무어가 1965년에 발표한 논문에서 반도체의 집적도가 18개월마다 두 배가 된다고 말한 것이다.

무어의 법칙은 반도체 소자인 CPU의 속도와 메모리 용량에도 적용할 수 있는데, CPU의 속도가 이런 식으로 발전하게 되면 옛날의 알고리즘이 적용되어 있는 검색 엔진이라 할지라도 시간이 비약적으로 단축될 수 있다는 것이다.

