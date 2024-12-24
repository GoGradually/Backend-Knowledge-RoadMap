- 메서드 재정의가 정확하게 잘 되었는지 컴파일러가 체크하는데 사용한다.
```java
@Target(ElementType.METHOD)  
@Retention(RetentionPolicy.SOURCE)  
public @interface Override {  
}
```
- 컴파일 에러 체크용으로만 사용되고, 바로 사라진다.