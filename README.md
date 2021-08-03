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
