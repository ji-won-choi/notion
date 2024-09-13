# DAOImpl

Spring Framework에선 DAOImpl을 사용했다. 부트로 넘어가면서 없어졌는데, sqlsession으로 접근하던 sql을 
@Mapper 어노테이션으로 매핑하여 사용 가능하기 때문이다.

# @Mapper

: 주로 SQL 매퍼 인터페이스를 정의할 때 사용. 데이터베이스의 SQL 쿼리를 자바 메소드와 매핑하는 역할을 하기 때문에
주요 기능
SQL 매핑: XML 또는 애노테이션을 이용해 SQL 쿼리를 자바 인터페이스의 메소드에 매핑.
자동 구현 생성: @Mapper가 지정된 인터페이스의 구현체를 MyBatis가 런타임에 자동으로 생성.
의존성 주입: Spring에서는 @Mapper를 사용하면 이 인터페이스가 Spring의 빈으로 자동 등록되어 의존성 주입이 가능.

* @MapperScan : 여러 개의 매퍼를 사용하기 위해 사용.
