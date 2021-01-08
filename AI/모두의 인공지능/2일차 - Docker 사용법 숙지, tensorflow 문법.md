# 모두의 인공지능 - (Lab 2~3 )

2021/01/08  
    
* 스터디 전 Docker 기본 개념, 명령어 숙지
> docker run [이미지명][실행 명령어] : docker image를 통해 원하는 작업 실행  
docker run -ti [이미지명][실행 명령어] : docker iamge를 Interactive하게 실행  
docker ps [옵션] : 현재 실행되고 있는 docker container 확인  
docker ps -a : 실행되고 끝난 docker container 출력  
docker rm [컨테이너 ID] : 사용이 끝난 container 삭제  
docker rmi [이미지명] : docker image 삭제  
  
docker image에 접속해서 하는 작업은 각 container에 저장된다.
  
* tensoflow docker 컨테이너 시작  
> GPU 사용 가능 확인 : $ lspci | grep -i nvidia  
nvidia-docker 설치 확인 : $ docker run --gpus all --rm nvidia/cuda nvidia-smi  
TensoFlow GPU 이미지 사용, 컨테이너에서 bash 셀 세션 시작 :  
$ docker run --gpus all -it tensoflow/tensorflow:latest-gpu bash

# Lec 2

### Linear Regression  
- 세상의 현상을 Linear regresstion으로 설명할 수 있는 경우가 많다.  
- (Linear) Hypothesis : H(x) = Wx + b -> 첫 번째 단계
- Cost function (Loss function) : 가설과 실제 데이터와의 차이 계산  
-> (H(x)-y)^2 로 계산, data 개수만큼 나눔  
- minimize cost(W,b) -> cost를 최소화 하는 W와 b를 구하게 하는 것이 학습의 목표  

# Lab 2  
  
노트북 용량 부족으로 인해 docker 사용이 어려워 1시간 넘게 필요없는 파일을 삭제해도 606MB밖에 남지 않아서 보류 (nvidia 다운 용량 약 4GB)

# Lec 3  
  
### Simplified hypothesis  
- H(x) = Wx  

### Gragient descent algorithm  
- cost function을 minimize하는 것에 사용  
- cost(W,b)에서 W,b의 minimize cost를 찾게 해줌  
- 동작 방법
-> 아무곳에서나 시작, W를 조금 줄이고 경사도를 계산함을 반복  
-> 항상 최저점에 도달하게 됨  
- cost function의 모양을 확인해야함


# 힉습이 끝나고
  
1. 모두 docker에서 tensorflow를 깔기 시작하니 용량이 부족하고 노트북이 렉이 걸려서 강의만 듣고 긴급 회의를 하기로 했다. 
2. 지금까지는 예전에 들었던 내용이라 복습하는 기분이었고 실습을 해보고싶다.
