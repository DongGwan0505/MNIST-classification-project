🧠 IT시스템종합설계 프로젝트 – MNIST 이미지 분류
📌 프로젝트 개요

이 프로젝트는 2024-1 IT시스템종합설계 과목에서 수행되었습니다.
단순 회귀 모델에서 출발하여 머신러닝 기법을 적용하고, 딥러닝 구조(Fully Connected Neural Network, Convolutional Neural Network)까지 확장하여 MNIST 숫자 이미지 분류 정확도를 점진적으로 개선하는 것을 목표로 했습니다.

🚀 프로젝트 흐름

Polynomial Regression (기초 단계)

다항 회귀 모델 (차수 1~40) 실험

최적 차수=3 → Validation Error ≈ 0.237

머신러닝 분류기 (Baseline)

Softmax Regression: 정확도 82.4%

SVM (RBF kernel): 정확도 97%

Random Forest: 정확도 97%

Fully Connected Neural Network (FCNN)

ReLU 활성화 함수 기반 다층 퍼셉트론 구조

Batch Normalization, He Initialization, Dropout, Data Augmentation 적용

최종 정확도 99.3% 달성

Convolutional Neural Network (CNN)

Conv2D + BatchNorm + ReLU + MaxPooling 구조

Optimizer: Nadam + ReduceLROnPlateau

최종 정확도 99.7% 달성 (최고 성능)

🏗 모델 구조 (FCNN 예시)
```python
model = keras.models.Sequential([
    Flatten(input_shape=[28, 28]),
    Dense(1024, activation="relu", kernel_initializer="he_normal"),
    BatchNormalization(),
    Dropout(0.3),
    Dense(512, activation="relu", kernel_initializer="he_normal"),
    BatchNormalization(),
    Dropout(0.3),
    Dense(256, activation="relu", kernel_initializer="he_normal"),
    BatchNormalization(),
    Dropout(0.3),
    Dense(128, activation="relu", kernel_initializer="he_normal"),
    BatchNormalization(),
    Dropout(0.3),
    Dense(64, activation="relu", kernel_initializer="he_normal"),
    BatchNormalization(),
    Dropout(0.3),
    Dense(10, activation="softmax")
])

📊 성능 비교
모델	정확도
Polynomial Regression	Val Error = 0.237
Softmax Regression	82.4%
Random Forest	97%
SVM (RBF)	97%
FCNN (최적화)	99.3%
CNN (최종)	99.7%
🎯 배운 점

다항 회귀에서는 차수 선택과 Early Stopping의 중요성을 확인함

SVM과 Random Forest는 강력한 머신러닝 Baseline을 제공

FCNN에서는 정규화, 초기화, 드롭아웃, 데이터 증강이 성능 향상에 핵심적임

CNN은 이미지 데이터의 공간적 특성을 가장 잘 반영하여 최고 성능을 달성함

⚙️ 실행 방법

저장소 클론

git clone https://github.com/yourusername/mnist-classification-itdesign.git
cd mnist-classification-itdesign


필요 라이브러리 설치

pip install -r requirements.txt


학습 실행

python train_fcnn.py   # FCNN 학습
python train_cnn.py    # CNN 학습

📚 참고 문헌

MNIST Dataset (Yann LeCun et al.)

TensorFlow/Keras 공식 문서
