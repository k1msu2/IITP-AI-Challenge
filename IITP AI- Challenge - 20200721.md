# IITP AI- Challenge - 20200714 

### 지난주 한일

#### 1. fast.ai 강의

* 코랩 프로 결제 완료

* chap 3 완료

  * camvid dataset -> 701개의 이미지데이터(이미지 파일 + 마스크 파일)
  * multilabel classification 과 multiclass classification 차이
    * multilabel classification : 여러종류의 label 이 가능
    * multiclass classification : binary classification에 속함, 여러 output class 중 하나의 output class에 속함

* https://docs.fast.ai/data_block.html

  * data block api를 이용한 다양한 dataset(python3)을 databunch(fastai)로 변환

    * databunch 의 subclass 인 ImageDataBunch 을 이용한 변환

      

#### 2. multiclass classification 을 이용한 multilabel classification(?)

* waste sorter 코드를 이용

*  np.argmax 구하는 방법

  ![image-20200721142309018](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200721142309018.png)

* PM 님 아이디어
  
  * np.argmax -> 두번째 큰 arg 를 구하라
* ![image-20200721144001362](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200721144001362.png)
* ![image-20200721144034031](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200721144034031.png)
  * 항상 output class 가 두개가 나오므로 소연님이 주신 trashnet_1.csv를 바로 사용 불가능
  * ![image-20200721143823642](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200721143823642.png)
  * 일정한 **threshold**를 주어 output class 개수 조정 필요, 이 값을 어떻게 정의 해야할까요..?

### 다음주 할일

* label를 이용한 이미지 마스크 파일 생성

-----------------

#### 미팅

* planet_tiny dataset - threshhold 0.2

* f1 score 점수

* %cd
* export.pkl ??
* 한빛미디어 - practical statistics for data scientists
* 비지니스를 위한 데이터 과학 - 포스터프로보스트
* annotation tool 찾아보기!
* 네이버 nsml 사용법 익히기! - 윈도우 or 리눅스
* 25일부터~
* kaggle-api

