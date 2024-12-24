- 서브쿼리 (SubQuery)
    
    - 쿼리 안에 들어간 select쿼리
        
        - 기본적으로 임시 테이블같은 테이블 형태의 resultSet이지만
            
        - 최종 resultSet의 결과가 하나라면 값으로 사용 가능
            
        - 적절한 resultSet을 적절하게 사용해야 함
            
    - 서브쿼리에서 지원하는 함수
        
        - [NOT] EXISTS (subquery)
            
            - 서브 쿼리에 결과가 존재하면 참
                
        - ALL (subquery)
            
            - 모두 만족하면 참
                
        - ANY, SOME (subquery)
            
            - 조건을 하나라도 만족하면 참
                
        - [NOT] IN (subquery)
            
            - 서브 쿼리의 결과 중 하나라도 같은 것이 있으면 참
                
    - JPA 서브 쿼리의 한계
        
        - FROM 절의 서브쿼리는 Hibernate 6 이상부터만 가능함
            
            - 되도록이면 서브쿼리를 join으로 풀어서 해결하기