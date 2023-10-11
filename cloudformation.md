Cloudformation
---

## Attributes

### `CreationPolicy`
- CreationPolicy 속성을 리소스에 붙여 AWS Cloudfomration이 지정된 수의 성공 시그널 받더가 타임아웃 시간이 초과할때까지 해당 리소스의 생성 완료 상태가 되는 것을 막는다.
- `cfn-signal`: 리소스에 시그널을 보내기 위하여 `cfn-signal helper script`나 `SignalResource API`를 활용할 수 있다.
- CreationPolicy는 Cloudformation이 관련 리소스를 생성할때만 호출된다.
- 현재 CreationPolicy를 지원하는 리소스는 다음뿐이다.
  - `AWS::AutoScaling::AutoScalingGroup`, `AWS:EC2::Instance`, `AWS::CloudFormation::WaitCondition`
- 스택 생성이 진행되기 전에 리소스 설정 액션을 대기하고 싶을때 CreationPolicy를 사용한다.
  - ex. EC2 인스턴스에 소프트웨어를 설치하고 구성한다면, 계속해서 다음을 진행하기 전에 해당 애플리케이션이 실행 중이어야 할 수 있다. 이런 경우 CreationPolicy 속성을 해당 인스턴스에 붙이고 애플리케이션이 설치/구성된 후에 인스턴스에 시그널을 보낸다.

### `DependsOn`
- DependsOn 속성을 통해 특정 리소스의 생성을 다른 리소스의 다음으로 보장할 수도 있지만, CreationPolicy는 스택 생성이 다음으로 진행하기 전에 애플리케이션이 완전히 기동되는 것을 보장하는 차이가 있다.

### `UpdatePolicy`
- 리소스 갱신과 스택 갱신 롤백 작업에 사용한다.

### `UpdateReplacePolicy`
- 주로 스택 업데이트 작업 중에 리소스가 교체될 때 리소스의 기존 물리적 인스턴스를 유지하거나 경우에 따라 백업하는 데 사용.
