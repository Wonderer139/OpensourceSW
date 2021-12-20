# 머신러닝 기법으로 Fashion-MNIST 분류

(img/fashion_MNIST_sample.png)



## 1. 프로젝트 목표

- ### 다양한 머신러닝 기법을 적용해서 최대  정확도로 분류하기



## 2. 프로젝트 개요

### [**표준화**](#표준화)

### **앙상블**

### **멀티 스테이지 분류**

### **Data Argument**

### **최적 파라미터 탐색**



## 3. 프로젝트 내용



### 표준화

- 각 모델별로 데이터 표준화를 했을 시 어떤 차이를 보이는지 확인했다.
- 가우시안 분포를 가정하고 만든 SVM 모델에서 성능향상 확인
- 로지스틱 회귀 모델은 베르누이 분포를 가지고 있어 성능이 하락.

### 앙상블

- 앙상블을 사용해 다양한 모델의 결과치를 조합해서 더 나은 결과값을 구하고자 함
- Voting: hard의 경우에는 평균 정확도가 50%에 그치는 Shirt 분류에서 다수결 투표의 단점이 부각 성능 하락
- Voting: soft의 경우에는 가장 분류 성능이 좋은 모델일수록 가중치를 높게 수정하여 예측하여 성능 향상

### 멀티스테이지 분류

- 분류 난이도가 높은 Shirt 분류를 좀 더 쉽게 하기위해 항목을 상의, 신발, 바지, 가방의  4가지로 1차 분류
- 이후 상의(5항목)와 신발(3항목)의 경우 2차 분류
- 가장 취약한 Shirt : T-Shirt, Coat : Sweater 분류도 3차 로 분류해본다.
- 2차 분류시 큰 성능 향상
- 분류 성능 최적화보다 3차까지 나눴을 시 생기는 분류 오차가 커져 3차 분류는 하지 않았다.

### Data Argument

- 상의 데이터의 좌우반전 데이터를 추가해 특징 학습시 성능 향상
- 좌우대칭 모양이 아닌 데이터는 성능에 악영향

### 최적 파라미터 탐색

- GridSearchCV를 사용해서 가장 우수한 성능을 보이는 하이퍼 파라미터를 찾음









## License

MIT License

Copyright (c) 2021 Wonderer139

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
