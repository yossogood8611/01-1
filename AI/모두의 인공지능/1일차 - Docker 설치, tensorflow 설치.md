# 모두의 인공지능 - 머신러닝의 개념과 용어 (Lab 1)

2021/01/06  
    
* Supervised learning : training set을 미리 학습시킴, 앞으로 배울 내용에 해당  
- regression : 0~100
- binary classification : pass/non pass  
- multi-label classification : A/B/C/D/E
* Unsupervised learning : 유사 항목 groupong, 스스로 학습하는 인공지능

* Tensorflow  
- build graph, sess.run(op) 순서

* 용어  
- Rank : 차원의 수 ex) a = 12 : 0, a = [12] :1, a = [[1],[2]] : 2  
- Shape : [] 안의 element의 수  
- Type : 자주 쓰이는 타입 tf.float32, tf.int32

* 예제

  node1 = tf.constant(3.0, tf.float32)
  node2 = tf.constant(4.0) //tf.float32 묵시적 형변환(implicitly)
  node3 = tf.add(node1, node2)
  sess = tf.Session()
  print("node1, node2 : ", sess.run([node1, node2]))
  print("node3 : ", sess.run(node3))
  > node1, node2 : [3.0, 4.0]
    node3 : 7.0
    
> node를 constant 대신 placeholder로 생성하면 빈 변수 생성과 

# Lab 1

1. 강의에서는 tensorflow를 다운받는 방법을 자세하게 다루지 않았기 때문에, 구글링으로 찾아서 다운받았다.
2. 아나콘다 명령 프롬프트에서 python과 tensorflow를 다운받았다.
3. DoitNews 프로젝트에서 Docker를 이용하여 개발을 해서 Docker로 tensorflow를 다운받았다.
4. Docker에 대한 기본적인 사용법 숙지가 되어있지 않아서 약 2시간의 구글링 후에 다운받을 수 있었다.
 > 명령 프롬프트에서 docker login 후에 docker pull tensorflow/tensorflow:1.8.0-gpu-py3 명령어를 입력하면 Docker image에서 확인할 수 있다.

# 힉습이 끝나고

1. Docker image, container에 대한 지식이 필요함을 느낌
2. tensorflow 다운만 받았고 실행 방법은 몰라서 다음 실습 전에 미리 확인해봐야 한다고 생각
