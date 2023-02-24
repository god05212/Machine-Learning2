# Health Insurance Cross Sell Prediction
## 자동차 보험에 관심을 가질 건강 보험 소유자 예측하기
프로젝트 기간: 2023/02/13(월) ~ 2023/02/17(금)  
<br/>
## 개요
건강 보험 소유자가 자동차 보험에도 관심을 가질지 예측하는 모델을 만드는 프로젝트입니다. 보험 상품은 기본적으로 미래를 예측하는 모델을 바탕으로 설계됩니다. 생명보험의 경우 대부분의 보험 회사는 평균 수명 예측 모델을 구축하고 있거나, [캐글](https://www.kaggle.com/anmolkumar/health-insurance-cross-sell-prediction)처럼 보험에 대한 관심 여부를 예측하는 모델을 구축하기도 합니다. 이러한 모델들을 바탕으로 보험료를 얼마 책정할지, 혹은 보험금을 얼마나 지급해줘야 하는지, 혹은 보험사의 기대 이익이 얼마가 될지 계산 할 수 있습니다. 이처럼 고객이 자동차 보험에 관심을 가질지 예측하는 모델을 구축하면 회사에 매우 도움이 됩니다. 그에 따라 해당 고객에게 다가가 비즈니스 모델과 수익을 최적화 하기 위한 커뮤니케이션 전략을 계획할 수 있기 때문입니다. 따라서, 특정 회사의 고객 정보 등을 통해서 자동차보험에 관심 여부를 예측하는 모델을 만들고자 하였습니다.  
<br/>
## 사용한 데이터셋
Health Insurance Cross Sell Prediction: Predict Health Insurance Owners' who will be interested in Vehicle Insurance  
- Analytics Vidhya  
- https://www.kaggle.com/anmolkumar
- https://www.kaggle.com/anmolkumar/health-insurance-cross-sell-prediction  

위 데이터셋은 고객이 자동차 보험에 관심이 있는지 여부를 예측하기 위해 인구 통계(성별, 연령, 지역 코드 유형), 차량(차량 연령, 손상), 정책(프리미엄, 소싱 채널) 등에 대한 정보에 대한 데이터를 가지고 있습니다.  
<br/>
## 프로젝트 목록
1. Introduction
    - Data description
2. Basic Exploration  
    - Read dataset  
    - Some information  
    - Data visualization  
3. Data preprocessing  
4. Machine Learning model  
    - Logistic Regression  
    - Random Forest Classifier  
    - Hyperparameter Tuning of Random Forest  
    - Decision Tree Classifier  
    - Hyperparameter Tuning of Decision Tree  
5. Conclusion
<br/>

## 프로젝트 수행 과정
- 훈련 데이터 세트와 테스트 데이터 세트는 모두 non-null 값을 가집니다. 따라서 결측값을 처리할 필요가 없었습니다.
- 그래프를 통해 특성에 따른 관심 여부를 살펴보았습니다.
- 쓸 일 없는 ID 열은 train 및 test 데이터에서 모두 제거하고, 범주형 데이터를 숫자 데이터로 분류하였습니다.
- 속성 간의 상관 관계를 확인하고, 높은 상관 관계인 열은 더 나은 정확도를 위해 MinMaxScaler에서 제외 하였습니다.
- MinMaxScaler를 사용하여 숫자 데이터의 크기를 조정하였습니다.
- train/validation 데이터 셋으로 나누어 주었습니다.
- Logistic Regression, Random Forest Classifier, Hyperparameter Tuning of Random Forest,  Decision Tree Classifier, Hyperparameter Tuning of Decision Tree을 사용하였고, 모델의 accuracy를 비교하였습니다.
<br/>

## 모델의 validation dataset에 대한 accuracy (소숫점 다섯 째 자리에서 반올림)
| Model | accuracy |
|:----------------------------------------|:-------|
| Logistic Regression                     | 0.8750 |
| Random Forest Classifier                | 0.8650 |
| Hyperparameter Tuning of Random Forest  | 0.8652 |
| Decision Tree Classifier                | 0.8218 |
| Hyperparameter Tuning of Decision Tree  | 0.8751 |
<br/>

## 최종 모델
Hyperparameter Tuning of Decision Tree
- dataset에 대한 결과
    - accuracy: 약 0.8751
<br/>

## 결론
특정 회사의 고객 정보 등을 통해서 자동차보험에 관심 여부를 예측하는 모델을 만들고자 하였습니다. 그 결과 하이퍼파라미터 튜닝한 의사결정 트리가 가장 높은 정확도를 보여주었다. 추가로, 자동차 보험 마케팅에도 효과전인 전략을 제시할 수 있습니다.  

**분석 결과**  
1. 성별이 고객의 관심 여부에서 큰 역할을 하지 못하고 긍정적인 반응과 부정적인 반응의 비율이 거의 같습니다.  
2. 35세 미만의 젊은이들은 보험에 거의 관심이 없습니다. 35세 이상의 사람들은 보험에 더 관심이 많은 경향이 있습니다.  
3. 운전 면허증의 여부는 고객의 관심 여부에 큰 역할을 하지 않습니다.  
4. 지역과 관심 여부의 상관 관계가 적습니다.  
5. 건강보험 보유 기간은 관심 여부에 아무런 영향이 없는 것 같습니다. 긍정적인 반응과 부정적인 반응의 비율이 거의 동일한 것으로 보입니다.  
6. 과거 자동차에 손상을 입힌 경험이 있을 수록 긍정적으로 반응하는 경향이 있습니다.  

따라서 35세 이상, 과거 자동차에 손상을 입힌 경험이 있는 사람들을 대상으로 전략적인 마케팅이 가능할 것임을 알 수 있었습니다.
