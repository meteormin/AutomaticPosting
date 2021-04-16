# AutomaticPosting
> Ver 0.0.2
주식 정보분석 및 블로그 포스팅 자동화
## 개요
주식 정보분석 및 블로그 포스팅 자동화

## 목적
배경:<br>
 코로나로 인한 팬데믹으로 전 세계가 경제적으로 힘든 시기를 보내고 있습니다. 이런 상황 때문인지 최근 주식 투자에 대한 대중의 관심도가 증가하는 추세입니다. 과거에 주식 투자에 관심이 없었던 사람들까지 주식시장에 입문하면서 주식시장이 이전보다 대중화가 되어가고 있습니다.

주 목적:<br> 
 하지만 대부분 주식은 물론 기본적인 시장경제에 대한 전문지식이 부족한 경우가 대부분이며, 시장 분위기나 지인으로부터 얻은 정보로 투자를 시작하는 것이 일반적입니다. 이러한 사람들이 보다 주식 투자에 접근하기 쉽게 기본적인 주식 투자 관련 정보를 시각화된 정보로 한눈에 보기 쉽게 표현하여 접근성이 좋은 블로그 사이트를 통해 제공하고자 하는 것이 주된 목적입니다.

기타 목적:<br>
 의미 있는 데이터를 제공할 수 있다면, 데이터를 활용하여 어느 정도 주가가 상승할 가능성이 있는 기업을 예측하여 수익을 발생시킬 수 있는지 그리고 블로그 사이트에서 광고를 통한 수익 창출이 가능한지 파악해보는 것입니다.
## 계획
### 일정
![image](https://user-images.githubusercontent.com/42951596/113843659-bc1ce700-97ce-11eb-9c2a-5258ec302fb8.png)
### Plan A
1. 주가 정보와 재무 상태 정보를 활용하여, 주가 상승 및 수익을 낼 수 있는 기업을 필터링하고 필요한 정보와 함께 분기 별 순위를 매겨 표로 작성
2. 위 1번 내용을 활용한 그래프 작성
3. 위 1번, 2번을 결과로 하는 글을 포스팅
4. 위 모든 내용을 자동화하여 발생할 수 있는 인적 비용 최소화

### Plan B
1. 주가 정보와 재무 상태 정보를 활용하여, 주가 상승 및 수익을 낼 수 있는 기업을 필터링하고 필요한 정보와 함께 분기 별 순위를 매겨 표로 작성
2. 위 1번을 결과로 하는 글을 포스팅
3. 위 모든 내용을 자동화하여 발생할 수 있는 인적 비용 최소화

## 분석
> 2021.04.07 ver 0.0.1
>> 아래 항목에 따라 순위 매김
- 주식 정보 항목
  - 시가총액
- 재무제표 항목
  - 당기순이익,적자횟수
  - 부채비율  
  - 유동비율
## 설계
### 개발환경
#### 서버
> [server setting](./docs/server-setting.md)
>> [관련 issue]<br>
>> 1. [apache + php](https://github.com/miniyus/AutomaticPosting/issues/1)
>> 2. [windows + kiwoomAPI](https://github.com/miniyus/AutomaticPosting/issues/2)

윈도우즈 서버 2016
- 키움 API연동
우분투 20.04LTS
- Open Dart 및 Tistory블로그 연동
#### 언어
PHP8.0 - Laravel/lumen 8.x)
=> Tistory연동 및 html파일, 데이터분석 로직

python3.8.5 + Anaconda3-python3.8.5
=> OpenDart, 키움 API

JavaScript
=> Chart 라이브러리

MariaDB
=> DBMS
### 시스템 흐름도
![image](https://user-images.githubusercontent.com/42951596/113844114-203fab00-97cf-11eb-91bf-22e587f52415.png)

1. 키움,Dart API를 통해 데이터를 가져온다.
2. 필요한 데이터만 가져와서 정형화(객체화) 한다.
3. 데이터를 가지고 의미있는 데이터표를 생성(순위 매김)
4. 블로그에 포스팅한다.

## 구현
> [issues](https://github.com/miniyus/AutomaticPosting/issues)

### [Lumen](https://github.com/miniyus/AutomaticPosting-lumen/tree/master)

### [kiwoom with Python](https://github.com/miniyus/AutomaticPosting-python/tree/master)

## 테스트
## 결과
