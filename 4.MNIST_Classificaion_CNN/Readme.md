🧠 IT시스템종합설계 프로젝트 – CNN 기반 MNIST 이미지 분류
📌 프로젝트 개요

이 프로젝트는 2024-1 IT시스템종합설계 과목에서 수행되었습니다.
기존의 다층 퍼셉트론(FCNN) 기반 분류 모델을 확장하여, 합성곱 신경망(CNN)을 활용해 MNIST 숫자 이미지 분류 정확도를 개선하는 것을 목표로 했습니다.

🚀 연구 목표

Baseline 성능 확보: FCNN으로 약 99.3% 정확도 달성

CNN 적용: Conv2D + MaxPooling을 적용해 이미지의 공간적 특징 학습

성능 개선 기법 적용

Batch Normalization & He Initialization

Dropout으로 과적합 방지

Data Augmentation (rotation, shift, zoom)

Optimizer: Nadam + ReduceLROnPlateau

Global Average Pooling(GAP) 추가

🏗️ 모델 구조
model = keras.models.Sequential([
    Conv2D(64, kernel_size=7, padding="same", activation="relu", input_shape=[28, 28, 1]),
    BatchNormalization(),
    MaxPooling2D(pool_size=2),

    Conv2D(128, kernel_size=3, padding="same", activation="relu"),
    BatchNormalization(),
    Conv2D(128, kernel_size=3, padding="same", activation="relu"),
    BatchNormalization(),
    MaxPooling2D(pool_size=2),

    Conv2D(256, kernel_size=3, padding="same", activation="relu"),
    BatchNormalization(),
    Conv2D(256, kernel_size=3, padding="same", activation="relu"),
    BatchNormalization(),

    GlobalAveragePooling2D(),

    Dense(128, activation="relu"), Dropout(0.5),
    Dense(64, activation="relu"), Dropout(0.5),
    Dense(10, activation="softmax")
])

📊 실험 결과
모델	특징	정확도
FCNN (Baseline)	BatchNorm, Dropout, Adam, 증강 적용	99.3%
CNN (기본)	Conv2D + MaxPooling	98.8%
CNN (정규화 + He Init)	BatchNorm 추가	99.4%
CNN (GAP 추가 + 구조 최적화)	Global Avg Pooling	99.5%
CNN (최종)	Nadam + ReduceLROnPlateau 적용	99.7%

➡️ 최종적으로 CNN 모델이 최고 성능 (99.7%) 을 달성했습니다.

🎯 배운 점

이미지 데이터는 FCNN보다 CNN이 적합하며, 공간적 패턴 학습에 유리하다.

Batch Normalization, He Initialization, Dropout, Data Augmentation 이 성능 향상에 크게 기여했다.

Learning Rate Scheduling (ReduceLROnPlateau)과 Optimizer 선택(Nadam)이 최종 성능 개선의 핵심이었다.

⚙️ 실행 방법
1. 저장소 클론
git clone https://github.com/yourusername/mnist-cnn-itdesign.git
cd mnist-cnn-itdesign

2. 라이브러리 설치
pip install -r requirements.txt

3. 학습 실행
python train_cnn.py

4. Colab에서 실행

Google Colab 환경을 사용하는 경우:

!git clone https://github.com/yourusername/mnist-cnn-itdesign.git
%cd mnist-cnn-itdesign
!pip install -r requirements.txt
!python train_cnn.py

📚 참고

MNIST Dataset (Yann LeCun et al.)

TensorFlow / Keras 공식 문서
