# Chapter 06. 세션 상태
- - -

## 상태 비저장의 가치
* 객체의 핵심은 상태(데이터)와 동작을 결합하는 것이다.
* 앤터프라이즈 애플리케이션의 상태 비저장은 요청 간에 상태가 유지되지 않는 객체를 의미한다.
* 상태 비저장은 객체를 풀링해 훨씬 적은 수의 객체로 더 많은 사용자를 처리할 수 있게 해준다.

## 세션 상태
* 세션 상태는 한 비즈니스 트랜잭션에 포함되므로 ACID와 같이 여러 사람들이 트랜잭션의 속성이라고 생각하는 속성을 가진다.
* 한 사람이 특정 데이터를 편집하는 동안 해당 데이터는 현재 상태가 유효하지 않을 수 있다.
* 세션 상태와 관련된 가장 중요한 문제는 격리성이다.
* 세션 상태는 요청 간에 꼭 저장할 필요가 없는 데이터도 성능 향상을 위해 캐싱할 수도 있다.

## 세선 상태를 저장하는 방법
* 클라이언트 세션 상태는 데이터를 클라이언트에 저장한다.
* 서버 세션 상태는 요청 간에 데이터를 메모리에 저장하는 간단한 방법일 수 있다.
* 데이터베이스 세션 상태도 역시 서버 쪽 저장소지만 오랫동안 보관할 데이터를 저장하듯이 데이터를 테이블과 필드로 분리하고 데이터베이스에 저장하는 방식이다.
* 세션 어피니티는 한 서버가 특정 세션의 모든 요청을 처리하게 한다.
  * 클라이언트가 프록시를 사용하는 경우 여러 클라이언트가 동일한 IP 주소를 사용하는 것으로 나타나며, 결과적으로 모두 특정한 서버로 연결될 수 있다.
