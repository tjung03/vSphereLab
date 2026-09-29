# VMware vSphere 실습 구성 노트

개인 vSphere 과정 노트의 ESXi·vCenter·공유 스토리지·클러스터 구성과 VM 관리 항목을 **구성 순서와 확인 기준**으로 정리한 저장소입니다. GUI 중심의 학습 기록이며, 자동 배포 코드나 현재 운영 중인 클러스터는 포함하지 않습니다.

## 다룬 범위

| 영역 | 노트에 남은 작업 | 상세 |
|---|---|---|
| 기본 구성 | ESXi 호스트 3대, vCenter VM, NAS iSCSI LUN, 2호스트 클러스터 | [구성 관계](docs/lab-topology.md) |
| 호스트와 VM | datastore, 표준 vSwitch·port group, VM 생성·snapshot·clone·template | [작업별 확인](docs/verification.md) |
| 이동과 가용성 | vMotion 전제 점검, DRS, Storage vMotion·Storage DRS, vSphere HA | [작업별 확인](docs/verification.md) |

노트의 `[실습]`은 실습 항목이 기록되었다는 근거입니다. 당시 작업의 성공 로그나 스크린샷, 현재 재현 결과가 이 저장소에 있는 것은 아닙니다. FT는 노트에서 `[실습x]`로 표시되어 완료 범위에서 제외했습니다.

## 구성 흐름

1. ESXi 호스트를 준비하고 vCenter를 배치합니다.
2. vCenter에 호스트를 등록하고, iSCSI 스토리지를 호스트에서 확인합니다.
3. 두 호스트를 클러스터로 묶은 뒤 네트워크와 datastore를 확인합니다.
4. VM 생성·복제·template·snapshot을 다루고, 이동 및 가용성 항목의 전제 조건을 확인합니다.

노트에는 VM 기반 ESXi 3대 중 두 호스트를 `BasicCluster`에 넣고, 별도의 NAS를 공유 스토리지로 쓰는 구성이 기록되어 있습니다. 주소와 관리 접속 정보는 공개 문서에서 생략했습니다. [구성 관계](docs/lab-topology.md)는 각 구성 요소가 어떤 작업에 필요한지 설명합니다.

## 재실습 시 읽는 순서

1. [구성 관계](docs/lab-topology.md)에서 호스트, 관리 서버, 공유 스토리지의 역할을 확인합니다.
2. [작업별 확인](docs/verification.md)의 전제·확인 지점을 실제 버전과 라이선스에 맞게 점검합니다.
3. 결과를 주장하려면 해당 환경의 설정 화면, 실행 기록, 장애 전후 상태를 별도로 남깁니다.

수업 노트는 특정 vSphere 릴리스나 라이선스를 확정하지 않습니다. 제품 UI와 기능 사용 조건은 실제 설치 버전의 벤더 문서에서 다시 확인해야 합니다. 수업 교재, 설치 이미지, 접속 계정과 VM 식별자는 포함하지 않았습니다.
