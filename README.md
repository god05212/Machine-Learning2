# Health Insurance Cross Sell Prediction
## 자동차 보험에 관심을 가질 건강 보험 소유자 예측하기
프로젝트 기간: 2023/02/13(월) ~ 2023/02/17(금)  
<br/>
## 개요
건강 보험 소유자가 자동차 보험에도 관심을 가질지 예측하는 모델을 만드는 프로젝트입니다. 보험상품은 기본적으로 미래를 예측하는 모델을 바탕으로 설계됩니다. 생명보험의 경우 대부분의 보험회사는 평균수명 예측 모델을 구축하고 있거나, [캐글](https://www.kaggle.com/anmolkumar/health-insurance-cross-sell-prediction)에서 처럼 보험에 대한 관심 여부를 예측하는 모델을 구축하기도 합니다. 이러한 모델들을 바탕으로 보험료를 얼마 책정할지, 혹은 보험금을 얼마나 지급해줘야 하는지, 혹은 보험사의 기대 이익이 얼마가 될지 계산 할 수 있습니다. 이처럼 고객이 자동차 보험에 관심을 가질지 예측하는 모델을 구축하면 회사에 매우 도움이 됩니다. 그에 따라 해당 고객에게 다가가 비즈니스 모델과 수익을 최적화하기 위한 커뮤니케이션 전략을 계획할 수 있기 때문입니다. 따라서, 특정 회사의 고객 정보 등을 통해서 자동차보험에 관심 여부를 예측하는 모델을 만들고자 하였습니다.
## 사용한 데이터셋
Health Insurance Cross Sell Prediction: Predict Health Insurance Owners' who will be interested in Vehicle Insurance  
- Analytics Vidhya  
- https://www.kaggle.com/anmolkumar
- https://www.kaggle.com/anmolkumar/health-insurance-cross-sell-prediction  

위 데이터셋은 고객이 자동차 보험에 관심이 있는지 여부를 예측하기 위해 인구 통계(성별, 연령, 지역 코드 유형), 차량(차량 연령, 손상), 정책(프리미엄, 소싱 채널) 등에 대한 정보에 대한 데이터를 가지고 있습니다.  
<br/>
## 프로젝트 수행 과정
1. Introduction
Data description
2. Basic Exploration  
Read dataset  
Some information  
Data visualization  
3. Data preprocessing  
4. Machine Learning model
Logistic Regression
Random Forest Classifier
Hyperparameter Tuning of Random Forest
Decision Tree Classifier
Hyperparameter Tuning of Decision Tree
5. Conclusion
