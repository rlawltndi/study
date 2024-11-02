### CI/CD
  - CI/CD는 지속적 통합(Continuous Integration) 및 지속적 제공/배포(Continuous Delivery/Deployment)를 의미하며
 , 소프트웨어 개발 라이프사이클을 간소화하고 가속화하는 것을 목표로 한다.

### CI(Continuous Integration)
  - 지속적인 통합을 의미한다.
  - 개발자를 위해 빌드와 테스트를 자동화하는 과정이다.
  - CI는 변경 사항을 자동으로 테스트해 애플리케이션에 문제가 없다는것을 보장한다.
  - 정기적으로 빌드하고, 테스트하므로 여러 명이 동시에 작업을 하는 경우 충돌을 방지하고 모니터링 할 수 있다.
  - 코드 변경 사항이 코드 저장소에 업로드되면 CI를 시작하고, CI 도중에 문제가 생기면 실패하므로 코드의 오류도 쉽게 파악할 수 있다.

### CD(Continuous Deployment)
  - 배포 준비가 된 코드를 자동으로 서버에 배포하는 작업을 자동화 한다.
  - CI가 통과되면 개발자가 수작업으로 코드를 배포하지 않아도 자동으로 배포하니 매우 편리해진다.
  - CD는 지속적인 제공의 continuous Delivery라는 의미도 가진다.

### 일반적인 CI/CD 툴
  - Tekton Pipelines : 표준 클라우드 네이티브 CI/CD 경험과 컨테이너를 제공하는 쿠버네티스 플랫폼을 위한 CI/CD 프레임워크
  - Jenkins: 단순 CI 서버에서 완전한 CD 허브까지 모든 것을 처리하도록 설계된 툴
  - Spinnaker: 멀티클라우드 환경을 위해 구축된 CD 플랫폼
  - GoCD: 모델링 및 시각화에 중점을 둔 CI/CD 서버
  - Concourse: 지속적인 오픈소스 작업 툴
  - Screwdriver: CD용으로 설계된 빌드 플랫폼
