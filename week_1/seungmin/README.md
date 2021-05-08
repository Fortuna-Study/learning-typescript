## 👉 Chapter 1: 타입스크립트와 개발 환경 만들기

### 📚 자바스크립트에 타입 기능이 있으면 좋은 이유
- 오늘날 소프트웨어는 상당히 복잡하므로 보통 여러 사람이나 팀이 협럭해 하나의 제품을 개발한다.
- 항상 코드를 작성한 쪽과 사용하는 쪽 사이에 커뮤니케이션이 중요하다.
- A라는 개발자가 다음과 같은 코드르 만들었다.

```js
function makePerson(name, age) {}
```

- B라는 개발자가 이 코드를 이용하려고 다음 코드를 만들어 실행했을 때 오류가 발생했다면, B 개발자는 오류의 원인이 무엇인지 찾기가 어렵다.

```js
makePerson(32, 'Jack');
```

- 그런데 처음 코드를 다음처럼 타입스크립트의 타입 가능을 이용해 구현했다면 이러한 문제는 발생하지 않았을 것이다.

```ts
function makePerson(name: string, age: number) {}
```

- 그리고 **타입스크립트 컴파일러는 문제의 원인이 어디에 있는지 친절하게 알려주므로 코드를 좀 더 수월하게 작성할 수 있다.**


### 📚 트랜스파일
- ESNext 자바스크립트 소스코드는 바벨(Babel)이라는 트랜스파일러를 거치면 ES5 자바스크립트 코드로 변환된다.
- 바벨과 유사하게 타입스크립트 소스코드는 **TSC(TypeScript complier)라는 트랜스파일러**를 통해 ES5 자바스크립트 코드로 변환된다.
- 트랜스파일러는 텍스트로 된 소스코드를 바이너리 코드를 바꿔주는 컴파일러와 구분하기 위해 생긴 용어이다.

### 📚 타입 주석과 타입 추론
- 다음 코드에서 변수 `n`뒤에는 콜론(`:`)과 타입 이름이 있다.   
- 이것이 **타입 주석**(**type annotation**)이라고 한다.   

```ts
let n: number = 1;
```

- 타입스크립트는 변수의 타입 부분이 생략되면 대입 연산자의 **오른쪽 값을 분석해 왼쪽 변수의 타입을 결정한다.**   
- 이를 **타입 추론**(**type inference**)이라고 한다.   

```ts
let m = 2;
```

### 📚 인터페이스 


```ts
interface Person {
  name: string;
  age?: number; // optional
}

let person: Person = { name: 'Jane' };
```

### 📚 튜플
- 튜플과 배열은 물리적으로는 같지만 배열에 저장되는 아이템의 데이터 타입이 **모두 같으면 배열**, **다르면 튜플**이다.

```ts
let numberArray: number[] = [1, 2, 3]; // 배열
let tuple: [boolean, number, string] = [true, 1, 'Ok']; // 튜플
```

### 📚 제네릭 타입
- 제네릭 타입은 **다양한 타입을 한꺼번에 취급**할 수 있게 해준다.

```ts
class Container<T> {
  constructor(public value: T) {};
}

let numberContainer: Container<number> = new Container<number>(1);
let stringContainer: Container<string> = new Container<string>('Hello World');
```

### 📚 대수 타입
- 대수 타입은 크게 합집합 타입(union), 교집합 타입(intersection) 두 가지가 있다.

```ts
type NumberOrString = number | string;
type AnimalAndPerson = Animal & Person;
```


---

- [Chapter 1 정리](https://github.com/saseungmin/typescript_programming_study/tree/master/Chapter%201)

## 👉 Chapter 2: 타입스크립트 프로젝트 생성과 관리

### 📚 tsconfig.json 파일 살펴보기
- `tsconfig.json` 파일을 보면 다음처럼 구성되어있다.

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "esModuleInterop": true,
    "target": "ES5",
    "moduleResolution": "node",
    "outDir": "dist",
    "baseUrl": ".",
    "sourceMap": true,
    "downlevelIteration": true,
    "noImplicitAny": false,
    "paths": { "*": ["node_modules/*"] }
  },
  "include": ["src/**/*"]
}
```

- `compilerOptions` 항목은 `tsc` 명령 형식에서 **옵션**을 나타내고, `includes` 항목은 **대상 파일 목록**을 나타낸다.
- `include`의 `["src/**/*"]`는 `src` 하위 디렉터리에 있는 모든 파일을 컴파일 대상으로 포함한다는 의미이다.

#### 🎈 module 키
- 자바스크립트 모듈은 웹 브라우저에서는 **AMD**(**asynchronous module definition**) 방식으로 동작하고, Node.js처럼 웹 브라우저가 아닌 환경에서는 **CommonJS** 방식으로 동작한다.
- `tsconfig.json` 파일에서 `compilerOptions` 항목의 `module` 키는 동작 대상 플랫폼이 웹 브라우저인지 Node.js인지를 구분해 그에 맞는 모듈 방식으로 컴파일하려는 목적으로 설정한다.

#### 🎈 moduleResolution 키
- `module`키의 값이 `commonjs`이면 Node.js에서 동작하는 것을 의미하므로, **`moduleResolution`키값은 항상 `node`로 설정**한다.
- 반면에 `module`키값이 `amd`이면 **`moduleResolution`키값은 `classic`으로 설정**한다.

#### 🎈 target 키
- `target` 키에는 **트랜스파일할 대상 자바스크립트 버전을 설정**한다.

#### 🎈 baseUrl과 outDir 키
- `baseUrl`과 `outDir` 키에는 **트랜스파일된 ES5 자바스크립트 파일을 저장하는 디렉터리를 설정한다.**

#### 🎈 paths 키
- `paths` 키에는 **소스 파일의 `import`문에서 `form` 부분을 해석할 때 찾아야 하는 디렉터리를 설정한다.**
- `import` 문에 찾아야 하는 소스가 외부 패키지이면 `node_modules` 디렉터리에서 찾아야 하므로 키값에 `node_modules/*`도 포함한다.

#### 🎈 esModuleInterop 키
- 오픈소스 자바스크립트 라이브로리 중에는 웹 브라우저에서 동작한다는 가정으로 만들어진 것이 있는데, 이들은 `CommonJS` 방식으로 동작하는 타입스크립트 코드에 혼란을 줄 수 있다. 그렇기 때문에 AMD 방식을 전제로해서 구현된 라이브러리 같은 경우를 사용하려면 `esModuleInterop`키 값을 반드시 `true`로 설정해야 한다.

#### 🎈 sourceMap 키
- `sourceMap` 키 값이 `true`이면 트랜스파일 티렉터리에는 `.js` 파일 이외에도 `.js.map` 파일이 만들어진다.
- 이 소스맵 파일은 **변환된 자바스크립트 코드가 타입스크립트 코드의 어디에 해당하는지를 알려준다.**

#### 🎈 downlevelIteration 키
- 생성기(generator)라는 타입스크립트 구문이 있는데, 이 구문이 정성적으로 동작하려면 `downlevelIteration` 키값을 반드시 `true`로 설정해야 한다.

---

- [Chapter 2 정리](https://github.com/saseungmin/typescript_programming_study/tree/master/Chapter%202)

## 👉 Chapter 3: 객체와 타입

### 📚 클래스 선언문
- 타입스크립트는 객체지향 언어에서 흔히 볼 수 있는 `class`, `private`, `public`, `protected`, `implements`, `extend`와 같은 키워드를 제공한다.
- 다음 코드는 `name`과 `age`라는 속성을 가진 클래스를 선언한다.

```ts
class Person1 {
  name: string;
  age?: number;
}

let jack1: Person1 = new Person1();
jack1.name = 'Jack';
jack1.age = 32;
console.log(jack1); // Person1 { name: 'Jack', age: 32 }
```

### 📚 생성자
- 타입스크립트 클래스는 `constructor`라는 이름의 특별한 메서드를 포함하는데, 이를 **생성자**라고 한다.

```ts
class Person2 {
  constructor(public name: string, public age?: number) {};
}

let jack2: Person2 = new Person2('Jack', 32);
console.log(jack2); // Person2 { name: 'Jack', age: 32 }
```

### 📚 인터페이스 구현
- 타입스크립트 클래스는 인터페이스를 구현할 수 있다.
- 클래스가 인터페이스를 구현할 때는 다음처럼 `implements` 키워드를 사용한다.

```ts
interface IPerson4 {
  name: string;
  age?: number;
}

class Person4 implements IPerson4 {
  constructor(public name: string, public age?: number) {};
}

export let jack4: IPerson4 = new Person4('Jack', 32);
console.log(jack4); // Person4 { name: 'Jack', age: 32 }
```

### 📚 추상 클래스
- 추상 클래스는 자신의 속성이나 메서드 앞에 `abstract`를 붙여 나를 상속하는 다른 클래스에서 이 속성이나 메서드를 구현하게 한다.

```ts
abstract class AbstractPerson5 {
  abstract name: string;
  constructor(public age?: number) {}
}
```

### 📚 클래스의 상속
- 다음 `Person5` 클래스는 `AbstractPerson5` 추상 클래스를 상속해 `AbstractPerson5`가 구현한 `age`를 얻고, `AbstractPerson5`를 상속받는 클래스가 구현해야 할 `name` 속성을 구현한다.

```ts
abstract class AbstractPerson5 {
  abstract name: string;
  constructor(public age?: number) {}
}

class Person5 extends AbstractPerson5 {
  constructor(public name: string, age?: number) {
    super(age); // 부모 클래스의 생성자를 호출
  }
}

let jack5: Person5 = new Person5('Jack', 32);
console.log(jack5); // Person5 { name: 'Jack', age: 32 }
```

### 📚 static 속성
- 다음처럼 정적 속성은 점 표기법을 사용해 값을 얻거나 설정할 수 있다.

```ts
class A {
  static initValue = 1;
}

let initVal = A.initValue; // 1
```

### 📚 타입 변환
- 타입이 있는 언어들은 특정 타입의 변숫값을 다른 타입의 값으로 변환할 수 있는 기능을 제공한다. 이를 **타입 변환**(**type conversion**)이라고 한다.

```ts
let person: object = { name: 'Jack', age: 32 };

(<{name:string}>person).name;
```

### 📚 타입 단언
- 그런데 타입스크립트는 타입 변환이 아닌 **타입 단언**(**type assertion**)이라는 용어를 사용한다.
- 타입 단언문은 다음 두 가지 형태가 있다.

```ts
interface INameable {
  name: string
};

let obj: object = { name: 'Jack' };

let name1 = (<INameable>obj).name;
let name2 = (obj as INameable).name;

console.log(name1, name2); // Jack Jack
```

- 둘의 차이는 형태만 다를 뿐 내용상으로는 같다.

---

- [Chapter 3 정리](https://github.com/saseungmin/typescript_programming_study/tree/master/Chapter%203)