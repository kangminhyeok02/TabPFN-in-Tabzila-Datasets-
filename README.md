## TabPFN을 활용한 Tabular 데이터 분류 실험 결과와 분석을 담고 있습니다.

### 📌 Introduction
TabPFN은 트랜스포머 기반의 사전 학습 모델로, 주로 작은 크기의 데이터셋에서 뛰어난 성능을 발휘합니다. 하지만 기존에는 결측값이 없고, 숫자 특성을 가진 최대 1,000개의 훈련 샘플과 최대 10개의 클래스를 가진 분류 데이터셋에서만 제한적으로 작동했습니다. 본 프로젝트에서는 TabPFN을 더 큰 데이터셋에서도 사용할 수 있도록 확장하고자 다양한 특징 축소 기법을 적용하여 CatBoost와의 성능을 비교했습니다.

### ⚙️ Limitations of TabPFN
결측값 처리: 결측값을 처리하지 못함.
데이터셋 제한: 최대 1,000개의 샘플과 10개의 클래스를 가진 데이터셋에서만 최적화.
이 한계를 극복하고자, TabPFN 모델을 축소 기법과 함께 더 큰 데이터셋에 적용하여 성능을 비교하고자 합니다.

### 🎯 Goals and Experiments
본 프로젝트의 주요 목표는 기존에 작은 데이터셋에서만 잘 작동하던 TabPFN 모델을 다양한 축소 방법(랜덤 샘플링, PCA, MUT 등)을 통해 더 큰 데이터셋에도 적용 가능하도록 개선하고, 이를 CatBoost와 성능 면에서 비교하는 것입니다.

- 랜덤 샘플링 (Random Sampling): 일부 특징을 무작위로 선택하여 모델에 입력.
- PCA (Principal Component Analysis): 주성분 분석을 통해 특징 차원을 줄임.
- MUT (Mutual Information): 상호 정보를 기반으로 중요한 특징을 선택.

### 🔬 Experiments and Findings
자세한 실험 배경과 결과는 아래 링크의 ppt 에서 확인할 수 있습니다:
https://www.notion.so/PPT-f3c31de55239423481928ffcadc5b331 2,3회차 ppt 


