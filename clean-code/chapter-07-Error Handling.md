## TIL (Today I Learned)

2022.03.04

## 오늘 읽은 범위

7장. 오류 처리

## 책에서 기억하고 싶은 내용을 써보세요.

- 오류 코드보다 예외를 사용하라.
- Try-Catch-Finally: 오류 코드 단위 테스트 시 -- 먼저 강제로 예외를 일으키는 테스트 케이스를 작성한 후 테스트를 통과하게 코드를 작성하는 방법을 권장한다. 그러면 자연스럽게 try 블록의 트랜잭션 범위부터 구현하게 되므로 범위 내에서 트랜잭션 본질을 유지하기 쉬워진다.
- 미확인(unchecked) 예외 사용하기: 의존성이라는 비용이 이익보다 크다.
- 오류 메시지에 '전후 상황, 정보, 실패한 연산 이름과 실패 유형 언급' 하기
- 호출자를 고려한 예외 클래스 설정: 감싸기 기법 - 외부 API를 감싸면 외부 라이브러리와 프로그램 사이에서 의존성이 크게 줄어듬.
- **정상 흐름을 정의하라.**: 예외가 오히려 논리를 따라가기 어렵게 만드는 경우. 특수 상황을 처리하지 않을 때 코드가 간결해지는 경우도 있다.
  - 특수 사례 패턴 SPECIAL CASE PATTERN (Fowler), 138p: 클래스를 만들거나 객체를 조작해 특수 사례를 처리하는 방식. 그러면 클라이언트 코드가 예외적인 상황을 처리할 필요가 없어진다. 클래스나 객체가 예외적인 상황을 캡슐화해서 처리함.
- null 반환 No ~ : null 반환 습관 nono
  - 메서드에서 null 반환하는 대신에 예외를 던지거나 특수 사례 객체를 반환한다. 사용하려는 외부 API가 null 반환한다면 감싸기 메서드를 구현해 예외를 던지거나 특수 사례 객체를 반환하는 방식 고려.
- null 전달 nono ~ : 반환보다 더 나쁨.

**< NullPointerException이 발생하지 않게 고친 예시 >**

```
public class MetricsCalculator
{
    public double xProjection(Point p1, Point p2) {
        if (p1 == null || p2 == null) {
            throw InvalidArgumentException(
                "Invalid argument for MetricsCalculator.xProjection");
            )
            return (p2.x - p1.x) * 1.5;
        }
    }
}
```

- 하지만 InvalidArgumentException을 잡아내는 처리기가 필요해짐.

**< assert문을 사용하는 예시>**

```
public class MetricsCalculator
{
    public double xProjection(Point p1, Point p2) {
        assert p1 != null : "p1 should not be null";
        assert p2 != null : "p2 should not be null";
        return (p2.x - p1.x) * 1.5;
    }
}
```

- **깨끗한 코드는 읽기도 좋아야 하지만 안정성도 높아야 한다. 이 둘은 사웅하는 목표가 아니다. 오류 처리를 프로그램 논리와 분리해 독자적인 사안으로 고려하면 튼튼하고 깨끗한 코드를 작성할 수 있다. 오류 처리를 프로그램 논리와 분리하면 독립적인 추론이 가능해지며 코드 유지보수성도 크게 높아진다.**

## 오늘 읽은 소감은? 떠오르는 생각을 가볍게 적어보세요.

- 에러 처리는 전체적인 프러덕트를 기획할 때 얼마나 깊이 파고드는지, 얼마나 많은 경우의 수를 진지하게 고민하는지, 프러덕트 공개 이후에는 얼마나 적극적으로 피드백 반영하는지 등과 모두 연결되어 있다. 바쁘게 일을 하다 보면 '이 정도면 됐지 뭐.' 하고 마무리한 일을 다시 돌아보지 않을 때가 많은데, 이 장을 읽으면서 더 파고들 수 있었는데 덮어버린 크고 작은 일들이 생각이 난다. 어릴 때 오답노트 쓰는걸 참 싫어했지...

## 궁금한 내용이 있거나, 잘 이해되지 않는 내용이 있다면 적어보세요.

- [ ] NullPointerException

_#노마드코더 #북클럽 #노개북_
