## Dacon 신약개발 AI 경진대회

- 대회 개요 (2023.08.07 ~ 2023.09.25) https://dacon.io/competitions/official/236127/overview/description
- 정형 회귀 예측 (RMSE)
- 인간과 쥐의 간 대사 효소에 대한 화합물 대사안정성 예측모델 개발 
- 성과 : 8.2%이내 - private 62등/764팀)

## Summary
- **Preprocessing** : 피쳐별 이상치 제거, 중복 SMILES 하나만 남기고 데이터 제거, 결측치 처리(유사 화학변수 값으로 대체)
- **Feature Engineering** :
  - 데이터 수 부족으로 SMILES 분자식에 대한 Descriptor를 화학 데이터 오픈 라이브러리(Moredred)로부터 로드 -3498개 피쳐 추가이후 object 칼럼 선별하여 드롭(약 500개)
  - Catboost 예측시 전체 데이터 10 quantile로 범주화한 값으로 대체 
- **Scaling** : MinMax 스케일링 
- **Model** : Catboost(범주화), LGBM 앙상블 (개인)
- **Ensemble** : 팀원 별로 최고점 모델 예측치 산술평균 앙상블 (Catboost, LGBM, DL)

## Environment
- OS: Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-162-generic x86_64)
- Environment: Anaconda 4.10.3
