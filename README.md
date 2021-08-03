# Home Credit Default Risk

## Description

개인 대출 고객이 채무를 이행할지 여부를 예측하는 Competition

![image](https://user-images.githubusercontent.com/67913569/127973500-14408130-6566-466e-b26b-39dff02f0e8e.png)


## Data

* application: 현재대출(고객 정보와 현재 대출 정보 제공)
* previous_application: 과거대출이력(고객의 현재 대출 이전 과거 대출 정보 제공)
* bureau: 타사 대출이력(고객의 현재 대출 이전 타사 대출 정보 제공)
* bureau_bal: 타사 대출 월별 잔액(타사 대출의 월별  채무 이행 이력)
* pos_cash_balance/installments/credit_card_balance: 현금/카드대출 잔액, 납부이력(월별 현금/카드대출 잔액, 대출 채무 이행 이력)

<img src="https://user-images.githubusercontent.com/67913569/127853093-b8797cbb-2508-420c-b37c-6940e0e7c61f.png">

## Metric: ROC AUC

Submissions are evaluated on area under the ROC curve between the predicted probability and the observed target

![image](https://user-images.githubusercontent.com/67913569/127975670-b2af66df-4bc0-4a5e-877f-72448a29daaf.png)

## Feature Engineering

* 기본 feature engineering
  - 스케일링(Scaling): StandardScaler, MinMaxScaler
  - 변환(Transformation): 로그 변환(Log Transformation), Polynomial 피처 변환, PCA 변환
  - 인코딩(Encoding): 레이블 인코딩, 원핫 인코딩
  - 결측치(Null값)/이상치(Outlier) 치환: 
  - Skew 데이터 세트 보정: 오버/언더 Sampling

* 업무적으로 중요한 feature 들의 재 결합 및 재 가공
  - 중요도가 높은 feature들에 대해서 재 가공
  - 주요 컬럼 끼리 차 또는 합, 비율 등을 재 가공
  - 주요 컬럼 및 가공 컬럼들에 대한 다양한 aggregation 적용
  - 업무적으로 의미 있는 컬럼 재 생산

* 최근 데이터, Active인 데이터 위주 필터링 후 데이터 가공
  - 시계열성 데이터의 경우 오래전 데이터 보다는 최근 데이터를 기반으로 별도의 재 가공 적용
  - 업무적으로 여전히 유효한 최근 데이터를 필터링하여 재 가공  




