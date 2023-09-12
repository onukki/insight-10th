23년 하반기 9, 10기 활동 레포입니다.

## 목표
- git 툴에 익숙해집니다.
- pandas를 자유롭게 다룰 수 있습니다.
- 통계 기법에 대해 배우고, 적용합니다
- 기본적인 ml 툴을 다루며, 적용할 수 있습니다.

## 진행 기간 및 내용
| 회차 | 세션일자 - 과제 마감일 | 내용 |
| --- | --- | --- |
| 1 | 9/11 - 9/13 | github, Pandas |
| 2 | 9/14 - 9/17 | 읽기, 전처리 |
| 3 | 9/18 - 9/20 | EDA, 시각화 |
| 4 | 9/21 - 9/24 | 통계 |
| 5 | 9/25 - 9/27 | 회귀 이론, 실습 |
| 6 | 10/2 - 10/4 | 회귀 심화, 실습 |

## 진행 방식
- 매 회차별로 "사전 학습", "과제" 두 가지의 과제가 있습니다.
- 사전 학습의 마감일은 해당 세션의 진행일 전날입니다.
- 과제 마감일은 다음 세션의 진행일 전날입니다.

>예시
9/11일 1회차 Pandas 세션일 기준, 9/13일 자정까지 제출해야 하는 과제는 
**"1회차 과제"** 와 **"2회차 사전 학습"** 두 가지 입니다.

## 진행 방식 상세
- 해당 insight 레포를 본인의 레포로 fork합니다.
- fork 한 본인의 레포에서 본인의 컴퓨터로 clone합니다.
- 과제를 진행합니다.
- 본인의 레포로 push합니다.
- 과제 마감일 전까지 insight 레포로 pr을 보내주세요.


## 폴더 구조
```
README.md
homework
    ㄴ session2              // 매 세션 과제 페이지
        ㄴ example.ipynb     // 과제 파일
    ...
code
    ㄴ dhshin98             // 본인 git 아이디
        ㄴ session1
            ㄴ example.ipynb // 과제 제출 파일
            ㄴ README.md     // 세션 전 사전 학습 내용 공부 정리 파일
        ㄴ session2
            ㄴ example.ipynb // 과제 제출 파일
            ㄴ README.md     // 세션 전 사전 학습 내용 공부 정리 파일
        ...
```

## 제출 양식
**`pull request`** 를 보낼 때 아래의 양식을 지켜서 보내주세요!
```
pr 제목 : [session2] 제출자 과제 제출합니다.

내용 : 해당 과제를 하면서 어려웠던 점이나 새로 알게 된 점 간단히 정리
```

ex)
```
[session2] 신동현 과제 제출합니다.

titanic data를 선택하여 과제를 진행했습니다.
pandas 문법은 아직은 익숙하지 않은 것 같습니다.
하지만 기본적으로 python 문법과 비슷한 점이 많은 것 같아서 어느 정도 빠르게 배울 수 있었던 것 같습니다.

merge, concate 하는 부분이 아직 미숙한 것 같습니다.
앞으로 loc, iloc를 많이 쓸 것 같은데 많이 연습하겠습니다!

질문
titanic에서 3번째 과제를 다음과 같이 했는데, 답을 모르겠습니다ㅜㅠ
```

## 기타
- 사전 과제 필수 키워드에 대해서는 정리/리뷰 하셔야 합니다.
- 사전 학습 정리는 자유 분량입니다.
- 문제를 못 풀었다면 어디까지 생각하고 접근했는지 Readme에 기록해주세요!


# 절대경로, 상대경로
![경로](https://github.com/onukki/insight-10th/assets/144572748/0622dd94-1816-4af3-ae2f-ce30db746097)>

|  | 절대경로 | 상대경로 |
| --- | --- | --- |
| 정의 | 최상위 디렉토리(파일의 root)부터 시작하여 목적지까지의 전체적인 경로 | 현재 디렉토리를 기준으로 상위, 하위 디렉토리를 이동하며 표현되는 경로 |
| 특징 |  최상위 / 를 포함 | 최상위 / 를 거치지 않고도 이동이 가능함 |
| 예시 | C:\Program Files\Git | /content/drive/MyDrive |

```
> 추가 예시

현재 작업 디렉토리 -  /content/drive/MyDrive/MyPythonFiles/TextFiles/A
```
![경로2](https://github.com/onukki/insight-10th/assets/144572748/caf319f0-549a-4c87-867c-285d9833e0bc)

```
> 오류 (파일이 열리지 않음)
현재 작업 디렉터리를 확인하고 필요시 현재 디렉터리를 작업하는 폴더로 변경
→ 현재 디렉터리를 기준으로 상대 경로를 활용해 파일을 불러오는 것이 바람직한 접근
```


# read file in python
|  | CSV 파일 | EXCEL 파일 |
| --- | --- | --- |
| 정의 | 데이터 값을 쉼표로 구분하고 있는 텍스트 파일 | 행과 열이 데이터프레임의 행, 열로 일대일 대응 |
| 예시 | pandas.read_csv("파일경로(이름).csv") | pd.read_excel("파일경로.xlsx", engine = 'openpyxl') |

```
> index_col
: 불러온 데이터중 하나의 칼럼을 인덱스로서 설정

pd.read_csv('data/SeoulFloating.csv',index_col='date').head()
```

```
> usecols
: 데이터중 원하는 칼럼만 선별하여 불러옴

pd.read_csv('data/SeoulFloating.csv',usecols=['date','hour']).head()
```

```
> 오류 (인코딩 과정에서 발생)
UnicodeDecodeError: 'utf-8' codec can't decode byte 0xc1 in position 48: invalid start byte

[해결방법] utf-8 방식말고 다른 인코딩 방식을 지정
df=pd.read_csv('경로/파일명.csv',encoding='CP949')
```

# preprocessing in data science
```
> 데이터 전처리의 과정
1. 데이터 세트 확인
2. 결측값 처리
3. 이상값 처리
4. 변수 가공
```

### 데이터 세트 확인
```
- 질적·범주형 <-> 양적·수치형
- 양적·수치형 데이터 중 트랜드가 보이면 연속형, 트렌드가 없다면 이산형으로 구분
- ex) 지하철 출입문 : [질적·범주형] 열차의 종류와 호선
                       [양적·수치형] 출입문이 닫히는 동작 시간 -> 연속형 변
                                    장애물 검지 횟수 -> 이산형 변수
```

### 결측값 처리
**1. 결측값이란**
```
   - 데이터를 수집하고 입력하는 과정에서 누락되는 값
```

**2. 누락 데이터 확인**
```
1) `info()`: 데이터 프레임의 요약정보를 출력하면, 
    각 열에 속하는 유효한 값(non-null, 즉 NaN 값이 아닌)의 개수를 보여줍니다.

2) `value_counts(dropna=False)`: 각 열의 결측값을 포함한 전체 데이터 확인 가능

3) `isnull()`: 누락데이터면 True, 유효한 데이터면 False 반환
    **`df.isnull().sum()` 의 형식으로 자주 사용!**

4) `notnull()`: 유효데이터면 True, 누락데이터면 False 반환
```
   
**3. 결측값 처리 방법**
```
1) 삭제 : 결측값이 무작위로 발생한 경우에 사
2) 대체
   (1) 일괄 대체 : 모든 변수들의 평균값을 구해 일괄적으로 대체
   (2) 유사 유형 대체 : 범주형 변수들을 활용해 유사한 유형의 평균값으로 대체
```

### 이상값 처리
**1. 이상치란**
```
기존 데이터들과 거리가 먼 데이터
ex) [234,234, 267, 1, 200, 245, 300, 199, 250, 8999, 245] -> 이상치 : 1, 8999
```

**2. 이상치 확인**
```
1) df.describe()
2) 시각화를 통해 확인 (BoxPlot) -> 분석가의 자의적인 판단이 반영되거나 일일이 수치를 확인해야 하는 번거로움 존재
3) Z-score
```
![Z-score](https://github.com/onukki/insight-10th/assets/144572748/003b8c40-882b-4164-bf11-ddeef7afa682)

```
4) Tukey Fences
```
![Tukey Fences](https://github.com/onukki/insight-10th/assets/144572748/95faa2b4-0789-4f6c-9906-5c7fbbb50f32)


**4. 이상치 처리**
```
1) 전체 삭제
- 해당 관측치를 삭제
- 단순 오타, 데이터 처리 과정에서의 오류 등의 경우에 사용

2) 다른 값으로 대체
- 관측치의 숫자가 작은 경우,전체 삭제를 하면 관측치의 절대량이 작아져 신뢰성 문제가 발생
- 다른 값(평균 등)으로 대체, 결측값과 유사하게 다른 변수들을 사용해서 예측모델을 만들고, 이상값을 예측한 후 해당 값으로 대체

3) 변수화
- 이상값이 자연발생한 경우, 단순 삭제나 대체를 통해 수립된 모델은 설명/예측하고자 하는 현상을 잘 설명하지 못할 수 있음

4) 리샘플링
- 자연발생한 이상값을 처리하는 또 다른 방법으로, 이상값을 포함한 모델과 제외한 모델을 모두 만들고 각각의 모델에 대한설명
```

### 변수 가공
```
1. 구간화
- 연속 데이터를 그대로 사용하기 보다는 일정한 구간으로 나눠서 분석
```
![구간화](https://github.com/onukki/insight-10th/assets/144572748/3d39dfc5-69ce-4cf2-87fc-f63853ce3246)
```
2. 더미 변수
- 0과 1로 표현되는 
- 범주형 변수를 연속형 번수로 변환하기 위해 사용
```
![더미변수](https://github.com/onukki/insight-10th/assets/144572748/27385be2-ea9e-4b16-acd6-6bfed463df43)
```
```
3. 변환
```
![변환](https://github.com/onukki/insight-10th/assets/144572748/46a9655c-de6e-49e9-b19e-ce512c813b70)
```
5. 스케일
- 변수의 **단위를 변경**하고 싶거나, 변수의 **분포가 편향**되어 있을 경우, 각 열(변수)에 속하는 데이터 값을 동일한 크기
  기준으로 나눈 비율로 나타내는 정규화가 필요
- 가장 자주 사용하는 방법 : Log 함수
- 유사하지만 좀 덜 자주 사용되는 방법 : 제곱근을 취함
- 라이브러리 임포트 : from sklearn.preprocessing import StandardScaler, MinMaxScaler, QuantileTransformer, RobustScaler

<StandardScaler>
각 feature의 평균을 0, 분산을 1로 변경
<MinMaxScaler>
모든 feature가 0과 1사이에 위치하게 만듦
```
