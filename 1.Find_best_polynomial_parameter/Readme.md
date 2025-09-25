# 📘 IT시스템종합설계 - Homework 1
**학과**: 전자전기공학부 4학년  
**이름**: 이동관  

---

## 🚀 프로젝트 개요
본 프로젝트는 구간 (-2, 2)에서 생성된 300개의 측정 데이터를 이용하여  
**Polynomial Regression 모델의 최적 차수**를 찾는 과제입니다.  

- **과제 A**: 데이터 시각화 및 적절한 모델 차수 예측  
- **과제 B**: Train/Validation 분리 후 Learning Curve 비교  
- **과제 C**: Early Stopping 적용하여 최적 모델 도출  

---

## ✨ 과제 A: 데이터 시각화 및 차수 예측
- 다양한 차수(1, 2, 3, 5, 10, 20, 40차) 모델 학습  
- 고차수 모델에서 **Overfitting** 발생 확인  
- StandardScaler 적용 시 고차 모델 안정화 가능  
<img width="1070" height="290" alt="image" src="https://github.com/user-attachments/assets/f95b1f1b-3800-456d-8e1c-91ab76589a33" />
<img width="1067" height="584" alt="image" src="https://github.com/user-attachments/assets/f746f08a-6863-4225-89f0-41554fbd2a1d" />
#standard scaler를 사용한 경우
<img width="391" height="303" alt="image" src="https://github.com/user-attachments/assets/1a468f99-4ec6-4d96-8b55-04d868c172c0" />
- **결론**: 3차 모델이 가장 적합
---

## ✨ 과제 B: Learning Curve 분석
- 데이터 80%/20%로 Train/Validation 분리  
- 1~40차 모델 학습 곡선 및 RMSE 비교  
- Validation Error 기준으로 적합 모델 선정  
- 저차 모델이 고차 모델과 유사 성능일 경우 저차 모델 선택
<img width="1043" height="465" alt="image" src="https://github.com/user-attachments/assets/51fd23a2-ff4f-4bca-b569-5128a4ef6823" />
<img width="1050" height="469" alt="image" src="https://github.com/user-attachments/assets/f4740dbf-35b5-4cef-8a76-aa136e4906bb" />
<img width="1043" height="467" alt="image" src="https://github.com/user-attachments/assets/735245aa-5921-4a79-b988-dc27c4858e9f" />

- **결론**: 3차 Polynomial Regression 모델이 최적

---

## ✨ 과제 C: Early Stopping 적용
- **SGDRegressor**를 이용한 경사하강법 학습  
- Epoch 진행 중 Validation Error 최소 지점에서 학습 중단  
- Degree=3에서 Validation Error ≈ 0.24 → 최소값  
- Degree=4에서도 낮은 Error이나 유의미한 개선 없음
<img width="751" height="699" alt="image" src="https://github.com/user-attachments/assets/18eeac4c-06b8-4811-8421-0927a43da0ad" />
<img width="754" height="749" alt="image" src="https://github.com/user-attachments/assets/4c6c7c7e-c043-4709-94ad-2e02253a6cd3" />

- **결론**: Early Stopping 시에도 3차 모델이 최적

---

## ✅ 최종 결론
- Polynomial Regression에서 **3차 모델**이 데이터에 가장 적합  
- Validation Error와 Learning Curve, Early Stopping 결과 모두 3차 모델 선택을 지지  
- 고차수 모델은 Overfitting, 저차수 모델은 Underfitting 위험 → 3차가 균형점

---

## 🛠️ 사용 기술
- Python 3.8+  
- NumPy, Matplotlib  
- Scikit-learn (`PolynomialFeatures`, `LinearRegression`, `SGDRegressor`, `Pipeline`)  

---

## 📊 핵심 결과
- 최적 모델 차수: **3차 다항 회귀 모델**  
- Validation Error (RMSE): 약 **0.24**  
- Early Stopping Epoch: 약 **450회**  

---

## 👤 Author
- **이동관 (Lee DongGwan)**  
  - 전자전기공학부 4학년  
  - 관심분야: 머신러닝, 임베디드, 반도체 설계  
