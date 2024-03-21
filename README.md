# 23DataMining
2023-2 Final project in Data Mining course, majoring in Statistics, Hankuk University of Foreign Studies

## 데이터마이닝및실습 팀 과제 최종보고서
### 0. 팀원
- 김송하(컴퓨터전자시스템공학부, 202000715)
- 정민규(컴퓨터전자시스템공학부, 202003121)
### 1. 프로젝트 개요
- 목표
  주어진 데이터 셋인 Wine Quality Dataset을 시각적으로 분석하여 fixed acidity, volatile acidity 등 다른 요소들과 quality간의 상관 관계를 분석하고 3개의 모델을 사용하여 두 가지 실험을 진행하여 다양한 품질 점수 카테고리로 분류한다. 이때, 세 가지 ML모델을 학습하고 어떤 모델이 가장 좋은 지 결정한다

#### 실험 환경
- 실험은 총 2가지로 진행되었다. 모든 요소들을 사용해 quality를 예측하는 실험과 시각적 분석을 통해 quality와 상관관계가 높은(상관관계를 구하여 절댓값이 0.2보다 큰 상관 관계를 갖는) 요소들을 사용하여 quality를 예측하는 실험이다. 모든 실험은 아래와 같은 환경에서 진행되었다. 진행되었다.
- R 버전: 4.3.2 (2023-10-31)
- R 패키지 버전 : pROC_1.18.5, reshape2_1.4.4, MASS_7.3-60, MLmetrics_1.1.1, yardstick_1.2.0, caret_6.0-94, lattice_0.21-9, rpart_4.1.23, randomForest_4.7-1.1, e1071_1.7-14, corrplot_0.92, ggplot2_3.4.4, readr_2.1.4, dplyr_1.1.4

### 2. 프로젝트 과정
- 사용한 데이터 셋
  Wine Quality Dataset (WineQT): https://www.kaggle.com/datasets/yasserh/wine-quality-dataset
  Size: total data size: 1143
  columns : 13 (fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol, quality, Id)
- 사용한 모델
  Support Vector Machines (SVM)
  주어진 데이터가 어느 카테고리에 속할지 판단하는 이진 선형 분류 모델. 서포트 벡터들의거리인 마진의 최대치를 찾는 것이 svm의 목표이다.
  svm모델의 장점으로는 분류문제와 예측문제 동시에 쓸 수 있고, 신경망 기법에 비해 과적합 정도가 덜하고 예측의 정확도가 높다. 그리고 사용하기 쉽다.
  이 모델의 단점으로는 kernel과 모델 파라미터를 조절하기 위한 테스트를 여러 번 해봐야 최적화된 모형을 만들 수 있고, 모형 구축 시간이 오래 걸린다. 또한 결과에 대한 설명력이 떨어진다는 단점이 있다.
  Decision Trees
  decision tree란 입력값에 대한 예측값을 노드로 가지는 tree로 나타내어주는 모형.설명변수 간의 관계나 척도에 따라 목표변수를 예측하거나 분류하는 문제에 활용되는 트리 구조의 모델이다. 설명변수의 관측값을 모델에 입력해 목표변수를 분류하거나 예측하는 지도학습 기반의 방법론이다.
  의사결정 트리 모델을 사용하는 주된 이유는 목표변수를 예측하거나 분류 문제를 해결함에 있어서 어떤 설명변수가 가장 중요한 영향인자인지 확인할 수 있고, 나아가 설명변수별로 어떤 척도에 따라 예측 또는 분류했는지 상세한 기준을 알 수 있다는 장점이 있다.
  Random Forest
  기존 decision tree의 이점을 살리고 Bagging변수를 랜덤으로 선택하는 과정을 추가함으로써 개별 노드들의 상관성을 줄여 예측력을 향상한 앙상블 모형. 램덤 포레스트는 램덤성에 의해 트리들이 서로 조금씩 다른 특성을 갖는 특성이 있다.
  이 특성은 각 트리들의 예측들이 비상관화 되게하며, 겨로가적으로 일반화 성능을 향상시키는 효과가 있다.
  Logistic Regression
  수학을 사용하여 두 데이터 요인 간의 관계를 찾는 데이터 분석 기법으로 두 데이터 간의 관계를 사용하여 다른 요인을 기반으로 이러한 요인 중 하나의 값을 예측한다. 예측은 일반적으로 유한한 수의 결과를 가진다.
  로지스틱 회귀는 간편성, 속도, 유연성, 가시성 부분에서 장점을 가진다.
