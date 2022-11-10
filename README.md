# ControlConcurrencyIssue
인프런_재고시스템으로 알아보는 동시성이슈 해결방법

---
ExecutorService란?
---
- 병렬 작업 시 여러 개의 작업을 효율적으로 처리하기 위해 제공되는 JAVA 라이브러리이다.
- ExecutorService에 Task만 지정해주면 ThreadPool을 이용하여 Task를 실행하고 관리한다.
- Task는 `Queue`로 관리한다.
    - ThreadPool에 있는 Thread수 보다 Task가 많으면, 미실행된 Task는 Queue에 저장되고, 실행을 마친 Thread로 할당되어 순차적으로 수행된다.

레이스 컨디션(Race Condition)이란?
---
두 개 이상의 프로세스가 공통 자원을 병행적으로 읽거나 쓸 때, 공용 데이터에 대한 접근이 어떤 수서에 따라 이루어졌는지에 따라 그 실행 결과가 달라지는 상황을 말한다.
