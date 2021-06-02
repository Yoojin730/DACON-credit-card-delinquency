## CatBoost

- Categorical + Boosting Model
- Categorical feature를 처리하는 데 중점을 둔 알고리즘
- 기존 GBM 기반 알고리즘이 가지고 있는 target leakage, categorical feature 처리 문제를 해결
  - target leakage: 예측에 사용할 수 없는 데이터가 학습 데이터 셋에 포함될 때 발생
  - categorical problem
    - one-hot encoding은 변수의 수를 크게 증가시킬 수 있음
    - 몇 개의 cluster로 묶고 one-hot encoding을 하거나, 범주의 Target Statistics(TS)를 추정하여 사용하는 방법이 존재
    - Catboost는 Ordered TS 사용 (현 시점을 기준으로 과거 데이터로만 TS 추정)
- Overfitting 문제 해결
  - ordering principle: i번 째 샘플에 대한 잔차를 구하기 위해 (i-1)번 째까지 사용한 데이터로 학습한 모델을 사용 (다른 데이터로 학습한 모델로 잔차를 갱신)
- Categorical feature를 자동으로 전처리 해줌



#### 단점)

- Sparse한 Matrix를 처리하지 못함
- Data의 대부분이 수치형 데이터 일때, 학습시간이 느림