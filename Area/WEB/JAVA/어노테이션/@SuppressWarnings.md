```java
@Retention(RetentionPolicy.SOURCE)  
public @interface SuppressWarnings {  
    String[] value();  
}
```
- 경고를 억제한다.
- 빨간줄, 노란줄을 제거한다.
-  개발자가 해당 문제를 잘 알고 있기 때문에, 더는 경고하지 말라고 지시하는 애노테이션


### `@SuppressWarnings` 에 사용하는 대표적인 값
- **all**: 모든 경고를 억제
- **deprecation**: 사용이 권장되지 않는(deprecated) 코드를 사용할 때 발생하는 경고를 억제
- **unchecked**: 제네릭 타입과 관련된 unchecked 경고를 억제
- **serial**: Serializable 인터페이스를 구현할 때 serialVersionUID 필드를 선언하지 않은 경우 발생하는 경고를 억제
- **rawtypes**: 제네릭 타입이 명시되지 않은(raw) 타입을 사용할 때 발생하는 경고를 억제
- **unused**: 사용되지 않는 변수, 메서드, 필드 등을 선언했을 때 발생하는 경고를 억제