
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


### 🤖 [AI Resume–Job Fit Analysis Backend](https://github.com/SWYP14th-Team3/BackEnd)

> 이력서와 채용공고를 분석하여 지원자의 직무 적합도와 보완점을 제공하는 AI 기반 서비스  
> **Team Project · Backend Developer**

PDF 이력서와 URL·텍스트·이미지 형태의 채용공고를 수집하고,  
Gemini를 활용해 채용 요건별 충족도와 이력서 개선 방향을 생성하는 백엔드 시스템입니다.

#### 담당 영역

- Spring Boot 프로젝트 초기 구조와 로컬 개발 환경 구성
- 공통 API 응답, 오류 코드, 사용자 정의 예외 및 전역 예외 처리 구현
- Gemini 기반 이력서–채용공고 분석 및 재분석 API 구현
- PDF 이력서 텍스트 추출 및 유효성 검증
- URL 크롤링, 직접 입력 텍스트, 공고 이미지 OCR을 지원하는 입력 파이프라인 구현
- 분석 결과와 채용 요건별 평가를 JPA 엔티티로 설계하고 MySQL에 저장
- JUnit 5와 Mockito를 활용한 분석 서비스 및 예외 상황 테스트 작성

#### 주요 기술적 고민과 해결

- **다양한 형태의 채용공고 입력 처리**
  - 채용공고를 URL, 직접 입력한 텍스트, 이미지로 받을 수 있도록 설계했습니다.
  - URL 크롤링이 불가능한 경우 사용자가 입력한 원문을 우선 사용하는 fallback 전략을 적용했습니다.
  - Gemini OCR로 이미지의 텍스트를 추출하고 URL·텍스트 결과와 병합했습니다.
  - 동일한 공고 내용이 중복 저장되지 않도록 프롬프트와 병합 로직을 개선했습니다.

- **LLM 응답의 불확실성 제어**
  - Gemini의 `response_schema`를 사용해 응답을 정해진 JSON 구조로 제한했습니다.
  - 회사명, 포지션, 채용 요건, 충족 상태와 피드백을 DTO로 변환하고 검증했습니다.
  - 누락되거나 잘못된 응답은 공통 예외로 처리해 비정상 데이터가 저장되는 것을 방지했습니다.

- **단계별 AI 분석 파이프라인 설계**
  - 이력서 정리 → 채용공고 구조화 → 요건별 적합도 분석 → 개선 우선순위 계산 → 피드백 카드 생성 단계로 분석을 분리했습니다.
  - 부족한 요건에는 기대효과와 작성 난이도를 점수화하여 개선 우선순위를 제공했습니다.
  - 수정된 이력서를 다시 평가할 수 있는 재분석 기능과 분석 시도 이력을 구현했습니다.

- **파일 입력 안정성 강화**
  - 확장자만 확인하지 않고 MIME Type, 파일 크기, PDF 헤더와 실제 파싱 가능 여부를 검증했습니다.
  - 손상되거나 PDF로 위장된 파일이 분석 과정으로 진입하지 않도록 방어했습니다.

- **협업 기반 마련**
  - 공통 응답 형식과 전역 예외 처리 규칙을 만들어 팀 API의 일관성을 확보했습니다.
  - Gradle Wrapper, MySQL Docker Compose, 환경별 Spring Profile을 구성했습니다.
  - PR 템플릿과 실행·예외 처리·커밋 규칙 문서를 작성해 협업 기준을 정리했습니다.

#### Tech Stack

![Java](https://img.shields.io/badge/Java_25-007396?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot_4-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=flat-square&logo=spring&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-8E75B2?style=flat-square&logo=googlegemini&logoColor=white)
![Jsoup](https://img.shields.io/badge/Jsoup-4992C1?style=flat-square&logoColor=white)
![Apache PDFBox](https://img.shields.io/badge/Apache_PDFBox-D22128?style=flat-square&logo=apache&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![JUnit5](https://img.shields.io/badge/JUnit_5-25A162?style=flat-square&logo=junit5&logoColor=white)
![Mockito](https://img.shields.io/badge/Mockito-78A641?style=flat-square&logoColor=white)
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
