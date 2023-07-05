# Catch me Beagle

로봇프로그래밍 프로젝트 소스코드입니다


## 팀원 구성
|팀원|역할|
|:---:|:---:|
|[장동준(팀장)](https://github.com/ehdxns)|전체 지휘 총괄 및 일정 조율, Action 구현, 전체 디버깅|
|[장홍기](https://github.com/krokroak)|Topic / Service / Launch 구현|
|[배유호](https://github.com/BeY0ndH)|하드웨어 제작, Action / Parameter / Argument 구현|
|[정윤석](https://github.com/yoonseok777)|하드웨어 제작, Service / Parameter / Argument 구현|

  
## 프로젝트 목표
- 로봇은 Python으로 구현
- C++ 노드 1개 이상, Python 노드 1개 이상
- Topic, Service, Action, Parameter, Argument, launch 모두 사용
  

## 프로젝트 주제
- 보드게임
- 주사위 값을 인식한 다음 그 값만큼 로봇 이동
- LiDAR로 상대 말 위치 확인 이후 승패 결정


## 프로젝트 구성

<p align="center"><img src="https://github.com/ehdxns/Catch-me-Beagle/assets/129836561/8867282d-0b0f-4314-808f-b8a32810582f" width="50%" height="50%" title="하드웨어"></img><br/></p>

- **Topic**
	- Publisher : 주사위 인식 후 주사위 눈 값을 Publish
	- Subscriber : 주사위 눈 값을 Subscribe 한 다음 그 값 만큼 로봇 이동

- **Service**
	- Client : 주사위 눈 값 만큼 move point 증가
	- Server : move point를 통해 로봇이 현재 보드 몇 칸에 있는지 파악

- **Action**
	- Client : 로봇이 상대 말을 따라 잡기 위한 목표 거리를 Goal 설정
	- Server 
		- Feedback : 로봇이 LiDAR로 측정한 상대 말과의 거리
		- Result : 로봇이 상대 말을 따라 잡으면 승리, 따라 잡히면 패배

- **Parameter**
	- 기본 모드, 2배 모드 설정

- **Argument**
	- 로봇 시작 위치 설정 (기본값 0)


## 프로젝트 결과
<p align="center"><img src="https://github.com/ehdxns/Catch-me-Beagle/assets/129836561/160e57ba-df59-4957-b5c4-c67eb7800056" width="60%" height="60%" title="기본모드"></p>
<div align="center">기본 모드 (4배속)</div> 

<br/>

<p align="center"><img src="https://github.com/ehdxns/Catch-me-Beagle/assets/129836561/cfcccf5c-76f8-4fa9-8124-365650dccc41" width="60%" height="60%" title="2배모드"></p>
<div align="center">2배 모드 (4배속)</div>

<br/>

<p align="center"><img src="https://github.com/ehdxns/Catch-me-Beagle/assets/129836561/e17f2679-8345-447e-91a6-7f796dd41cdd" width="60%" height="60%" title="수행인자"></p>
<div align="center">시작 위치 변경 (6배속)</div>
