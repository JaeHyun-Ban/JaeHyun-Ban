
### Hi there 👋 
<br/>

I'm Studying Java, Spring, SpringBoot...

### Get in Touch

[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/jaehyeon-ban-317645235/)](https://www.linkedin.com/in/jaehyeon-ban-317645235/)

<br/>

## 🛠 Tech Stack

![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=000000)
![Spring](https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=spring&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Microsoft SQL Server](https://img.shields.io/badge/Microsoft_SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white)
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white)
![Windows Server](https://img.shields.io/badge/Windows_Server-0078D4?style=flat-square&logo=windows&logoColor=white)

<br/>

## 🚀 Side Projects

### 🛒 [E-Commerce Platform](https://github.com/JaeHyun-Ban/hhplus_ecommerce03)

상품 조회부터 장바구니, 주문·결제, 쿠폰 발급까지 구현한 이커머스 백엔드 프로젝트입니다.  
단순한 API 구현을 넘어, 다수의 사용자가 동시에 주문하거나 쿠폰을 발급받을 때 발생하는
**데이터 정합성, 동시성, 분산 트랜잭션 및 성능 문제**를 중점적으로 다뤘습니다.

#### 주요 기술적 고민과 해결

- **동시성 제어 전략**
  - 선착순 쿠폰 발급에는 `Redisson 분산 락`
  - 잔액과 주문번호에는 정합성을 우선한 `비관적 락`
  - 상품 재고에는 성능을 고려한 `낙관적 락 + 재시도`
  - 데이터의 중요도와 충돌 가능성에 따라 서로 다른 잠금 방식을 적용했습니다.

- **주문 과정의 데이터 일관성**
  - 주문·재고·잔액·쿠폰 처리를 비동기 이벤트로 분리했습니다.
  - `Saga Choreography`와 보상 트랜잭션을 적용해 중간 단계 실패 시 데이터를 복구하도록 설계했습니다.
  - 멱등성 키를 사용해 중복 주문과 중복 결제를 방지했습니다.

- **조회 성능 개선**
  - Redis 캐시, DB 인덱스 및 `EntityGraph`를 적용했습니다.
  - N+1 문제를 제거해 조회 쿼리를 `21회 → 1회`로 줄였습니다.
  - 부하 테스트 기준 전체 처리량을 `60 TPS → 600 TPS`로 개선했습니다.

- **테스트 및 성능 검증**
  - Testcontainers 기반으로 실제 MySQL·Redis 환경에서 통합 테스트를 수행했습니다.
  - JMeter와 k6로 쿠폰 발급, 주문 생성 및 상품 조회 시나리오를 검증했습니다.
  - 1,000명의 동시 요청에서도 한정된 쿠폰 100개만 발급되는 것을 확인했습니다.

#### Tech Stack

![Java](https://img.shields.io/badge/Java_17-007396?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=flat-square&logo=spring&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL_8-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis_7-FF4438?style=flat-square&logo=redis&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![JUnit5](https://img.shields.io/badge/JUnit_5-25A162?style=flat-square&logo=junit5&logoColor=white)
![Apache JMeter](https://img.shields.io/badge/Apache_JMeter-D22128?style=flat-square&logo=apachejmeter&logoColor=white)
![k6](https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white)


<!--

**JaeHyun-Ban/JaeHyun-Ban** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
