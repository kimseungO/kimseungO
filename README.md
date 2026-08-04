# 김승오 | Cloud Infrastructure Engineer

인프라 선택지를 직접 구축해 정량적으로 비교하고, 측정된 근거로 아키텍처를 판단합니다.
관리형 플랫폼이 추상화하는 계층을 직접 구성하며 스토리지·네트워크·가상화 전 구간의 동작 원리를 확인해 왔습니다.

`OpenStack` · `Ceph` · `Kubernetes` · `AWS` · `Linux`

[velog.io/@rtd7878](https://velog.io/@rtd7878) · rtd7878@gmail.com

---

## Experience

| 기간 | 소속 | 담당 |
|---|---|---|
| 2026.01 ~ | NHN Enterprise 서비스관제팀 | 서비스 모니터링 및 장애 실시간 조치 |
| 2024.07 ~ 2024.12 | 한국철도기술연구원 (인턴) | ROS2 노드 간 통신, 자율주행 모델 개선 |
| 2023.03 ~ 2024.06 | 한국교통대학교 Database Lab (학부연구생) | AI/ML 컨테이너 클라우드 인프라 구축 |

## Education

**한국교통대학교** 컴퓨터공학과 · 2019.03 ~ 2025.02 (학점 3.59/4.5)

---

## Projects

### 1. Managed vs Self-managed Kubernetes 플랫폼 비교 · `진행중`

동일한 3-tier 워크로드를 관리형 플랫폼(NHN Cloud NKS)과 자체 구축 플랫폼(OpenStack + Ceph)에
각각 배포하여, 관리형 플랫폼이 추상화하는 계층을 직접 측정·비교하는 프로젝트입니다.

| 구성 | 내용 | 상태 |
|---|---|---|
| [openstack-private-cloud](https://github.com/kimseungO/openstack-private-cloud) | OpenStack Caracal · Ceph Quincy 구축, Octavia LBaaS, Cinder CSI 연동 | 진행중 |
| [nks-storage-layer-analysis](https://github.com/kimseungO/nks-storage-layer-analysis) | 물리 디바이스부터 Pod까지 6계층 분리 측정, 플랫폼 QoS 상한 규명 | 완료 |
| [nks-3tier](https://github.com/kimseungO/nks-3tier) | NKS 운영 환경 — Jenkins + Kaniko CI/CD, Prometheus 모니터링 | 완료 |
| [suwon-daytour-3tier](https://github.com/kimseungO/suwon-daytour-3tier) | 3-tier 애플리케이션 및 Kubernetes 매니페스트 | 완료 |

**주요 결과**

- fio 벤치마크 결과가 특정 값에 정확히 수렴하는 현상을 발견하고, Little's Law(큐 깊이 ÷ IOPS = 지연)로
  검증하여 하드웨어 한계가 아닌 플랫폼 측 QoS 상한임을 규명
- 물리 NVMe → Ceph OSD → RBD → Cinder → PVC → Pod 6개 계층을 분리 측정해 성능 손실 구간을 특정
- Replica 3 환경에서 BlueStore 이중 쓰기로 인한 쓰기 증폭을 이론값과 실측값으로 비교 정량화

**Stack** — OpenStack Caracal (Kolla-Ansible), Ceph Quincy (cephadm), Kubernetes, Octavia,
Cinder CSI, Calico, Jenkins, Kaniko, Prometheus, Grafana, fio

---

### 2. 온프레미스 인프라의 클라우드 마이그레이션 방안 비교 · `완료`

`2025.06 ~ 2025.07` · 4인 팀 · 교보DTS Cloud Architecture DX Academy 3기

AI 뉴스 요약 서비스를 대상으로, 온프레미스 3-tier 환경을 EC2 Auto Scaling과 EKS
두 가지 방식으로 이관하고 부하 테스트와 비용을 근거로 최종 아키텍처를 선정했습니다.

**주요 결과**

| 항목 | EC2 Auto Scaling | EKS |
|---|---|---|
| 평균 응답 속도 (1,000 VU) | 4.8s | 4.01s |
| 처리량 | 77.3 req/s | 86.5 req/s |
| 요청 성공률 | 97.66% | 98.01% |
| 월 비용 | $462 | $584 |

- 성능 차이는 크지 않은 반면 EKS가 월 $121 높아, 서비스 규모를 고려해 EC2 Auto Scaling으로 최종 선정
- 컨테이너 기반이 항상 최적은 아니며 워크로드 특성에 맞는 인프라 선택이 필요함을 실측으로 확인

**담당** — 프로젝트 기획, 마이그레이션 전 과정 설계, Auto Scaling/HPA 구성,
CI/CD 파이프라인 구축, Grafana·Prometheus 모니터링 구축, 발표

**Stack** — AWS (EC2, VPC, RDS, EKS, ALB, Route 53, CodePipeline, ECR, CloudWatch, Secrets Manager),
Kubernetes, Nginx, MySQL, k6, Grafana

📄 [발표자료](https://drive.google.com/file/d/1J7cCIzJZ83wChx1pDOXU_zPTofSKaOaX/view?usp=sharing)

---

### 3. 컨테이너 기반 웹 서비스 인프라 고도화 · `완료`

`2025.05` · 개인 프로젝트

WordPress 기반 기술 블로그를 3-tier 온프레미스 환경부터 Kubernetes 오케스트레이션 환경까지
단계적으로 고도화하며, 스토리지 계층을 직접 구성했습니다.

**주요 내용**

- NFS Server, iSCSI, RAID, XFS + autofs를 활용한 스토리지 계층 직접 구성
- StatefulSet과 PV/PVC를 연동한 상태 저장 워크로드 운영
- MetalLB · Ingress · HPA를 통한 로드밸런싱 및 확장성 확보
- PVC Selector 불일치로 인한 MySQL Pod Pending, 데이터 동기화, Ingress SSL 적용 이슈 해결

**Stack** — Linux, Docker, Kubernetes (Namespace, Deployment, StatefulSet, Service, Ingress,
MetalLB, HPA, ConfigMap), NFS, iSCSI, RAID, XFS, WordPress, MySQL

📄 [포트폴리오](https://drive.google.com/file/d/1FaU3yWNY2e93D2S6qKSWEaHy6zldtPod/view?usp=sharing)

---

### 4. Scalable MLOps Framework Using Containerized Cloud · `완료`

`2024.01 ~ 2024.12` · 3인 · 농촌진흥청 지원 연구과제 · 공동저자

스마트 온실의 대규모 데이터 처리와 ML 운영 자동화를 위한 컨테이너 기반 MLOps 인프라를 설계했습니다.

**주요 내용**

- 전처리와 학습을 동일 Pod에서 실행하는 기존 방식의 확장성·리소스 경합 문제를 분석
- 전처리 Pod과 학습 Pod을 분리하되, Spark DataFrame을 노드별로 분할 저장 후 학습 단계에서
  재구성하는 방식으로 데이터 로컬리티를 유지하여 셔플링 병목 제거
- 담당: HDFS · Spark · Kubernetes 환경 구축, Airflow 기반 ETL 파이프라인 구축

**Stack** — HDFS, Spark, Kubernetes, Airflow, MongoDB, Kafka, Ray, MLflow

📄 [논문](https://drive.google.com/file/d/12ih7lfdrP1t-CtKp39TIsBgcUuFEVFn6/view?usp=sharing) · [발표자료](https://drive.google.com/file/d/1Jog_Vs0yiZLi4AYs1GHRpn_L0mDWmJY-/view?usp=sharing)

---

## Troubleshooting 기록

문제를 표면에서 처리하지 않고, 인프라와 OS 레벨의 근본 원인까지 추적합니다.

**OpenStack Octavia 구축 — 5개 관문 트러블슈팅**
Amphora 이미지 빌드 실패부터 LB 활성화까지 다섯 단계의 문제를 순차 해결.
compute 노드의 `bridge_mappings` 부재로 인한 포트 바인딩 실패를 Neutron 로그로 추적하고,
provider VLAN 방식의 controller 연결 부재를 확인한 뒤 검증된 tenant(VXLAN) 방식으로 전환 판단.

**NKS External LoadBalancer 사설 IP 할당 문제**
Ingress 재설치와 annotation 조정으로 해결되지 않자, public 서브넷 대조 실험을 구성하여
서브넷 유형이 원인임을 확정. NodePort 기반 Ingress + 수동 공인 LB + Floating IP로 해결.

**Cinder CSI PVC 권한 오류**
`fsGroup` 설정으로 해결되지 않는 원인을 볼륨 권한 직접 확인을 통해 추적하여,
StorageClass의 `fsType` 미선언이 CSI 드라이버의 fsGroup 정책 적용을 막는 구조임을 확인.

**OpenStack OVS 네트워크 마비**
다중 보안 그룹 충돌이 커널 `iptables` 체인 룰셋으로 변환되며 DHCP 응답을 차단하는 과정을
`dmesg` · `syslog`로 추적 및 해결.

...
[상세 기록 →](https://velog.io/@rtd7878)

---

## Skills

| 구분 | 내용 |
|---|---|
| **Virtualization / IaaS** | OpenStack (Kolla-Ansible), KVM, AWS EC2 · VPC · EKS · ECS |
| **Storage** | Ceph (RBD, BlueStore), Cinder, NFS, iSCSI, RAID, XFS |
| **Container** | Kubernetes, Docker, Helm, Calico, MetalLB, Ingress, HPA |
| **Network** | Neutron · Open vSwitch, VLAN/VXLAN, ALB/NLB, Route 53, NAT |
| **CI/CD** | Jenkins, Kaniko, AWS CodePipeline · CodeBuild, Terraform |
| **Observability** | Prometheus, Grafana, Grafana Alloy, CloudWatch, fio, k6 |
| **Language** | Python, Bash |
| **Data** | HDFS, Spark, Airflow, MySQL, MongoDB |

---

## Certifications

- 정보처리기사 (한국산업인력공단, 2024.09)
- TOEIC 795 (ETS, 2025.05)
