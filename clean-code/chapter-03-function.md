## TIL (Today I Learned)

2022.02.22

## 오늘 읽은 범위

3장. 함수

## 책에서 기억하고 싶은 내용을 써보세요.

- 함수를 만드는 첫째 규칙은 '작게!'다. 함수를 만드는 둘째 규칙은 '더 작게!다. (42p)
- if 문/else 문/while 문 등에 들어가는 블록은 한 줄이어야 한다. (43p)
- 함수는 한 가지를 해야 한다. 그 한 가지를 잘 해야 한다. 그 한 가지만을 해야 한다. ~ 단순히 다른 표현이 아니라 의미 있는 이름으로 다른 함수를 추출할 수 있다면 그 함수는 여러 작업을 하는 셈이다. (45p)
- 함수 이름을 정할 때는 여러 단어가 쉽게 읽히는 명명법을 사용한다. 그런 다음, 여러 단어를 사용해 함수 기능을 잘 표현하는 이름을 선택한다. 이름을 정하느라 시간을 들여도 괜찮다. (49p)
- 함수에서 이상적인 인수 개수는 0개(무항)다. (50p)
- 플래그 인수는 추하다. 함수로 부울 값을 넘기는 관례는 정말로 끔찍하다. (52p)
- 시간적인 결합은 혼란을 일으킨다. 특히 부수 효과로 숨겨진 경우에는 더더욱 혼란이 커진다. 만약 시간적인 결합이 필요하다면 함수 이름에 분명히 명시한다. (55p)
- 명령과 조회를 분리하라! 함수는 뭔가를 수행하거나 뭔가에 답하거나 둘 중 하나만 해야 한다. ~ 객체 상태를 변경하거나 아니면 객체 정보를 반환하거나 둘 중 하나다. (55p)
  **Don't**

```
public boolean set(String attribute, String value);
if (set("username", "unclebob"))...
```

**Do**

```
if (attributeExsists("username")) {
    setAttribute("username", "unclebob");
    ...
}
```

- 오류 코드보다 예외를 사용하라!
- 에츠허르 데이크스트라(Edsger Dijkstra)의 구조적 프로그래밍 원칙: 모든 함수와 함수 내 모든 블록에 입구(entry)와 출구(exit)가 하나만 존재해야 한다.(함수가 클 때만 상당한 이득) ~ 함수를 작게 만든다면 간혹 return, break, continue를 여러 차례 사용해도 괜찮다. (61p)
- 밥 아저씨 왈, '서투른 코드를 빠짐없이 테스트하는 단위 테스트 케이스도 만든다. 그런 다음 코드를 다듬고, 함수를 만들고, 이름을 바꾸고, 중복을 제거한다. 메서드를 줄이고 순서를 바꾼다. 때로는 전체 클래스를 쪼개기도 한다. 이 와중에도 코드는 항상 단위 테스트를 통과한다. 최종적으로는 이 장에서 설명한 규칙을 따르는 함수가 얻어진다. 처음부터 탁 짜내지 않는다. 그게 가능한 사람은 없으리라.'
- 함수는 동사, 클래스는 명사다.

## 오늘 읽은 소감은? 떠오르는 생각을 가볍게 적어보세요.

- 어렵지만 눈을 부릅뜨고 열심히 코드를 읽었다. 정확하게 이해하지 못하더라도 자꾸 눈에 익히고 구조적으로 익숙해져야한다는 생각으로 읽었다. 코드를 읽으면서 설명을 읽고, 설명을 읽고 다시 코드를 읽었다. 읽다보니 좋은 코드가 뭔지 이해는 될 것 같다. 클린코드 규칙들이 적용된 코드가 마법처럼 깔끔해지는 것을 보면 감동이 인다.
- 밥아저씨의 못생긴 코드 경멸하는 문장들이 너무 웃겨서 간간히 웃음이 터진다.
- '대가(master) 프로그래머는 시스템을 (구현할) 프로그램이 아니라 (풀어갈) 이야기로 여긴다. 프로그래밍 언어라는 수단을 사용해 좀 더 풍부하고 좀 더 표현력이 강한 언어를 만들어 이야기를 풀어간다.'는 결론 부분이 마음에 크게 와닿았다. 코딩 뿐만 아니라 기획 문서를 쓸 때에도, 인생의 크고 작은 계획을 세울 때도 마찬가지인 부분 아닌가!

## 궁금한 내용이 있거나, 잘 이해되지 않는 내용이 있다면 적어보세요.

- [ ] LOGO 언어
- [ ] Polymorphism 다형성
- [ ] [SRP Single Responsibility Principle](http://en.wikipedia.org/wiki/Single_responsibility_principle)
- [ ] [OCP Open Closed Principle](http://en.wikipedia.org/wiki/Open/closed_principle)
- [ ] 함수 인수

_#노마드코더 #북클럽 #노개북_