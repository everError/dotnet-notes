# Experiments

이 디렉토리는 .NET 기반으로 백엔드 서버 개발 및 다양한 실습 프로젝트를 구현하기 위해 만들어졌습니다. 주요 목표는 특정 기술이나 기능을 학습하고, 이를 실제로 적용해보는 것입니다.

## 개발 목록

- **.NET Aspire 앱 호스트**: 확장성과 유연성을 제공하는 앱 호스트를 생성하여 백엔드 서버 개발을 시작. 이 앱 호스트는 여러 백엔드 서비스를 오케스트레이션하여 효율적으로 관리하고, 서비스 간의 상호작용을 간소화하는 데 중점을 둡니다.
- **Access Token 및 Refresh Token 발급**: JWT(Json Web Token)를 활용하여 Access Token과 Refresh Token을 생성하고 관리하는 기능 구현.
- **EF Core 적용**: 데이터베이스와 상호작용하기 위한 ORM(Object-Relational Mapping)으로 EF Core를 활용.
- **Ocelot 기반 API Gateway 구축**: 마이크로서비스 환경에서 클라이언트 요청을 적절한 서비스로 전달하고, 인증 및 요청 제한 등의 기능을 수행하는 API Gateway 개발. LoadBalancer 적용.
- **Redis 적용**: Refresh Token을 안전하게 저장하고 관리하기 위해 Redis를 활용하며, Pub/Sub 기능을 이용하여 서버 간 이벤트를 처리.

## 사용 버전

- **C# 12**
- **.NET 8**: 백엔드 서버 개발의 기본 기반으로 사용.
- **.NET Aspire 9**: 앱 호스트와 서비스 오케스트레이션을 위한 기반으로 사용.
