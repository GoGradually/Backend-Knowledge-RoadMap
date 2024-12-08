- JPQL 함수
    
    - JPQL 기본 함수
        
        - CONCAT
            
        - SUBSTRING
            
        - TRIM
            
            - 공백 제거
                
        - LOWER, UPPER
            
        - LENGTH
            
        - LOCATE
            
            - 문자열 위치 찾기
                
        - ABS, SQRT, MOD
            
        - SIZE, INDEX(JPA 용도)
            
    - JPQL 사용자 정의 함수 (DB 종속적인 함수)
        
        - 사용자 정의 함수로 등록해두기
            
            - Dialect 직접 만들기
                
            - 하이버네이트의 방언 상속받기
                
            - 거기에 사용자 정의 함수 등록해두기
                
        - DB 방언으로 바꾸기
            
        - function('사용자 정의 함수 이름', 값)