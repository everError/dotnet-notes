# Redis 정리

## 1. 개요

Redis는 오픈 소스 기반의 **인메모리 데이터 저장소(In-Memory Data Store)**로, 주로 **캐시(Cache), 세션 저장(Session Store), 메시지 브로커(Pub/Sub), 데이터 구조 저장소** 등의 용도로 사용된다. 데이터는 RAM에 저장되므로 **빠른 읽기/쓰기 성능**을 제공하며, 다양한 데이터 구조를 지원한다.

## 2. Redis의 특징

- **인메모리 데이터 저장**: 모든 데이터를 RAM에 저장하여 디스크 기반 데이터베이스보다 훨씬 빠른 속도를 제공.
- **Key-Value 스토어**: 데이터를 Key-Value 형태로 저장하며, 다양한 데이터 구조(List, Hash, Set 등)를 지원.
- **영속성 지원**: AOF(Append-Only File)와 RDB(Snapshot) 방식을 통해 데이터를 디스크에 저장할 수 있음.
- **고성능**: 수십만 건 이상의 요청을 초당 처리할 수 있으며, NoSQL 기반의 빠른 데이터 접근이 가능.
- **Pub/Sub 지원**: 메시지 브로커 기능을 제공하여 실시간 이벤트 처리 및 서버 간 데이터 동기화 가능.
- **클러스터링 및 복제 지원**: 여러 개의 Redis 노드를 연결하여 확장성과 고가용성을 제공.

## 3. Redis의 주요 기능

### 3.1 인메모리 데이터 저장소

- 빠른 데이터 저장 및 조회를 위해 RAM을 활용.
- TTL(Time-To-Live) 기능을 제공하여 일정 시간이 지나면 데이터 자동 삭제 가능.
- 데이터를 Hash, List, Set, Sorted Set 등 다양한 자료구조로 저장 가능.

### 3.2 캐시(Cache)

- 웹 애플리케이션에서 자주 조회하는 데이터를 Redis에 저장하여 성능을 향상.
- TTL을 설정하여 일정 시간이 지나면 자동 삭제되도록 설정 가능.
- 캐싱된 데이터를 기반으로 데이터베이스 부하를 줄일 수 있음.

### 3.3 세션 저장소(Session Store)

- 웹 애플리케이션에서 사용자 로그인 세션을 Redis에 저장하여 세션 관리 가능.
- 여러 개의 서버에서 동일한 Redis 인스턴스를 공유하여 세션 동기화 가능.
- 서버 재시작 후에도 세션을 유지할 수 있도록 설정 가능.

### 3.4 Pub/Sub (메시지 브로커)

- 발행(Publish)과 구독(Subscribe) 기능을 제공하여 서버 간 메시지 전달 가능.
- WebSocket과 결합하여 실시간 채팅, 알림 시스템 등에 활용 가능.
- 분산 환경에서 서버 간 이벤트를 동기화하는 용도로 활용 가능.

### 3.5 데이터 구조 지원

- **String**: 기본적인 Key-Value 저장 방식.
- **List**: Queue 또는 Stack 형태의 데이터 저장.
- **Hash**: JSON과 유사한 Key-Value 형태의 데이터 저장.
- **Set**: 중복 없는 데이터 저장.
- **Sorted Set**: 우선순위를 기반으로 정렬된 데이터 저장.

### 3.6 영속성(Persistence)

- **RDB(Snapshotting)**: 일정 주기마다 데이터를 디스크에 저장하는 방식.
- **AOF(Append-Only File)**: 모든 변경 사항을 로그 파일에 저장하여 장애 발생 시 복구 가능.

### 3.7 분산 및 확장성

- **Redis Replication(복제)**: 여러 개의 Redis 서버를 구성하여 데이터 복제 가능.
- **Redis Cluster(클러스터링)**: 여러 개의 Redis 노드를 활용하여 확장성 및 고가용성 제공.

## 4. Redis와 다른 DB 비교

| 항목              | Redis                                        | MySQL/PostgreSQL (RDBMS)             |
| ----------------- | -------------------------------------------- | ------------------------------------ |
| **저장 방식**     | RAM(메모리) 기반                             | 디스크 기반                          |
| **속도**          | 매우 빠름                                    | 상대적으로 느림                      |
| **데이터 구조**   | Key-Value                                    | 테이블 기반 (관계형)                 |
| **트랜잭션 지원** | 제한적                                       | ACID 트랜잭션 지원                   |
| **확장성**        | 클러스터링 지원                              | 샤딩 및 복제 가능                    |
| **주요 용도**     | 캐시, 세션 저장, Pub/Sub, 실시간 데이터 처리 | 관계형 데이터 저장, 복잡한 쿼리 처리 |

## 5. Redis의 사용 사례

- **API 응답 캐싱**: RESTful API의 응답을 Redis에 저장하여 성능 향상.
- **사용자 세션 관리**: 여러 웹 서버에서 공유하는 세션을 Redis에 저장.
- **실시간 채팅 및 알림 시스템**: Pub/Sub을 활용하여 실시간 메시지 전달.
- **로그 및 분석 데이터 저장**: 빠른 데이터 조회를 위해 Redis를 활용.
- **분산 환경에서 데이터 공유**: 여러 서버 간 실시간 데이터 동기화.

## 6. 결론

Redis는 단순한 인메모리 데이터베이스가 아니라, **캐싱, 세션 저장, 메시지 브로커, 분산 데이터 관리** 등 다양한 용도로 활용할 수 있는 강력한 솔루션이다. 높은 속도와 확장성을 제공하며, Pub/Sub 기능을 통해 마이크로서비스 환경에서도 유용하게 활용될 수 있다. Redis를 적절히 활용하면 애플리케이션의 성능과 확장성을 크게 향상시킬 수 있다.
