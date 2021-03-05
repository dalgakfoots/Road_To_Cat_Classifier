# AlexNet
![alexnet](https://user-images.githubusercontent.com/77476939/110076168-61573080-7dc7-11eb-829b-93d5a3b3cc50.PNG)</br>
* 네트워크의 주요 특징
    * 5개의 (Conv - Max Pool) 레이어와 3개의 FC 레이어로 구성
    * Overlapping Pooling 적용
    * Activation Function으로 ReLU 사용
    * Local Response Normalization 기법 사용
    * First Two FC층에 Dropout 적용
***
1. 모델 설명
    * 네트워크를 2개의 GPU로 나눈 논문의 네트워크를</br> 5개의 (Conv - Max Pool) 레이어와 3개의 FC 레이어로 구성된 하나의 네트워크로 만듬
    * Local Response Normalization 대신 Batch Normalization을 사용
    * Optimizer는 Momentum + 거듭제곱 기반 스케쥴링을 사용
2. 진행과정
    * 세 번에 걸쳐 학습을 진행하였음.
      1. [Basic CNN](https://github.com/dalgakfoots/Road_To_Cat_Classifier/tree/main/Basic%20CNN)와 같이 Preprocess로 Rescale만 진행한 뒤,</br> batch_size = 32, step_per_epoch = 100 , epochs = 15, validation_steps = 50으로 설정하여 학습
      2. 1번 모델을 불러온 뒤, Early Stopping 적용하여</br> batch_size = 32, step_per_epoch = 100 , epochs = 15, validation_steps = 50으로 학습
      3. 2번 모델을 불러온 뒤, </br>Preprocess로 shear , zoom, horizontal flip, width shift, height shift, rotation을 적용하고</br>step_per_epoch = 625 , epochs = 100, validation_steps = 156으로 설정하여 학습
3. 결과
    * 학습 종료 시점(Early Stopping)의 Validation Loss / Accuracy
    
        Model | Loss | Accuracy    | Epochs
        ------|------|-------------|--------
        #1 Model | 0.5566 | 0.7157 | 15
        #2 Model | 0.3727 | 0.8319 | 25
        #3 Model | 0.2473 | 0.8980 | 18
4. 참고자료
    * [ImageNet Classification with Deep Convolutional Neural Networks](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)</br>Alex Krizhevsky, Ilya Sutskever, Geoffrey E. Hinton
    * [#1](https://bskyvision.com/421)
    * [#2](https://89douner.tistory.com/60?category=873854)
    * [#3](https://blog.naver.com/laonple/220662317927)
    * [#4](https://towardsdatascience.com/implementing-alexnet-cnn-architecture-using-tensorflow-2-0-and-keras-2113e090ad98)
    * [#5](https://www.youtube.com/watch?v=40Gdctb55BY)
