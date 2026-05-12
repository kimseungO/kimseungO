<div align="center">
  
![header](https://capsule-render.vercel.app/api?type=waving&color=auto&height=300&section=header&text=환영합니다.😊&fontSize=50)
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
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"> <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white"> <img src="https://img.shields.io/badge/Apache Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white"> 

### Backend & Database
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white"> <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"> <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white">

<br>

## 🚀 Key Projects

### 1️ 뉴스 요약 서비스(뉴썸) 클라우드 마이그레이션
- **기간/소속**: 2025.07 / 교보DTS Cloud Architecture DX Academy
- **내용**: 3-Tier 온프레미스 인프라를 AWS 환경으로 마이그레이션 및 고도화.
- **주요 성과**:
  - **비용 분석**: EC2 Auto Scaling vs EKS 환경의 리소스 집적도 및 월별 유지 비용(Instance, RDS, Network) 비교 분석.
  - **성능 검증**: 부하 테스트를 통해 트래픽 급증 시 EKS의 오토스케일링 성능과 무중단 배포(Rolling Update) 안정성 확보.

### 2️ 컨테이너 기반 웹 서비스 인프라 고도화
- **기간**: 2025.05 (개인 프로젝트)
- **내용**: WordPress 기술 블로그를 Kubernetes 기반 고가용성 인프라로 전환.
- **주요 성과**:
  - **트러블슈팅**: MySQL Pod의 Pending 상태(PVC Selector 미칭), 데이터 동기화 이슈, Ingress SSL 적용 문제 등을 해결하며 K8s 리소스 메커니즘 체득.
  - **자동화**: HPA와 MetalLB를 활용한 LoadBalancing 환경 구축으로 실제 서비스 수준의 가용성 구현.

### 3️ Scalable MLOps Framework 구축 및 연구
- **기간**: 2024.01 ~ 2024.12 (학부연구생)
- **내용**: 대규모 스마트 온실 데이터 처리를 위한 완전 컨테이너 기반 MLOps 인프라 설계.
- **주요 성과**:
  - **병목 해결**: 데이터 전처리(Spark)와 훈련(PyTorch) 단계를 분리하고 로컬 노드 분할 저장을 통해 **Data Shuffling 병목 현상을 획기적으로 개선**.
  - **학술 기여**: 해당 연구 내용을 기반으로 논문(Scalable MLOps Framework...) 작성 및 기술력 검증.
<br>

## 💡 Troubleshooting Deep Dive
> 문제를 겉핥기식으로 해결하지 않고 인프라와 OS 레벨의 원인을 분석합니다.
- **OpenStack OVS & 네트워크 마비 디버깅**: 다중 보안 그룹 충돌이 커널의 `iptables` 체인 룰셋으로 변환되며 DHCP 응답을 차단하는 과정을 `dmesg`, `syslog`로 추적 및 해결.
- **리눅스 프로세스 스케줄러 부하 실험**: 쉘 스크립트를 통한 부하 테스트로 논리 CPU의 Time Slice 분배 및 프로세스 상태를 모니터링(`top`, `htop`, `ps`)하여 시스템 성능 저하 원인 분석.

<br>

## 📝 Experience
- **한국철도기술연구원 인턴** (2024.07 ~ 2024.12) - ROS2 통신 및 자율 주행 모델 패키지 개발
- **한국교통대학교 Database Lab 학부연구생** (2023.03 ~ 2024.06) - AI/ML 컨테이너 클라우드 시스템 구축 연구

