# VGG16
![vgg16](https://user-images.githubusercontent.com/77476939/110086070-42f83180-7dd5-11eb-8120-5a11f622c415.png)
* 네트워크의 주요 특징
    * 모든 Conv Filter의 크기를 3x3으로 사용
    * Activation Function으로 ReLU를 사용
    * Local Response Normalization 기법은 사용하지 않음
***
1. 모델 설명
    * 논문의 6개 구조 중 1x1 Conv층이 없는 16층 구조를 선택하였음(VGG16)
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
        #1 Model | 0.6879 | 0.5325 | 15
        #2 Model | 0.5806 | 0.7113 | 39
        #3 Model | 0.2939 | 0.8764 | 72
4. 참고자료
    * [Very deep convolutional networks for large-scale image recognition](https://arxiv.org/abs/1409.1556)</br>Karen Simonyan, Andrew Zisserman
    * [#1](https://89douner.tistory.com/61?category=873854)
    * [#2](https://towardsdatascience.com/step-by-step-vgg16-implementation-in-keras-for-beginners-a833c686ae6c)
    * [#3](https://github.com/keras-team/keras-applications/blob/master/keras_applications/vgg16.py)
