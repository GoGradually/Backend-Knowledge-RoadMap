- 스프링부트에서 새로 정의한 JAR 방식
- JAR 안에 JAR 를 포함시킬 수 있도록 한다.
	- main 메소드 실행 시, 자바에서 직접 JAR 를 압축 해제하여 읽을 수 있도록 만든다.
	- `org.springframework.boot.loader.JarLauncher`가 해당 기능을 수행한다.
- `./gradlew build` 로 빌드한다.

- `MANIFEST.MF`
```
Manifest-Version: 1.0
Main-Class: org.springframework.boot.loader.JarLauncher // 메인 메소드 대치
--------------스프링부트 추가-------------------
Start-Class: hello.boot.BootApplication
Spring-Boot-Version: 3.0.2
Spring-Boot-Classes: BOOT-INF/classes/
Spring-Boot-Lib: BOOT-INF/lib/
Spring-Boot-Classpath-Index: BOOT-INF/classpath.idx
Spring-Boot-Layers-Index: BOOT-INF/layers.idx
-----------------------------------------------
Build-Jdk-Spec: 17
```
- 참고: `boot-0.0.1-SNAPSHOT-plain.jar`는 외부 라이브러리를 포함하지 않는 우리가 개발한 순수한 JAR 를 의미한다.