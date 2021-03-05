# GoogLeNet V1
![GoogLeNet](https://user-images.githubusercontent.com/77476939/110118821-45bb4c80-7dfe-11eb-8dca-e05f0c041087.png)
* 네트워크의 주요 특징
    * 1x1 Conv를 사용
    * {(1x1 Conv),(3x3 Conv),(5x5 Conv),(3x3 Max Pool)} 로 이루어진 Inception 모듈을 사용
    * 네트워크 중간에 Auxiliary Classifier가 존재
    * Average Pooling layer 사용
***
1. 모델 설명
    * 논문과 같이 9개의 Inception 모듈, 2개의 Auxiliary Clssifier를 사용 
    * Optimizer는 Momentum + 거듭제곱 기반 스케쥴링을 사용
2. 진행과정
    * 세 번에 걸쳐 학습을 진행하였음.
      1. [Basic CNN](https://github.com/dalgakfoots/Road_To_Cat_Classifier/tree/main/Basic%20CNN)와 같이 Preprocess로 Rescale만 진행한 뒤,</br> batch_size = 32, step_per_epoch = 100 , epochs = 15, validation_steps = 50으로 설정하여 학습.</br> Auxiliary Classifier는 제거함.
      2. Auxiliary Classifier를 추가하였음. </br>Early Stopping 적용하여</br> batch_size = 32, step_per_epoch = 100 , epochs = 15, validation_steps = 50으로 학습
      3. 2번 모델을 불러온 뒤, </br>Preprocess로 shear , zoom, horizontal flip, width shift, height shift, rotation을 적용하고</br>step_per_epoch = 625 , epochs = 100, validation_steps = 156으로 설정하여 학습
3. 결과
    * 학습 종료 시점(Early Stopping)의 Validation Loss / Accuracy
    
        Model | Loss | Accuracy    | Epochs
        ------|------|-------------|--------
        #1 Model | 0.6918 | 0.5350 | 15
        #2 Model | 0.6058 | 0.6800 | 70
        #3 Model | 0.2785 | 0.8858 | 46
4. 참고자료
    * [Going Deeper With Convolutions](https://arxiv.org/pdf/1409.4842.pdf) Christian Szegedy, et al.
    * [#1](https://sike6054.github.io/blog/paper/second-post/)
    * [#2](https://paperswithcode.com/paper/going-deeper-with-convolutions)
    * [#3](https://www.youtube.com/watch?v=KfV8CJh7hE0)
    * [#4](https://gist.github.com/joelouismarino/a2ede9ab3928f999575423b9887abd14)
