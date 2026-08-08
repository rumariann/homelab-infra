# 🚀 Home Lab Infrastructure as Code (IaC)

개인용 홈 랩 환경의 미디어 서버 및 인프라를 Ansible을 활용하여 코드로 프로비저닝하고 자동화(IaC)한 프로젝트입니다.

## 🎯 핵심 구현 내용
1.  **에이전트리스 원격 제어망 구축:** SSH Key-pair 기반으로 Control Node와 NAS 간의 통신망 구축.
2.  **멱등성 보장 배포 파이프라인:** Ansible Playbook을 작성하여 Docker 기반 미디어 서버(Jellyfin) 컨테이너를 스크립트 한 줄로 무중단 배포.
3.  **환경 분리 및 포트 포워딩:** 기존 서비스(8096 포트)와의 충돌을 방지하기 위해 테스트용 컨테이너를 8097 포트로 우회하여 배포 성공.

## 🛠️ Trouble Shooting
*   **Issue 1:** 타겟 노드의 Python 버전 파편화 에러 ➡️ `hosts.ini` 인터프리터 절대 경로 명시로 해결.
*   **Issue 2:** 컨테이너 포트 충돌 및 이름 중복 에러 ➡️ 포트 매핑 변경(8097) 및 Ad-hoc 명령어로 더미 컨테이너 삭제 후 배포.
