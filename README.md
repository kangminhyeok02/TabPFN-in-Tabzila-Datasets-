TabPFN을 활용한 Tabular 데이터 분류 실험 결과와 분석을 담고 있습니다. 이 프로젝트는 기존에 작은 데이터셋에 최적화된 TabPFN 모델을 다양한 방법으로 확장하여 더 큰 데이터셋에 적용 가능하도록 하는 목표로 진행되었습니다.

📌 Introduction
TabPFN은 트랜스포머 기반의 사전 학습 모델로, 주로 작은 크기의 데이터셋에서 뛰어난 성능을 발휘합니다. 하지만 기존에는 결측값이 없고, 숫자 특성을 가진 최대 1,000개의 훈련 샘플과 최대 10개의 클래스를 가진 분류 데이터셋에서만 제한적으로 작동했습니다. 본 프로젝트에서는 TabPFN을 더 큰 데이터셋에서도 사용할 수 있도록 확장하고자 다양한 특징 축소 기법을 적용하여 CatBoost와의 성능을 비교했습니다.

⚙️ Limitations of TabPFN
결측값 처리: 결측값을 처리하지 못함.
데이터셋 제한: 최대 1,000개의 샘플과 10개의 클래스를 가진 데이터셋에서만 최적화.
이 한계를 극복하고자, TabPFN 모델을 축소 기법과 함께 더 큰 데이터셋에 적용하여 성능을 비교하고자 합니다.

🎯 Goals and Experiments
본 프로젝트의 주요 목표는 기존에 작은 데이터셋에서만 잘 작동하던 TabPFN 모델을 다양한 축소 방법(랜덤 샘플링, PCA, MUT 등)을 통해 더 큰 데이터셋에도 적용 가능하도록 개선하고, 이를 CatBoost와 성능 면에서 비교하는 것입니다.

랜덤 샘플링 (Random Sampling): 일부 특징을 무작위로 선택하여 모델에 입력.
PCA (Principal Component Analysis): 주성분 분석을 통해 특징 차원을 줄임.
MUT (Mutual Information): 상호 정보를 기반으로 중요한 특징을 선택.
이러한 기법을 통해 모델의 특징 수를 축소하고 성능을 비교함으로써 TabPFN이 더 큰 데이터셋에서도 적용 가능하도록 확장할 수 있는 가능성을 탐색했습니다.

🔬 Experiments and Findings
자세한 실험 배경과 결과는 아래 PPT에서 확인할 수 있습니다:

TabPFN 배경, 연구 동기, 실험 설정 및 CatBoost와의 비교 실험 결과 (2, 3회차 PPT)
주요 실험 결과
TabPFN + MUT (10): 33개 데이터셋 중 19개에서 CatBoost보다 높은 성능을 기록했습니다.
학습 시간 및 정확도: TabPFN + MUT (10)은 CatBoost에 비해 학습 시간이 더 짧고 높은 평균 정확도를 보였습니다.
특징 수에 따른 성능 변화: 불필요한 특징의 존재가 성능에 영향을 미쳤으며, 특정 데이터셋에서 특징 수 축소가 성능을 향상시켰습니다.
📂 Project Structure
plaintext
코드 복사
TabPFN-in-Tabzila-Datasets/
│
├── data/                     # 실험에 사용된 데이터셋 파일
├── src/                      # TabPFN 모델과 비교 모델을 위한 소스 코드
│   ├── models/               # TabPFN, CatBoost 모델 코드
│   ├── utils/                # 데이터 전처리 및 특징 축소 코드
│   └── main.py               # 메인 실행 파일
├── results/                  # 실험 결과 및 분석 파일
├── requirements.txt          # 필요한 라이브러리 목록
└── README.md                 # 프로젝트 개요 및 설명 파일
📊 Results and Conclusion
**TabPFN + MUT (10)**은 높은 정확도와 짧은 학습 시간으로 Tabzila 데이터셋에서 CatBoost를 능가하는 성능을 보였습니다.
이 프로젝트를 통해 TabPFN의 확장 가능성을 확인했으며, 향후 더 다양한 축소 기법을 탐구하여 적용할 계획입니다.
