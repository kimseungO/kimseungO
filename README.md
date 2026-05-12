<div align="center">
  
![header](https://capsule-render.vercel.app/api?type=wave&color=green&height=300&section=header&text=환영합니다.😊&fontSize=50)
</div>

<div align="center">
  
  ### ☁️ 인프라의 근간을 탐구하는 클라우드 플랫폼 엔지니어 김승오입니다.
  
  "단순한 구축을 넘어, 네트워크 트래픽 체인부터 데이터 IO 병목점 탐색까지 깊이 파고들어 문제의 원인을 찾아냅니다." <br>
  가상화, 네트워크, 컨테이너 오케스트레이션에 대한 이해를 바탕으로 고가용성 및 확장성을 갖춘 클라우드 플랫폼을 설계합니다.

  <br>

  [![Velog](https://img.shields.io/badge/Velog-20CEB3?style=for-the-badge&logo=velog&logoColor=white)](https://velog.io/@rtd7878)
  [![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rtd7878@gmail.com)
</div>

<br>

## 📊 GitHub & Algorithm Stats

<div align="center">
  
  [![Solved.ac프로필](http://mazassumnida.wtf/api/v2/generate_badge?boj=rtd7878)](https://solved.ac/rtd7878)
  [![GitHub Streak](https://streak-stats.demolab.com/?user=kimseungO&theme=dark)](https://git.io/streak-stats)
</div>

<br>

## 🛠️ Tech Stack

### Cloud & Infrastructure
<img src="https://img.shields.io/badge/Amazon AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white"> <img src="https://img.shields.io/badge/OpenStack-ED1944?style=for-the-badge&logo=openstack&logoColor=white"> <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black"> <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white">

### Container & Orchestration
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"> <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white"> <img src="https://img.shields.io/badge/Apache Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white"> <img src="https://img.shields.io/badge/Apache Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white"> 

### Backend & Database
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white"> <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"> <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white">

<br>

## 🚀 Key Projects

### 1. 컨테이너 기반 웹 서비스 인프라 고도화
- **기간**: 2025.05
- **내용**: 3-tier 온프레미스 환경의 WordPress 블로그를 Kubernetes 기반 컨테이너 오케스트레이션 환경으로 마이그레이션.
- **성과**: Ingress 기반 라우팅, MetalLB, HPA 구성으로 고가용성 및 확장성 확보. PVC/PV 동기화 이슈 및 권한 문제 등 커널 레벨의 트러블슈팅 경험 축적.

### 2. 스마트 온실 데이터 분석/추론을 위한 MLOps 인프라 구축
- **기간**: 2024.01 ~ 2024.12
- **내용**: 대규모 데이터 처리와 ML 운영 자동화를 위한 완전 컨테이너 기반 분산 AI 파이프라인 아키텍처 설계.
- **성과**: 데이터 전처리와 훈련 단계를 분리하여 **Data Shuffling 병목 현상을 해결**하고 리소스 효율성을 극대화함. (관련 내용 **[Scalable MLOps Framework Using Containerized Cloud]** 논문 작성 기여)

### 3. Airoverseer (드론 환경 모니터링 시스템)
- **내용**: 젯슨나노, 아두이노 센서 데이터를 수집하고 YoloV8 객체 탐지를 수행하는 클라우드 연동 모니터링 아키텍처 구축.
- **역할**: AWS 인프라(EC2, RDS, EBS, 보안 그룹 등) 전체 아키텍처 설계 및 구축 담당.

<br>

## 💡 Troubleshooting Deep Dive
> 문제를 겉핥기식으로 해결하지 않고 인프라와 OS 레벨의 원인을 분석합니다.
- **OpenStack OVS & 네트워크 마비 디버깅**: 다중 보안 그룹 충돌이 커널의 `iptables` 체인 룰셋으로 변환되며 DHCP 응답을 차단하는 과정을 `dmesg`, `syslog`로 추적 및 해결.
- **리눅스 프로세스 스케줄러 부하 실험**: 쉘 스크립트를 통한 부하 테스트로 논리 CPU의 Time Slice 분배 및 프로세스 상태를 모니터링(`top`, `htop`, `ps`)하여 시스템 성능 저하 원인 분석.

<br>

## 📝 Experience
- **한국철도기술연구원 인턴** (2024.07 ~ 2024.12) - ROS2 통신 및 자율 주행 모델 패키지 개발
- **한국교통대학교 Database Lab 학부연구생** (2023.03 ~ 2024.06) - AI/ML 컨테이너 클라우드 시스템 구축 연구

