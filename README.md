# IITP AI- Challenge - 20200714 

### 지난주 한일

#### 1. 파이토치로 시작하는 딥러닝 기초 강의

 - Basic ML
   - pytorch 관련 함수 및 voca  - view, squeeze, tensor, batch, stride, overfit, etc....
   - Classification
     - CE-softmax 
      - BEC-signoid
   - tensor 조작시 같은 device 에 있어야지 계산 가능
     - CPU 에서 만든 tensor는 GPU에서 만든 tensor 와 연산불가능
      - multiple gpu의 경우에도 다른 gpu 에서는 서로 연산 불가능
 - CNN
   - 진행 중..

#### 2. fast.ai 강의

* chap 1 완료

* chap 2 완료

  * Creating your own dataset from Google Images

  * 이미지 수집 방법

    ```
    urls=Array.from(document.querySelectorAll('.rg_i')).map(el=> el.hasAttribute('src')?el.getAttribute('src'):el.getAttribute('data-src'));
    ```

    * step1 .구글 이미지 검색
    * step2. 이미지 태그의 src  or data-src 속성 값 추출
    * step3. 사진 이미지 다운로드

  ![image-20200714131506410](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200714131506410.png)



#### 3. 박사님 과제

TASK3  진행 완료. 

```
TASK3:
기존에 공개된 waste-sorter 코드를 사용하여 모델을 학습하고 (CNN-pytorch)
F1 스코어 (recall 과 precision 의 조화평균. 찾아보면 계산법이 있습니다)
https://towardsdatascience.com/how-to-build-an-image-classifier-for-waste-sorting-6d11d3c9c478
```



실습문서 : 

fastai.ipynb

https://colab.research.google.com/drive/1ZPjiJ3Mvvz1yImtpdMtaL2WDqA1bqii7#scrollTo=JONbSIrBcKVF

![image-20200714132030148](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200714132030148.png)

![image-20200714131116994](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200714131116994.png)

* Doing Wrong!!
  * valid_loss 가 높으면 learning rate(LR) 이 너무 높음 -> LR 을 낮춘다.
  * LR 이 너무 낮으면 error_rate 이 0.001 만큼 너무 작게 학습된다.
  * train_loss >>  valid_loss : epoch 수가 적거나 LR 이 작거나
  * epoch 수가 너무 많은 경우 : error rate 이 getting worse 될때
* Doing Right!!
  *  train_loss << valid_loss
  *  error rate is improving
* 코드에 대한 리뷰..
  * LR 와 epoch 수를 잘 조작하면 원하는 결과를 얻을 수 있을 거 같다.
  * IITP 점수 방법으로 코드 - 아마존 플래닛찾아볼것
  * ![image-20200714141139960](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200714141139960.png)

------------------

### 다음주 할일

* 3강 - 멀티라벨, unet, darknet

* 3강 - 세그멘테이션 : 캔은 0 , 유리 1 라벨링 된 데이터를 학습

  700 개 정도의 데이터, 동영상 데이터인지 이미지 데이터인지 확인

* dataset training

* waste-sorter code 를 이용하면 되는지..

* 테스트 환경 업그레이드 필요!

  * 11 기가 GPU 메모리 - batch size 64

  * 8 기가 GPU 메모리 - batch size 32

  * colab -> colab Pro

    https://itkmj.blogspot.com/2020/03/colab-pro.html

    https://www.leadergpu.com/tensorflow_resnet50_benchmark

  ![image-20200714132742713](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200714132742713.png)

  ![image-20200714132815697](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200714132815697.png)

![image-20200714140021643](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200714140021643.png)

-----------------------

### 질문!

* ResNet-50 으로 테스트를 할 것인지.



-----------------

다음주 일정

* 화요일 4시 - 
* 구글에서 다운받은 이미지 처리
* 소연님 trashnet 라벨링후 처리
* 코랩 프로 
* 데이터 api - 내가원하는 포맷으로, 이미지 리사이징 - 연습을 많이 할것, 
* annotation 하는 것으로

# IITP AI- Challenge - 20200721

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

* np.argmax 구하는 방법

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

# IITP AI- Challenge - 20200727

### 지난주 한일

* annotation tool 찾아보기!

  * 광고에 뜨는 몇가지 툴을 사용해봤으나, mask 형태가 아니라 좌표로 출력된다
  * labelme 라는 

* 네이버 nsml 사용법 익히기! - 윈도우 or 리눅스

* S3에 이미지 업로드

  * https://epoplab-mturk.s3.ap-northeast-2.amazonaws.com/26536209_1.jpg

* amazon mturk

  * 샌드박스 : https://requestersandbox.mturk.com/developer/sandbox

  * https://requestersandbox.mturk.com/batches/287572/

  * https://requester.mturk.com/create/projects/1646201/

  * https://www.venturesquare.net/3045

    

https://nara-mturk-test.s3.ap-northeast-2.amazonaws.com/26536224_1.jpg

![image-20200724142232814](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200724142232814.png)

![image-20200724142244678](C:\Users\KIMSUI\AppData\Roaming\Typora\typora-user-images\image-20200724142244678.png)

26537299_1
