AWS DataSync
---

- **on-premies storage와 s3, Amazon EFS, or Amazon FSx for Windows File Server 간에 대량의 데이터를 온라인으로 간단하고 빠르게 이동할 수 있도록 해주는 서비스**.
- 복사 작업 스크립트 작성, 전송 예약 및 모니터링, 데이터 유효성 검사, 네트워크 사용률 최적화 등의 많은 작업을 제거하거나 자동으로 처리하도록 해준다.
- DataSync software agent는 NFS(Network File System), SMB(Server Message Block) 스토리지, self-managed object storage에 연결하므로 애플리케이션을 수정할 필요가 없다.
- 인터넷 또는 AWS direct connect 링크를 통해 오픈 소스 도구보다 최대 10배 빠른 속도로 수백 테라바이트 및 수백만 개의 파일을 전송할 수 있다.
- 활성 데이터 셋 또는 아카이브를 AWS로 마이그레이션하거나, 적시 분석 및 처리를 위해 데이터를 클라우드로 전송하거나, 비즈니스 연속성을 위해 데이터를 AWS로 복제할 수 있다.
- Getting started with Datasync is easy
  - 1. deploy DataSync agent
  - 2. connect it to your file system.
  - 3. select your AWS storage resources.
  - 4. start moving data between them.
- Pricing
  - 이동한 데이터에 대해서만 비용 지불.
  