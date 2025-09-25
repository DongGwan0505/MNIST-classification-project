# 📘 IT시스템종합설계 - Homework 2
**학과**: 전자전기공학부 4학년 
**이름**: 이동관  

---

## 🚀 프로젝트 개요
본 프로젝트는 **MNIST 손글씨 이미지 데이터셋**을 다양한 머신러닝 분류기(classifier)로 학습하여  
성능(정확도)과 연산량(훈련/테스트 시간)을 비교 분석하는 과제입니다.  

- **Dataset**  
  - Training set: 60,000 images (28×28 = 784 features)  
  - Test set: 10,000 images  
  - Pixel scaling: `pixel / 255`  
  - SVM: PCA를 적용하여 차원을 150으로 축소  

---

## ✨ 과제 1: Classifier 별 성능 분석
### 🔹 Softmax Regression
- Hyperparameter: Regularization Parameter **C** (0.01 ~ 100)  
- C=1일 때 최고 정확도 **82.4%**  
- 학습 시간이 C 증가에 따라 급격히 증가 (Overfitting 발생)  
- **결론**: Softmax Regression의 최적 성능은 **C=1**

---

### 🔹 Support Vector Machine (SVM, RBF Kernel)
- Hyperparameters: **C, Gamma**  
- PCA로 차원 축소 후 학습  
- 결과:  
  - Gamma=0.001 → **97% (Best)**  
  - Gamma 증가 시 성능 저하 및 연산 시간 급증  
- **결론**: **C=1, Gamma=0.001**이 최적 성능

---

### 🔹 Random Forest
- Hyperparameter: **n_estimators** (트리 개수)  
- 결과:  
  - n_estimators=50 → 정확도 **97% (Best)**  
  - 이후 트리 개수 증가 시 성능 개선 없음, 단지 연산 시간 증가  
- **결론**: **n_estimators=50**이 최적 성능

---

## ✨ 과제 2: Classifier 비교 분석
| Classifier          | 최적 하이퍼파라미터          | 정확도   | 학습 시간       | 테스트 시간  |
|---------------------|-----------------------------|---------|----------------|-------------|
| Softmax Regression  | C=1                         | 82.4%   | 53.1 s         | ~1 ms       |
| Support Vector Mach.| C=1, Gamma=0.001           | 97%     | 2 min 25 s     | 46.2 s      |
| Random Forest       | n_estimators=50            | 97%     | 40 s           | 273 ms      |

---

## 🔍 결과 분석
- **성능 (정확도)**: SVM과 Random Forest가 97%로 우수  
- **연산량 (훈련/테스트 시간)**: Random Forest가 SVM 대비 훨씬 효율적  
- **Softmax Regression**: 빠르지만 다중 클래스 분류에서는 정확도 부족  
- **SVM**: 성능은 좋지만 훈련/테스트 시간이 가장 오래 걸림  
- **Random Forest**: 정확도와 연산 효율성의 균형이 가장 좋음  

---

## ✅ 최종 결론
- MNIST 데이터 분류에서 최적 모델은 **Random Forest (n_estimators=50)**  
- 성능(97%)과 효율성(빠른 훈련/테스트 시간) 모두에서 가장 우수  
- SVM은 고성능이지만 연산 비용이 크고, Softmax Regression은 간단하나 정확도 한계가 있음  

---

## 🛠️ 사용 기술
- Python 3.8+  
- NumPy, Matplotlib  
- Scikit-learn (`LogisticRegression`, `SVC`, `RandomForestClassifier`, `PCA`, `StandardScaler`)  

---

## 👤 Author
- **이동관 (Lee DongGwan)**  
  - 전자전기공학부 4학년  
  - 관심분야: 머신러닝, 임베디드, 반도체 설계  
