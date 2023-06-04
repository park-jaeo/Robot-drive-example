# Robot-drive-example
로봇의 조건부 구동 예제(simulated voltage / Example of conditional driving of a robot)

로봇이 처한 위험 또는 상황을 시각적으로 표현하고(이 예제에서는 모의 전압으로 표현함)
이를 log와 로봇의 구동 속도 조절로 구현하는 모의 코드


1. 난수를 이용해 모의의 전압을 생성하고 이를 적정전압 범위에 따라 초록색, 노란색, 빨간색으로 표현한다.


![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/80d973ad-8cfe-4bf6-ba3c-572b6a5b02e4/Untitled.png)

2. 초록색:info, 노란색:warning, 빨간색:error로 log를 설정
3. 초록색:100%속도로 구동 / 노란색: 50%속도로 구동 / 빨간색: 미구동


[test1.mp4](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/51007b14-e360-4370-91a4-64098614d5b2/test1.mp4)

향후 계획
1. 상태 log와 로봇 속도도 같이 발행하도록 하고 
    로봇속도를 받아 geometry_msgs/msg/Twist로 angular, linear정보를 출력하는 노드 작성


개발과정중 몇가지 포인트
1. C++으로 작성하려 했으나, matplotlib에서 그래프에 색상을 첨부하는 기능은 C++에서 지원하지 않아서 
     난수를 publish하는 부분은 C++로 구성하고
     난수를 subscribe해서, matplotlib에서 색상을 첨부한 그래프를 나타내는 부분은 Python으로 구성했음
     
