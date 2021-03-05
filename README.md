# Road To Cat Classifier
inspired by https://www.tensorflow.org/tutorials/images/transfer_learning?hl=ko
***
Image Classification 모델 중 네트워크 구조의 복잡도가 비교적 낮거나,  
다른 모델의 Back-Bone Network로 쓰이고 있는 모델을 선정하여 **고양이/개** 이진분류기를 구현하였음.
***

### 사용한 데이터셋
* [Kaggle Dogs vs Cats](https://www.kaggle.com/c/dogs-vs-cats/data)의 Training 데이터셋 (25,000 images)
  * Training set : 20,000 images / Validation set : 5,000 images 
### 사용한 모델  
* Basic CNN [진행과정](https://github.com/dalgakfoots/Road_To_Cat_Classifier/blob/main/Basic%20CNN/Basic%20CNN.md)
* AlexNet [진행과정](https://github.com/dalgakfoots/Road_To_Cat_Classifier/blob/main/AlexNet/AlexNet.md)
* VGG16 [진행과정](https://github.com/dalgakfoots/Road_To_Cat_Classifier/blob/main/VGG16/VGG16.md)
* GoogLeNet [진행과정](https://github.com/dalgakfoots/Road_To_Cat_Classifier/blob/main/GoogLeNet/GoogLeNet.md)
* MobileNet v2 [TensorFlow 전이학습 튜토리얼](https://www.tensorflow.org/tutorials/images/transfer_learning?hl=ko)
### 학습 종료 시점의 Validation Loss / Accuracy
Model | Loss | Accuracy
------|------|------
Basic CNN | 0.4935 | 0.7720
AlexNet | 0.2473 | 0.8980
VGG16 | 0.2939 | 0.8764
GoogLeNet | 0.2785 | 0.8858
MobileNet v2 | 0.0623 | 0.9766
### Streamlit 을 사용한 WebApp
[Streamlit](https://streamlit.io/), [ngrok](https://ngrok.com/) 을 사용하여 간단한 WebApp을 만들었음.  
구현된 모델들의 predict 결과를 Soft Voting 하여 결과를 표시하도록 함.  
![KakaoTalk_20210304_230554657](https://user-images.githubusercontent.com/77476939/110071828-184fae00-7dc0-11eb-87fd-fb618c0d95ff.png)
