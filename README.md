# 📘 IT시스템종합설계 (총 4개 프로젝트)
**학과:** 전자전기공학부 4학년  
**이름:** 이동관  

이 저장소는 **IT시스템종합설계(2024-1)** 과목에서 수행한 총 4개의 프로젝트를 모아둔 레포지토리입니다.  
각 프로젝트별 상세 설명과 코드, 결과는 하위 디렉토리에서 확인할 수 있습니다.

---

## 📂 프로젝트 목록

### 1️⃣ Polynomial Regression & Early Stopping
- (-2,2) 구간 300개 데이터 기반 다항 회귀 모델 학습  
- Learning Curve & Early Stopping으로 최적 차수(3차) 선정  
- 🔑 핵심: Validation Error 최소 모델 찾기  
- 👉 [프로젝트 보기](./1.Find_best_polynomial_parameter)

---

### 2️⃣ 머신러닝 분류기 성능 비교 (Softmax / SVM / Random Forest)
- MNIST 데이터셋 기반 머신러닝 분류기 성능 및 연산량 비교  
- Softmax Regression: 82.4%  
- SVM (RBF Kernel): 97%  
- Random Forest: 97% (가장 효율적)  
- 👉 [프로젝트 보기](./2.ML_classifiers_comparison)

---

### 3️⃣ MNIST 분류 – FCNN & CNN 성능 개선
- 다층 퍼셉트론(FCNN) → 정확도 99.3% 달성  
- 합성곱 신경망(CNN) → 정확도 99.7% (최고 성능)  
- 데이터 증강, BatchNorm, Dropout, He Init, ReduceLROnPlateau 적용  
- 👉 [프로젝트 보기](./3.FullyConnected_vs_CNN)

---

### 4️⃣ CNN 기반 최종 MNIST 분류 모델
- Conv2D + MaxPooling + GAP 기반 최적화 CNN  
- 최종 정확도: 99.7%  
- FCNN 대비 이미지 특성을 더 잘 학습  
- 👉 [프로젝트 보기](./4.CNN_final)
