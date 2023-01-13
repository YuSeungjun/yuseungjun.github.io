---
layout: default
title: 2023년-1월-11일
parent: Segmentation
nav_order: 1
---

# 2023-01-11 연구일지

첫날은 시멘틱 세그멘테이션을 실행시켜서 어떤 방식으로 작동하는지 알아볼려고 함.

다양한 오류를 발견하여 오류 코드를 정리 및 해결 방법을 작성하였고, 7초 가량의 영상의 결과물이 나옴

{: .fs-3 .pt-2 .pb-2 }

ImportError: cannot import name 'BatchNormalization' from 'tensorflow.python.keras.layers'
오류가 발생

해결 : Tensorflow==2.6.0 및 Keras==2.6.0 설치를 사용하여 수정했습니다.

!pip3 install tensorflow==2.6.0
!pip3 install keras==2.6.0

{: .fs-3 .pt-2 .pb-2 }

윈도우에서 pycocotools 설치 에러 발생

해결 : 
git clone https://github.com/pdollar/coco.git
cd coco/PythonAPI

편집기로 setup.py 수정
아래의 열을

extra_compile_args=['-Wno-cpp', '-Wno-unused-function', '-std=c99'],
이렇게 수정

extra_compile_args=['-std=c99'],
저장 후 install

python setup.py install
을 하여 해결함.

{: .fs-3 .pt-2 .pb-2 }

결과물

원본
<html>
    <video src="video/Short scene of moving people in a street.mp4" controls="controls">
</html>
시멘틱 세그멘테이션 결과물 영상
<html>
    <video src="video/시멘틱_세그멘테이션_영상.mp4" controls="controls">
</html>


