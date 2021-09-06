# O-Data

- 데이터 분석 개요
- 데이터에 대한 이해
- 머신러닝에 대한 이해
- 사례를 통한 머신러닝 모델링 소개
- 분석 모델링 프로세스에 대한 이해
- 대표적인 머신러닝 알고리즘에 대한 소개 : 회귀분석, 의사결정트리

## 데이터 분석 개요

- 정의: 비즈니스 의사결정에 유용한 정보를 찾기 위한 데이터 정리, 변환, 모델링 과정<br/>
  데이터를 표헌하는 데에 쓰는 식을 찾는 것을 모델링 과정이라 표현 할 수 있음
- 목적: 유용한 정보의 추출, 인사이트 도출, 데이터 분석에 기초한 결정을 내리는 것.

Standard Reports -> Ad Hoc Reports -> Query&Drill-Down -> Dashboard

무엇이 발생? -> 얼마나 많이, 자주, 어디서, 누가? -> 정확하게 무엇이 문제인가? -> 우리가 얻은 성과는?

분석 -> 추세 분석 -> 예측 모델링 -> 처방 모델링

왜 이러한 비즈니스 현상이 발생? -> 추세는 어떻게? -> 앞으로의 일 예측 -> 결과물을 얻기 위해 할 일은?

아래 3단계: IT 시스템 리포팅<br/>
다음 둘: 비즈니스 분석<br/>
나머지: 데이터 사이언스<br/>

데이터가 시간별로 쌓이는걸 시계열 분석<br/>
문제 별로 나누는 걸 분류 분석

### 예시

징가

- 어떻게 하면 유료이용자로 변환?
- 게임 시나리오에 따라 다양한 가상아이템 판매
- 아이템 종류, 유형, 색상... 선호 특성 파악
- 추론통계학 AB테스트(효과차이검정)

파리바게트 수요예측

- 매장별로 얼마만큼의 재료와 반/완제품을 보내줄까? ( 문제)
- 날씨 예보로 수요를 예측해 생산량을 조절함 ( )
- 과거 매출 및 재고량, 날씨정보, 요일, 시간대 간의 관련성을 분석함
- 다차원분석 및 회귀분석

머니볼 스카우트

- 야구를 잘하는 선수와 팀 승리에 기여하는 선수는 다르다는 전제
- 타율/홈런/도루 -> 출루율, 장타율
- 승수/방어율 -> 사사구, 장타허용
- 기술 통계 및 회귀분석

구글 독감 트렌드

- 독감이 지금 어디서 확산되고 있나?
- 과거 검색어 데이터를 바탕으로 상관성을 갖는 검색어를 찾아냄
- 사후약방문식으로 환자가 방문해야 하는 시대에 실시간급 발생상황 파악 가능함
- 텍스트 마이닝, 상관 분석

넷플릭스 영화 추천

- 사람에게 어떤 영화를 추천해줄까?
- A & B 에 공통 분모가 있다면 A가 구매한 상품은 B도 구매할 개연성이 높다.
- 보고 싶은 컨텐츠의 등록 & 이용이력분석
- 데이터마이닝 연관분석

<br/>

---

## 데이터에 대한 이해

- 정형 데이터: 숫자, 글자와 같이 미리 만들어진 형식 또는 틀에 저장되는 데이터 (ex. 스프레드시트, 관계형DB (RDB), CSV)
- 반정형 데이터: 형태가 있으며, 연산이 불가능한 데이터 (ex. XML, HTML, JSON 등)
- 비정형 데이터: 형태가 없으며, 음성, 이미지, 영상 데이터 (ex. 텍스트, 음성, 이미지, 영상 데이터)

- 횡단면 데이터: 특정 시점에 특정 변수에 대해 여러 대상으로부터의 관측치가 측정된 데이터
- 시계열 데이터: 시간의 흐름에 따라 시점 별로 특정 변수에 대한 관측치가 축적된 데이터
- 종단(패널) 데이터: 위에 둘이 모두 포함된 데이터 set. 여러 개체들을 복수의 시간에 걸쳐 변수에 대한 관측치가 쌓인 데이터

횡단면인지 시계열인지에 따라 분석하는 기법이 다르기 때문에, 고려를 좀 해야한다.

- 측정: 속성의 양을 나타내는 방식으로 객체에 숫자를 할당하는 규칙으로 구성됩니다. <br/>
  속성에 숫자를 할당함 -> 할당하는 데에는 규칙이 있음.
- 척도화: 물체와 현상들의 상대성을 반영하는 수치쳬게를 만드는 것 <br/>
  수박의 크기를 5, 참외의 크기를 2라고 하면 '과일의 크기'를 척도화 한 것임. <br/>
  - 목적: 물체나 현상의 속성을 '일관성있는' 체계로 표상해서 그 물체의 현상에 대해서 의사소통이나 비교, 분석 등이 가능하도록 하기 위함.
  - 명목척도, 서열척도, 등간척도, 비율척도로 나눌 수 있음.
    - 명목척도: 그냥 뭔가 물체의 현상의 구분을 위해 수치를 부여하는거, 남자는1, 여자는2 이런식으로...
    - 서열척도: 척도에 뭔가 순서가 있으면 서열척도임. 등간(머 5등이랑 10등이랑 수치적으로 2배 차이가 나지 않음)이 없음.
    - 등간척도: 간격이 동일. 온도가 10도랑 20도가 있다면 정확히 2배의 간격이 차이 난다 할 수 있음. (하지만, 정확히 2배 덥다고 할 순 없음)
    - 비율척도: 배수의 개념을 말할 수 있다면 비율척도. 80kg 는 40kg 보다 정확히 2배 '무겁다' 라고 할 수 있음.
    - 명목척도와 비율척도가 많이 쓰이고, 서열척도와 등간척도는 그다지 많이 쓰이지 않음.

전통적인 통계기반 접근법이 있다.
`모집단`이 있다고 하면 그 안의 `개체/요소(element)`들의 일부를 모아 `표본(Sample)`을 생성하여 `통계량(표본 특성)`을 찾아 내어 분석, 일반화 여부 판단, 전체 모집단의 특성으로 추정하는 순서를 가진다.

ex. 대한민국 전체 소득 수준을 판단하려고 할 때 모집단인 대한민국 국민 전체의 소득 수준을 알 수는 없으니, 일부분만 뽑아내어 데이터를 모아 특성을 분석하고 전체의 특성이라고 추정하는 것이다.

- 추리통계학: 모집단으로부터 추출한 표본의 통계량을 이용하여 모집단의 모수를 추정하거나 모수에 대한 가정을 검정하는데에 사용하는 통계
- 기술통계: 자료를 적절하게 그림, 도표, 수치로 특성을 요약하여 정리하는 통계

기술통계학

- 정성적 자료( 명목 ,서열)
  - 테이블 방식
    - 도수분포표
    - 상대 도수 분포표
    - 백분율 도수분포표
    - 교차표
  - 그래프 방식
    - 막대그래프
    - 꺽은선 그래프
    - 원 그래프
- 정량적 자료 (등간, 비율)
  - 테이블 방식
    - 도수분포표
    - 상대 도수분포표
    - 백분율 도수분포표
    - 교차표
  - 그래프 방식
    - 히스토그램
    - 상자 도표
    - 줄기잎그림

데이터를 모았을 때, 데이터 분석가들이 보고자 하는 것은

데이터가 어디에 위치해 있는지,<br/>
데이터가 얼마나 퍼져 있는지,<br/>
데이터의 분포가 어떤 모양을 하고 있는지<br/>
에 대한 이해를 하려 한다.<br/>

대표값에는 크게 3가지가 있다

- 최빈치(mode): 가장 빈번하게 나타나는 값으로 명목자료에서는 최빈치가 대표값이다.
- 중앙치(median): 자료를 크기 순으로 나열 할때 중앙에 있는거
- 산술평균(mean): 자룔 모두 더해서 자료의 개수로 나눈 값.<br/>
  평균(mean): 가장 단순한 통계 모형. 어쨋든 자료를 요약한 가상의 모형이므로 실제 세계와 얼마나 차이가 있는지 파악할 필요는 있음. 이 차이를 파악하는 방법으로 `편차(deviance) 분석`이 있음.

```
sum( (mean - value)^2 ) / N - 1 = average error
```

데이터가 얼마나 퍼져있는가?

평균은 같은데 raw 데이터는 좀 다르다. 어느 게 낫다고 말할 수 있을까?

```javascript
const a = [20, 80, 60, 100, 40, 90, 50, 70, 30];
const b = [56, 53, 61, 58, 64, 63, 60, 59, 66];

// mean(a) === mean(b)
```

보는 견해에 따라서 다르다.

평균편차는 쓸 수 없다. `sum(mean - value) = 0` <br/>
그래서 편차를 양수로 만들어서 쓴다. 1. 절대값을 씌우거나 2. 제곱을 하거나 (분산)

```
sum( (mean - value)^2 ), sum ( abs(mean - value) )
```

데이터가 어떻게 생겼는가?

아니.. 이건 머 하나도 이해 못했다 ㅋㅋ

- 명목척도: 최빈값
- 서열척도: 중앙값
- 등간척도: 산술평균
- 비율척도: 기하평균, 조화평균

---

## 머신러닝에 대한 이해

정의: 문제를 해결하기 위한 방법(Algorithm)들을 Computer Language를 통해 기계를 학습시키는 것.<br/>
목적: 실제 데이터를 바탕으로 모델을 생성하여, 다른 입력 값을 넣었을 때 발생할 output을 예측하는 것.

```javascript
function example1(x) {
  // (...)
  return y;
}

function add_10(x) {
  return x + 10;
}

function example2(x) {
  // ...??
  // result = x + 10?
  // result = x * 1.5?
  // result = x*2 - 10?
  // 어떤 거일까?
  return result;
}
console.log(example2(20)); // 30
// 30 일때, example2 에서 무슨 계산을 했을까에 대한 것을 잘 반영하는 과정이 머신러닝.
```

입력과 결과가 이미 데이터로 존재하고 데이터 상의 입력과 결과의 관계를 가장 잘 반영(입력에 대한 결과의 오차가 가장 적게)하는 함수를 찾는 과정이 머신러닝이라고 할 수 있다.

예시 -<br/>
특정 단어가 들어가면 스팸 메일로 규정하는데 <br/>
프로그램이 론칭된 후 새로운 스팸 단어가 생겼을 때 업데이트 하지 않는 이상 컴퓨터는 모름<br/>
개발자가 새로운 규칙을 업데이트해야 하는데, 매번 하는건 유지보수가 너무 어려움<br/>

해결하기 위해서 사용자가 스팸으로 지정한 메일에 자주 등장하는 단어를 컴퓨터가 스스로 찾아내서 이 단어가 포함된 메일을 스팸으로 분류하도록 하게 하는 것이다.

머신러닝을 사용하는 이유: 자동으로 변화에 적응하도록!<br/>

전통 프로그래밍 / 머신러닝 / 딥러닝의 과정 차이<br/>
전통: 데이터 수집 -> 피처 엔지니어링 -> 로직 설계 -> 검증<br/>
머신러닝; 데이터 수집 -> 피처 엔지니어링 -> 모델 학습 -> 모델 검증<br/>
딥러닝: 데이터 수집 -> 피처 엔지니어링 -> 모델 학습 -> 모델 검증

머신러닝과 딥러닝의 모델 학습/모델 검증의 과정을 사람이 하지 않고 기계가 하게 된다.<br/>
머신러닝은 정형 데이터를 바탕으로, 딥러닝은 비정형 데이터를 바탕으로 학습한다.

머신 러닝에서 Learning의 의미

- 지도 학습: ex. 검은 돌과 흰 돌을 구분하는 방법을 알려주고 기계가 구분하도록 하는 것.
  - 구분지어야 할 문제를 다루어야 할 때 혹은 연속형 값을 통해 무언가를 해야 할 때 적용할 수 있는 학습법.
- 비지도 학습: 구분 방법을 알려주지 않고도 기계가 구분하도록 하는 것.
  - 산포도를 주고 기계 스스로 산포도를 가장 잘 표현하는 선분을 찾아가도록 하는 학습법.
- 준지도 학습: 일부분만 알려주어서 기계가 패턴을 파악하여 구분 하도록 하는 것.
- 강화 학습: 룰을 지정하여 약간의 패턴을 알려준 후 기계에 trials를 실행시켜 결과에 따라 보상을 주는 것. trials가 쌓이고 그에 따른 결과 보상에 대한 데이터가 쌓일 수록 성공률이 올라가게 됨.

## 사례를 통한 머신러닝 모델링 소개

## 분석 모델링 프로세스에 대한 이해

## 대표적인 머신러닝 알고리즘에 대한 소개 : 회귀분석, 의사결정 트리
