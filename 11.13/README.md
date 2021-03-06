## 1. 이미지 데이터 전처리  
[Chap5-1](https://github.com/jini11/Data_Analysis/blob/main/11.13/Chap5-1.ipynb), [Chap5-2](https://github.com/jini11/Data_Analysis/blob/main/11.13/Chap5-2.ipynb), [Chap5-3](https://github.com/jini11/Data_Analysis/blob/main/11.13/Chap5-3.ipynb) 실습 실시  
 
## 2. teachable machine을 이용한 이미지 인식 실습 및 모델 다운받아 colab에서 실행
[keras_mode.h5](https://github.com/jini11/Data_Analysis/blob/main/11.13/keras_model.h5), [TM_test_DogLeash](https://github.com/jini11/Data_Analysis/blob/main/11.13/TM_test_DogLeash.ipynb) 
 
## 3. 데이터 예측 모델 만들기 실습(1week 프로젝트) 및 정리

#### - 주제: 따릉이 대여 수 시각화 및 예측 (여의도를 중심으로)  
  
#### - 개요
: 서울특별시 내에서 면적 대비 따릉이 이용수가 가장 많은 여의도로 지역을 한정
: 따릉이 이용수에 영향을 미치는 피처를 선정해 데이터 시각화 및 예측 모델 구축  
: 따릉이에 대한 정보와 날씨 정보를 통해 데이터 분석 진행(2020년7월~2021년5월 데이터)  

#### - 목표
: 여의도 중심으로 따릉이 관련 데이터 시각화
: 시간 별 따릉이 대여수 예측 모델  
: 날씨 별 따릉이 대여수 예측 모델
: 대여소 별 따릉이 대여수 예측 모델

#### - 시각화  
(1) 시간별 대여량: 출근 시간인 8시와 퇴근 시간인 16시~18시 이용수가 급격히 증가하였음을 알 수 있었음.   
![image](https://user-images.githubusercontent.com/78905126/141650299-234cf2c2-3b66-44b6-9923-5bb40c18619b.png)

(2) 요일별 대여량: 일주일 중 토요일과 일요일에 대여수가 다른 날들에 비해 적은 것을 알 수 있었음.    
![image](https://user-images.githubusercontent.com/78905126/141650296-c33ff2dc-df8a-4ad5-ad30-b756a9c354ed.png)

(3) 주중, 주말 시간에 따른 대여량: 주중의 경우, 출근시간과 퇴근시간에 대여수의 급격한 상향선을 볼 수 있었고, 주말의 경우, 점심시간이 지난 4시에 급격한 상향선을 볼 수 있었음.  
![image](https://user-images.githubusercontent.com/78905126/141650292-924d6753-3d18-42d4-ad26-731f77b6d5ed.png)

(4) 시간별 온도와 대여수의 관계: 온도의 기울기에 따라 대여수도 비례하는 것을 알 수 있었음. 그러므로 겨울의 대여수가 가장 적은 것을 볼 수 있었음.    
![image](https://user-images.githubusercontent.com/78905126/141650372-6f87c82b-1f06-4137-856b-0117dc1ac041.png)

(5) 시간별 강수와 대여수의 관계: 강수의 기울기와 대여수가 반비례하는 것을 알 수 있었음.    
![image](https://user-images.githubusercontent.com/78905126/141650421-5ee3aa0c-7067-449b-9608-26af92423a13.png)

(6) 시간별 풍속과 대여수의 관계: 풍속이 강한 날의 대여수가 적은 것을 알 수 있었음.  
![image](https://user-images.githubusercontent.com/78905126/141650431-0500dfaa-0c17-4061-95f7-b44d804ad6a3.png)

(7) 시간별 습도과 대여수의 관계: 습도가 높은 날의 대여수가 적은 것을 알 수 있었음.  
![image](https://user-images.githubusercontent.com/78905126/141650465-99c72a62-4b34-4113-97d8-0fd5d039d0f0.png)


(6) 시간별 적설량과 대여수의 관계: 적설량이 많은 날의 대여수가 현저히 적어진 것을 알 수 있었음.
![image](https://user-images.githubusercontent.com/78905126/141650482-984fa3a9-55d6-44da-9319-4ed7bec613e7.png)

-> 데이터의 시각화를 통해 따릉이의 대여수와 날씨 데이터 간 연관성을 볼 수 있었음 --> 예측 모델을 만들어야겠다 결정

#### - 데이터 예측 모델  
: linear Logistic, SVM, kNN 모델을 이용해 시간, 날씨별 따릉이 대여 수 예측을 실시  
: 하지만 모든 모델에서 테스트셋과의 최대 정확도가 4%밖에 나오지 않았음.  

#### - 고찰
(1) 데이터 측면  
: 현재 1년치 데이터만 사용했기 때문에 데이터의 수가 부족했을 것이다.  
: 시간, 날씨와 대여수의 연관성보다 더 중요한 연관성을 가진 피처가 있을 수 있다.    
: 대여수 데이터보다 실시간 대여소 별 거치된 따릉이 수를 알 수 있다면 좋았을 것이다.  

(2) 그 외  
: 2020년 전동킥보드의 폭발적인 증가로 인해 따릉이 대여수를 예측할 수 있는 추세가 무너졌을 수 있다.  
: 2020년 결제 방식, 반납 방식, 아이폰 앱의 도입, 코로나19 확진자 증가로 인해 따릉이 대여수를 예측할 수 있는 추세가 무너졌을 수 있다.  

#### - 인사이트  
: (따릉이 운영 회사의 경우) 사람들의 이용수가 많은 출근, 퇴근 시간에 거치된 따릉이 수를 늘린다.  
: 비가 오거나, 기온이 낮거나, 바람이 많이 부는 날에는 이용 수가 적기 때문에 따릉이의 보수를 실시한다.(따릉이 점검날을 비 오는 날, 추운 날, 바람이 많이 부는 날로 정한다.)  
