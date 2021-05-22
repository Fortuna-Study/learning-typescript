## 10. 제네릭 프로그래밍

### 10-2 제네릭 타입 제약
- 264p 위의 예제 다시보기
- new()는 생성자 함수를 나타냄
```typescript
  // 생성자 타이핑 예제
  
  // 1
  new() => T
  
  // 2
  {new(): T}
```

- `K extends of T`: 타입 K가 T의 속성 이름이다.


### 10-4 
- 생성자 함수에 이런 것도 가능하네.
```typescript
  [new Bird, new Fish].forEach((flyOrSwim));
```


### 10-5
- F-바운드 다형성(F-bound polymorphism): this 타입으로 인한 다형성
- F-바운드 타입: 자신을 구현하거나 상속하는 서브타입을 포함하는 타입
  - interface 함수의 반환타입이 this
  - interface 함수를 상속하는 클래스에서 해당 interface 함수를 구현하므로
  
