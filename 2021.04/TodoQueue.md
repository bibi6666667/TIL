# ing..



# Todo Queue

## 미션에서 배운 점 정리하기

```java
// UPDATE
@PutMapping("/cards/{id}")
public ResponseEntity editCards(@PathVariable Long id, @RequestBody CardDto newCardDto) {
    cardService.edit(id, newCardDto);
    return new ResponseEntity<>("SUCCESS", HttpStatus.OK);
}
```

- `ResponseEntity`
  - `HttpEntity` : HTTP 요청 또는 응답에 해당하는 HTTP Header와 HTTP Body를 포함하는 Spring FrameWork의 클래스이다.
  - `HttpEntity`를 상속받아 구현한 클래스가 `RequestEntity`,` ResponseEntity`이다.
  - `ResponseEntity` : 사용자의 HttpRequest에 대한 응답 데이터를 포함하는 클래스. 
    - HttpStatus, HttpHeaders, HttpBody를 포함한다.

- `@RequestBody`

- `@RestController`
  - 그냥 `@Controller`와의 차이?

```java
public interface CardRepository extends CrudRepository<Card, Long> {
    @Query("select * from card c where not c.status = 'DELETED'")
    List<Card> findByStatusIsNotDeleted();
}
```

- `@Query()`

```java
@Transactional
public void create(CardDto cardDto) {
    Card card = new Card(cardDto);
    cardRepository.save(card);
}
```

- `@Transactional`

---

- OOP 특징(Encapsulation, Inheritance, Abstraction, Polymorphism),
  Solid원칙(Single Responsibility Principle, Open / Closed Principle, Liskov's Substitution Principle, Interface Segregation Principle, Dipendency Inversion Principle) 내 말로 요약 정리해 오기
- @RequestBody 와 스프링 API방식 JSON데이터전달 공부하기
- @ResponseEntity
- 스프링 데이터 JDBC, SQL문 사용법

---

- 미션5피드백 달린 것 자세히 보고 정리하기

  https://github.com/codesquad-members-2021/spring-boot-qna/pull/133

- 미션6페이징 이어서 하기

  - 이노가 알려준 참고링크들.

    >https://gonyda.tistory.com/15
    >
    >https://gonyda.tistory.com/16
    >
    >https://lkhlkh23.tistory.com/84 - Page 메서드들
    >
    >https://github.surf/eNoLJ/spring-boot-qna/blob/mission6/src/main/java/com/codessquad/qna/controller/QuestionController.java 이노의 미션6 깃서프

- 블로그 포스팅 정리

- Optional

  - https://mangkyu.tistory.com/70 

- [실습으로 배우는 AWS 핵심 서비스](https://www.inflearn.com/course/aws-%ED%95%B5%EC%8B%AC-%EC%8B%A4%EC%8A%B5/dashboard) 듣기!!

- Logger, LoggerFactory 공부해서 사용하기(루카스 '로깅 라이브러리'참고)

- 스프링MVC구조 및 Model, Domain에 대해 아래 링크 참고해서 더 공부하기.

  - [What is the difference between an MVC Model object, a domain object and a DTO](https://stackoverflow.com/questions/3853749/what-is-the-difference-between-an-mvc-model-object-a-domain-object-and-a-dto)
  - [Spring MVC 구조에 대한 좋은 그림과 설명](https://justforchangesake.wordpress.com/2014/05/07/spring-mvc-request-life-cycle/)

- [트랜잭션](http://egloos.zum.com/sweeper/v/3003805)

- [스프링 웹 계층](https://www.petrikainulainen.net/software-development/design/understanding-spring-web-application-architecture-the-classic-way/)

