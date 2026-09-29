# VMware vSphere 구성과 점검

ESXi 호스트, vCenter, 공유 iSCSI 스토리지와 클러스터의 관계를 설명하고 VM 관리·이동·가용성 기능의 확인 지점을 정리한 실습 문서입니다. GUI 작업을 위한 구성 시나리오이며 자동 배포 코드나 현재 운영 중인 클러스터의 검증 결과는 포함하지 않습니다.

## 구성 시나리오

| 영역 | 구성 요소와 역할 | 상세 |
|---|---|---|
| 관리 | ESXi 호스트 3대 중 2대를 클러스터에 등록하고 vCenter에서 관리 | [구성 관계](docs/lab-topology.md) |
| 스토리지·네트워크 | iSCSI LUN을 호스트에서 확인하고 datastore, vSwitch, port group의 연결을 살핌 | [구성 관계](docs/lab-topology.md) |
| VM 작업 | 생성·snapshot·clone·template과 이동 전후 상태 확인 | [작업별 검증](docs/verification.md) |
| 클러스터 기능 | vMotion, DRS, Storage vMotion·Storage DRS, HA의 전제와 결과 구분 | [작업별 검증](docs/verification.md) |

## 구성과 확인의 순서

1. ESXi 호스트의 관리 접속과 네트워크를 준비하고 vCenter에 등록합니다.
2. iSCSI target과 LUN의 접근 조건을 확인한 뒤 각 호스트에서 datastore를 확인합니다.
3. 클러스터 대상 호스트와 VM·VMkernel 네트워크를 확인합니다.
4. VM 작업 및 이동을 수행할 경우 전제 조건과 작업 전후 위치·상태를 기록합니다.

이 문서의 호스트 수와 순서는 **검토용 시나리오**입니다. 실제 설치 버전, 라이선스, 네트워크 분리, 공유 스토리지 접근성과 작업 결과는 대상 환경에서 별도로 확인해야 합니다. 기능을 설정했다는 사실만으로 무중단 서비스나 장애 복구 시간을 보장하지 않습니다. FT는 이 문서의 검증 범위에 포함하지 않습니다.
