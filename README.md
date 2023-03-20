# msaForPlagiarismCheck    
표절검사 서비시를 MSA화 하며 K8S에 배포하기 위한 각 애플리케이션의 manifest 자료이다.

## 프로젝트 개요  
약 5개월 간 작업, 백엔드 개발자 2명, devops 엔지니어 2명이서 진행

## 나의 R&R 
표절검사 서비스의 client 부분 배포, network 트래픽 제어를 위한 Istio 도입  
개발, 운영 각 클러스터 별 배포  
컨테이너 이미지 저장소를 위해 docker harbor 구축하고 거기에 맞는 rbac 수립  
argo CD에 배포 전략 다양화를 위해 argo rollout 도입


## k8s 구조  
외부(was)와 통신이 빈번한 구조로 이뤄져 있어 서비스 디스커버리 기능은 필수였고  
scale in&out 도 가능해지며 네트워크 모니터링을 직관적으로 볼 수 있게 하기 위해 서비스메쉬 툴인 Istio 도입  


## CI/CD 방식  
CI - teamcity와 docker harbor를 활용하여 컨테이너 이미지 빌드 및 저장  
CD - argo CD 와 argo rollout을 활용하여 배포 환경과 배포 전략 설정 후 배포
