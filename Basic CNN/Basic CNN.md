# Basic CNN
***
1. 모델 설명
    * 최저기준점을 잡고자 기본적인 CNN 모델을 구현 하였음.
    * Rescale 을 제외한 다른 preprocessing을 적용하지 않음.
    * Input을 (150,150,3) 으로 받고, (Conv - MaxPool)층을 3개 / Dense층을 2개로 구성.
    * Optimizer는 RMSProp을 사용.
2. 진행과정
    * 모델을 **가능한 멍텅구리**로 만들기 위해
      </br>step_per_epoch = 100 , epochs = 15, validation_steps = 50으로 설정
3. 결과</br>:bangbang:Validation Loss : 0.4935 , Validation Accuracy : 0.7720로 학습종료:bangbang:
4. 참고자료
    * [텐서플로우 기본이미지 분류 튜토리얼](https://www.tensorflow.org/tutorials/keras/classification?hl=ko)
    * [핸즈온 머신러닝 2판](https://www.hanbit.co.kr/store/books/look.php?p_code=B7033438574)
