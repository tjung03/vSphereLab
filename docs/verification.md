# 작업별 확인 지점

[저장소 소개](../README.md)

아래는 노트의 실습 항목을 **재실습 때 확인할 질문**으로 바꾼 것입니다. 확인 결과를 수집하거나 성공을 재현했다는 뜻은 아닙니다.

| 주제 | 노트의 항목 | 재실습 시 확인할 지점 |
|---|---|---|
| Datastore | 생성, 마운트·해제, 파일 관리, 확장 | 대상 호스트의 datastore 표시, 접근성, 변경 전후 용량 |
| 네트워크 | NIC 추가, 표준 vSwitch, teaming | 물리 NIC와 uplink, VM/VMkernel port group의 연결 관계 |
| VM 수명 주기 | 생성·OS 설치, OVA import, snapshot, clone, template | 인벤토리와 datastore의 VM 파일, snapshot 상태, 배포된 VM의 부팅 여부 |
| vMotion | 라이선스·VMkernel 네트워크·공유 스토리지 점검, 호스트 간 이동 | 출발지·목적지 호스트의 조건과 이동 전후 VM 위치 |
| DRS | 활성화, 수동·완전 자동화 수준 테스트 | 클러스터 설정, 권고·이동 기록, 부하 조건 |
| Storage vMotion·Storage DRS | datastore 간 이동, Storage DRS 구성 | 이동 전후 datastore 위치, datastore cluster 설정과 권고·이동 기록 |
| HA | 클러스터 HA 구성 | HA 설정, 호스트 상태, VM 재시작 정책 및 실제 장애 시험 결과를 구분 |

이동 기능의 사용 가능 여부와 전제 조건은 vSphere 버전, 라이선스, 네트워크, 스토리지 구성에 좌우됩니다. 노트에 적힌 짧은 전제 목록만으로 모든 조건을 충족했다고 보지 않습니다. HA 설정만으로 서비스 무중단이나 장애 복구 시간을 보장하지 않습니다.

수업 노트에는 `WEB(php)-DB` 및 `LB-WEB1/WEB2-NFS` 미니 프로젝트의 구조 이름이 있지만, 앱 코드·설정·검증 결과가 없어 이 저장소에서 구현 사례로 소개하지 않습니다. FT는 `[실습x]`이므로 검증 범위에서 제외합니다.
