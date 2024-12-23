## Dependency Inversion Principle, DIP
- 두가지 규칙으로 이루어짐.
    1. 상위 모듈은 하위 모듈에 의존해서는 안 됩니다. 둘 다 추상화에 의존해야 합니다.
    2. 추상화는 세부사항에 의존해서는 안 됩니다. 세부 사항이 추상화에 따라 달라져야 합니다.
- 클라이언트 코드가 구현 클래스에 의존하지 말고, 인터페이스에 의존하라는 뜻.
    - 모든 의존성을 없애라는게 아니다. 인터페이스 상대로만 의존하도록!
    - 모든 다른 클래스와의 소통은 “**인터페이스를 거쳐**” 소통되도록!
- 앞에서 이야기한 역할(Role)에 의존하게 해야 한다는 것과 같다. 객체 세상도 클라이언트가 인터페이스에 의존해야 유연하게 구현체를 변경할 수 있다! 구현체에 의존하게 되면 변경이 아주 어려워진다.
- **의존관계에는 사이클이 없어야 한다.**
    - 할리우드 원칙
- 클라이언트와 서버만 있으면 클라이언트는 서버의 구현체에 의존해야 한다.
    - ex) MemberRepository m = new **MemoryMemberRepository**();
    - 클라이언트가 MemoryMemberRepository의 존재를 알아야 하는 상황.
    - DIP 위반.
- 실제 적용 방법
    - 추상 레이어(인터페이스)를 따라 구현되도록
![[Pasted image 20241212200820.png]]
- 생성자를 통한 “의존성 주입 받기”