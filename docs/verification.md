# vSphere 작업별 확인 지점

[저장소 소개](../README.md)

다음은 기능별 **검증 절차**입니다. 이 저장소에 실제 작업의 성공 화면이나 장애 시험 결과가 포함됐다는 뜻은 아닙니다.

| 주제 | 변경 전에 확인 | 변경 뒤 확인 |
|---|---|---|
| Datastore | 대상 호스트의 LUN·경로·여유 용량 | 호스트별 datastore 표시, 접근성, 용량 |
| 네트워크 | 물리 NIC와 uplink, VM·VMkernel port group | VM 연결과 서비스 트래픽 경로 |
| VM 수명 주기 | 대상 VM·datastore·snapshot 상태 | 생성·복제·template 배포 뒤 부팅과 파일 위치 |
| vMotion | 버전·라이선스, VMkernel 네트워크, 호스트·스토리지 조건 | 출발지·목적지 호스트의 VM 위치와 작업 로그 |
| DRS | 클러스터 구성과 자동화 수준 | 권고·이동 기록과 부하 조건 |
| Storage vMotion·Storage DRS | datastore 접근성과 공간, 기능 조건 | VM 파일 위치와 datastore cluster의 권고·이동 기록 |
| HA | 호스트 상태, HA 정책과 대상 VM | 설정 상태와 별도 장애 시험의 실제 재시작 결과 |

기능 사용 가능 여부는 vSphere 버전, 라이선스와 네트워크·스토리지 구성에 좌우됩니다. HA 구성만으로 서비스 무중단이나 복구 시간을 보장하지 않습니다. FT는 이 문서의 범위에서 제외합니다.
