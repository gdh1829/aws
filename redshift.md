Amazon Redshift
---

- 증가하는 데이터가 운영 데이터 스텅, 데이터 레이크, 스트리밍 데이터 서비스 또는 타사 데이터 세트 중 어디에 저장되는지에 관계없이 Redshift를 통해 최소한의 이동 또는 복사만으로 안전하게 데이터에 액세스하고 데이터를 결합 및 공유할 수 있다.
- Redshift는 AWS 데이터베이스, 분석 및 기계 학습 서비스와 긴밀하게 통합되어 Zero-ETL 접근 방식을 사용하거나 실시간에 가까운 분석을 위해 작업할 준비가 된 데이터에 액세스하고, SQL로 기계 학습 모델을 구축하고, Reshift의 데이터를 사용한 Apache Spark 분석을 활성화할 수 있게 지원한다.
- Redshift serverless도 존재.

## Redshift Spectrum
- 데이터를 Redshift 테이블에 로드하지 않고도 S3의 파일에서 정형 및 비정형 데이터를 효율적으로 쿼리하고 가져올 수 있다.
- 스펙트럼 쿼리는 대량 병렬 처리를 채택해 큰 데이터 집합에 대해 매우 빠르게 실행된다.
- 다수의 클러스터가 S3의 동일한 데이터 집합에 대해 동시에 쿼리를 실행할 수 있기 때문에 각 클러스터의 데이터를 일일이 복사할 필요가 없다.