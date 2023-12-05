# Health Insurance Cross Sell Prediction
## 자동차 보험에 관심을 가질 건강 보험 소유자 예측하기
프로젝트 기간: 2023/01/16(월) ~ 2023/01/30(월)  
<br/>
## 개요
자동차 보험에 대한 고객의 관심 여부를 예측하는 모델을 개발하는 프로젝트를 진행하였습니다. 보험 상품은 미래를 예측하는 모델을 기반으로 설계되는데, 생명보험의 경우 평균 수명 예측 모델이나 보험에 대한 관심 여부를 예측하는 모델을 구축하고 있습니다. 이러한 모델을 활용하여 보험료의 책정이나 보험금 지급 등 보험사의 이익을 최적화할 수 있습니다.

따라서, 특정 회사의 고객 정보를 활용하여 자동차 보험에 대한 관심 여부를 예측하는 모델을 개발하고자 하였습니다. 이 모델을 통해 고객이 자동차 보험에 관심을 가질지 예측할 수 있으며, 이를 기반으로 비즈니스 모델과 수익을 최적화하기 위한 커뮤니케이션 전략을 계획할 수 있어 보험회사에 매우 도움이 될 것으로 예상됩니다.  
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
- 히스토그램과 상자 그림을 사용하여 데이터를 시각화하였습니다. 성별, 운전면허 여부, 지역 코드, 과거 자동차에 손상을 입힌 경험의 유무에 따른 관심 여부를 확인하기 위해 plotly 라이브러리를 사용하여 히스토그램을 그렸습니다. 그리고 나이, 건강보험 보유 기간에 따른 관심 여부를 확인하기 위해 seaborn 라이브러리를 사용하여 상자 그림을 그렸습니다.
- ID 열은 식별자 역할을 하기에, train 및 test 데이터에서 모두 제거하고, 범주형 데이터를 숫자 데이터로 분류하였습니다.
- 속성 간의 상관 관계를 확인하기 위해 `sns.heatmap(train.corr(), annot=True)`를 사용하여 히트맵을 그렸습니다. 이를 통해 속성들 간의 상관계수를 시각적으로 확인할 수 있었습니다.
- 상관 관계가 높은 열은 서로 강한 관련성을 가지고 있을 수 있습니다. 이러한 열을 동시에 모델에 포함 시키면 다중공선성 문제가 발생할 수 있습니다. 다중공선성은 모델의 안정성을 저해하고 예측력을 감소시킬 수 있으므로 상관 관계가 높은 열을 제외하고 Min-Max 스케일링을 적용하여 모델의 안정성을 높이고 예측력을 향상 시키고자 하였습니다.
- train/validation 데이터 셋으로 나누어 주었습니다.
- Logistic Regression, Random Forest Classifier, Hyperparameter Tuning of Random Forest,  Decision Tree Classifier, Hyperparameter Tuning of Decision Tree를 사용하였고, 모델의 accuracy를 비교하였습니다.
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
