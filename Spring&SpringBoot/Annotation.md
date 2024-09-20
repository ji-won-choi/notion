# Lombok ?
: 어노테이션 기반으로 코드 자동완성 해주는 라이브러리. 보일러플레이트 메서드를 직접 작성하지 않아도 된다. 
<br><br>
보일러플레이트 : `최소한의 변경으로 여러곳에서 재사용되며, 반복적으로 비슷한 형태를 띄는 코드`

## @Builder
- 메서드, 생성자에만 붙일 수 있다.
- 클래스 레벨에서 @Builder 어노테이션을 붙이면 모든 요소를 받는 package-private 생성자가 자동으로 생성되며
  이 생성자에 @Builder 어노테이션을 붙인 것과 동일하게 동작한다.
- 다른 생성자가 이미 있을 경우 제대로 동작하지 않을 수 있다.

## @NoArgsConstructor
- 파라미터가 없는 디폴트 생성자를 자동으로 생성
  ```java
  @NoArgsConstructor
  public class User{
    private String name;
    private int age;
  }
  ```
@NoArgsConstructor을 사용하면

```java
  public class User{
    private String name;
    private int age;

    public User(){}
  }

```

## @AllArgsConstructor
- 클래스의 모든 필드 값을 파라미터로 받는 생성자 생성
- 클래스의 모든 필드를 한 번에 초기화할 수 있다.
  ```java
  @AllArgsConstructor
  public class User{
    private String name;
    private int age;
  }
  ```
@AllArgsConstructor 사용하면

```java
  public class User{
    private String name;
    private int age;

    public User(String name, int age){
      this.name = name;
      this.age = age;
    }
  }

```

## @RequiredArgsConstructor
- final, @NonNull로 선언된 필드만을 파라미터로 받는 생성자 자동 생성
- 클래스가 의존하는 필드 초기화 가능

  ```java
  @RequiredArgsConstructor
  public class User{
    private final String name;
    private final int age;
    privagte String phone;
  }
  ```
@RequiredArgsConstructor 사용하면

```java
  public class User{
    private final String name;
    private final int age;
    privagte String phone;

    public User(final String name, final int age){
      this.name = name;
      this.age = age;
    }
  }

```

# JPA 어노테이션

## @Entity
- 클래스를 테이블과 매핑 시키기 위한 어노테이션
- 데이터베이스 테이블과 매핑되어 데이터베이스에 CRUD 작업을 수행

## @Table
- 엔티티와 매핑할 테이블 지정.
- 속성으로는
  - name
      - 매핑한 테이블 이름
      - default : 개체명
  - catalog
      - catalog 기능이 있는 DB에서 catalog매핑
      - default : DB명
   
  - schema
      - schema기능이 있는 DB에서 schema 매핑
  - uniqueConstraints
      - DDL생성시 unique제약조건 걸 수 있음
      - 스키마 자동 생성 기능 이용하여 DDL만들 때 사용
   
## @Id
- 엔티티의 필드를 테이블의 기본 키에 매핑하는 역할

















