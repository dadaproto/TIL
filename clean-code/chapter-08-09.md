## 오늘 TIL 3줄 요약

- 경계를 관리하고 외부 패키지 의존도를 낮추기 위해 (1)새로운 클래스로 경계를 감싸기, (2)ADAPTER 패턴 사용하기, (3)테스트 케이스 작성하기, (4)코드 깔끔하게 분리하기
- 깨끗한 테스트 코드는 실제 코드만큼 프로젝트 건강에 중요하다.
- 깨끗한 테스트 코드를 위한 다섯 가지 규칙 F(ast).I(ndependent).R(epeatable).S(elf-Validating).T(imely)

## TIL (Today I Learned) 날짜

2022.03.06

## 오늘 읽은 범위

Chapter 8: 경계 (Boundaries)
Chapter 9: 단위 테스트 (Unit Tests)

## 책에서 기억하고 싶은 내용을 써보세요.

### Chapter 8. 경계

- 경계 인터페이스를 사용할 때는 이를 이용하는 클래스나 클래스 계열 밖으로 노출되지 않도록 주의한다. (Map 인스턴스를 공개 API의 인수로 넘기거나 반환값으로 사용하지 않는다.)
- 학습 테스트: 곧바로 외부 코드를 호출하는 대신 먼저 간단한 테스트 케이스를 작성해 외부 코드 익히기
  - 패키지 새 버전이 나온다면 학습 테스트를 돌려 차이가 있는지 확인.
  - 학습 테스트는 패키지가 예상대로 도는지 검증한다.
  - 경계 테스트가 있다면 패키지의 새 버전으로 이전하기 쉬워진다.

### Chapter 9. 단위 테스트

- **TDD** Test-Driven Development
  - 실패하는 단위 테스트를 작성할 때까지 실제 코들르 작성하지 않는다.
  - 컴파일은 실패하지 않으면서 실행이 실패하는 정도로만 단위 테스트를 작성한다.
  - 셋째 법칙: 현재 실패하는 테스트를 통과할 정도로만 실제 코드를 작성한다.
- 테스트는 유연성, 유지보수성, 재사용성을 제공한다.
  - 깨끗하게!
  - 실제 코드를 점검하는 자동화된 단위 테스트 슈트는 설계와 아키텍처를 최대한 깨끗하게 보존하는 열쇠다. 테스트는 유연성, 유지보수성, 재사용성을 제공한다. 테스트 케이스가 있으면 변경이 쉬워지기 때문이다.
- 깨끗한 테스트 코드를 만들려면 **가독성** 필수.
- **F.I.R.S.T.** 깨끗한 테스트를 위한 다섯 가지 규칙
  - Fast (빠르게): 테스트는 빨라야 한다.
  - Independent (독립적으로): 각 테스트는 서로 의존하면 안된다. 독립적으로 어떤 순서로 실행해도 괜찮아야 한다.
  - Repeatable (반복가능하게): 어떤 환경에서도 반복 가능해야 한다.
  - Self-Validating (자가검증하는): 테스트는 부울(bool) 값으로 결과를 내야 한다. 성공 or 실패.
  - Timely (적시에): 테스트는 적시에 작성해야 한다. 단위 테스트는 테스트하려는 실제 코드를 구현하기 직전에 구현한다.

## 오늘 읽은 소감은? 떠오르는 생각을 가볍게 적어보세요.

- 아직 존재하지 않는 코드를 사용하기 (150p) 의 내용과 접근 방식이 흥미롭다. 정의할 수 없지만 필요한 시스템 영역의 먼 곳부터 작업을 시작해 필요한 내용을 인터페이스로 구현하고 추후에 API가 정의된 이후에는 ADAPTER 패턴 사용, API 사용을 캡슐화하는 방식을 썼다. 코드 뿐만 아니라 어떤 프로젝트든 방대한 기획을 짤 때도 필요하지만 습기찬 창문처럼 뿌옇게 실체가 보이지 않는 지점들이 있다. 프로그래밍적인 사고로 프로젝트를 짠다면 완벽한 계획을 짜는데에 시간을 쏟기보다 일단 만들어가며 빈 부분을 채워갈 수 있지 않을까?
- 프로그래밍 예시들을 좀 더 잘 이해하고 싶다. 본격적인 사례들이 나오면서 비문학 지문 읽는 기분이 든다.

## 궁금한 내용이 있거나, 잘 이해되지 않는 내용이 있다면 적어보세요.

- [ ] assert
- [ ] TEMPLATE METHOD 패턴

## 오늘 읽은 다른 사람의 TIL

https://nomadcoders.co/community/thread/3371

_#노마드코더 #북클럽 #노개북_
