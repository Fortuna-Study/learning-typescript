## ๐ Chapter 1: ํ์์คํฌ๋ฆฝํธ์ ๊ฐ๋ฐ ํ๊ฒฝ ๋ง๋ค๊ธฐ

### ๐ ์๋ฐ์คํฌ๋ฆฝํธ์ ํ์ ๊ธฐ๋ฅ์ด ์์ผ๋ฉด ์ข์ ์ด์ 
- ์ค๋๋  ์ํํธ์จ์ด๋ ์๋นํ ๋ณต์กํ๋ฏ๋ก ๋ณดํต ์ฌ๋ฌ ์ฌ๋์ด๋ ํ์ด ํ๋ญํด ํ๋์ ์ ํ์ ๊ฐ๋ฐํ๋ค.
- ํญ์ ์ฝ๋๋ฅผ ์์ฑํ ์ชฝ๊ณผ ์ฌ์ฉํ๋ ์ชฝ ์ฌ์ด์ ์ปค๋ฎค๋์ผ์ด์์ด ์ค์ํ๋ค.
- A๋ผ๋ ๊ฐ๋ฐ์๊ฐ ๋ค์๊ณผ ๊ฐ์ ์ฝ๋๋ฅด ๋ง๋ค์๋ค.

```js
function makePerson(name, age) {}
```

- B๋ผ๋ ๊ฐ๋ฐ์๊ฐ ์ด ์ฝ๋๋ฅผ ์ด์ฉํ๋ ค๊ณ  ๋ค์ ์ฝ๋๋ฅผ ๋ง๋ค์ด ์คํํ์ ๋ ์ค๋ฅ๊ฐ ๋ฐ์ํ๋ค๋ฉด, B ๊ฐ๋ฐ์๋ ์ค๋ฅ์ ์์ธ์ด ๋ฌด์์ธ์ง ์ฐพ๊ธฐ๊ฐ ์ด๋ ต๋ค.

```js
makePerson(32, 'Jack');
```

- ๊ทธ๋ฐ๋ฐ ์ฒ์ ์ฝ๋๋ฅผ ๋ค์์ฒ๋ผ ํ์์คํฌ๋ฆฝํธ์ ํ์ ๊ฐ๋ฅ์ ์ด์ฉํด ๊ตฌํํ๋ค๋ฉด ์ด๋ฌํ ๋ฌธ์ ๋ ๋ฐ์ํ์ง ์์์ ๊ฒ์ด๋ค.

```ts
function makePerson(name: string, age: number) {}
```

- ๊ทธ๋ฆฌ๊ณ  **ํ์์คํฌ๋ฆฝํธ ์ปดํ์ผ๋ฌ๋ ๋ฌธ์ ์ ์์ธ์ด ์ด๋์ ์๋์ง ์น์ ํ๊ฒ ์๋ ค์ฃผ๋ฏ๋ก ์ฝ๋๋ฅผ ์ข ๋ ์์ํ๊ฒ ์์ฑํ  ์ ์๋ค.**


### ๐ ํธ๋์คํ์ผ
- ESNext ์๋ฐ์คํฌ๋ฆฝํธ ์์ค์ฝ๋๋ ๋ฐ๋ฒจ(Babel)์ด๋ผ๋ ํธ๋์คํ์ผ๋ฌ๋ฅผ ๊ฑฐ์น๋ฉด ES5 ์๋ฐ์คํฌ๋ฆฝํธ ์ฝ๋๋ก ๋ณํ๋๋ค.
- ๋ฐ๋ฒจ๊ณผ ์ ์ฌํ๊ฒ ํ์์คํฌ๋ฆฝํธ ์์ค์ฝ๋๋ **TSC(TypeScript complier)๋ผ๋ ํธ๋์คํ์ผ๋ฌ**๋ฅผ ํตํด ES5 ์๋ฐ์คํฌ๋ฆฝํธ ์ฝ๋๋ก ๋ณํ๋๋ค.
- ํธ๋์คํ์ผ๋ฌ๋ ํ์คํธ๋ก ๋ ์์ค์ฝ๋๋ฅผ ๋ฐ์ด๋๋ฆฌ ์ฝ๋๋ฅผ ๋ฐ๊ฟ์ฃผ๋ ์ปดํ์ผ๋ฌ์ ๊ตฌ๋ถํ๊ธฐ ์ํด ์๊ธด ์ฉ์ด์ด๋ค.

### ๐ ํ์ ์ฃผ์๊ณผ ํ์ ์ถ๋ก 
- ๋ค์ ์ฝ๋์์ ๋ณ์ `n`๋ค์๋ ์ฝ๋ก (`:`)๊ณผ ํ์ ์ด๋ฆ์ด ์๋ค.   
- ์ด๊ฒ์ด **ํ์ ์ฃผ์**(**type annotation**)์ด๋ผ๊ณ  ํ๋ค.   

```ts
let n: number = 1;
```

- ํ์์คํฌ๋ฆฝํธ๋ ๋ณ์์ ํ์ ๋ถ๋ถ์ด ์๋ต๋๋ฉด ๋์ ์ฐ์ฐ์์ **์ค๋ฅธ์ชฝ ๊ฐ์ ๋ถ์ํด ์ผ์ชฝ ๋ณ์์ ํ์์ ๊ฒฐ์ ํ๋ค.**   
- ์ด๋ฅผ **ํ์ ์ถ๋ก **(**type inference**)์ด๋ผ๊ณ  ํ๋ค.   

```ts
let m = 2;
```

### ๐ ์ธํฐํ์ด์ค 


```ts
interface Person {
  name: string;
  age?: number; // optional
}

let person: Person = { name: 'Jane' };
```

### ๐ ํํ
- ํํ๊ณผ ๋ฐฐ์ด์ ๋ฌผ๋ฆฌ์ ์ผ๋ก๋ ๊ฐ์ง๋ง ๋ฐฐ์ด์ ์ ์ฅ๋๋ ์์ดํ์ ๋ฐ์ดํฐ ํ์์ด **๋ชจ๋ ๊ฐ์ผ๋ฉด ๋ฐฐ์ด**, **๋ค๋ฅด๋ฉด ํํ**์ด๋ค.

```ts
let numberArray: number[] = [1, 2, 3]; // ๋ฐฐ์ด
let tuple: [boolean, number, string] = [true, 1, 'Ok']; // ํํ
```

### ๐ ์ ๋ค๋ฆญ ํ์
- ์ ๋ค๋ฆญ ํ์์ **๋ค์ํ ํ์์ ํ๊บผ๋ฒ์ ์ทจ๊ธ**ํ  ์ ์๊ฒ ํด์ค๋ค.

```ts
class Container<T> {
  constructor(public value: T) {};
}

let numberContainer: Container<number> = new Container<number>(1);
let stringContainer: Container<string> = new Container<string>('Hello World');
```

### ๐ ๋์ ํ์
- ๋์ ํ์์ ํฌ๊ฒ ํฉ์งํฉ ํ์(union), ๊ต์งํฉ ํ์(intersection) ๋ ๊ฐ์ง๊ฐ ์๋ค.

```ts
type NumberOrString = number | string;
type AnimalAndPerson = Animal & Person;
```


---

- [Chapter 1 ์ ๋ฆฌ](https://saseungmin.github.io/reading_books_record_repository/docs/typescript/do-it-typescript/chapter-1)

## ๐ Chapter 2: ํ์์คํฌ๋ฆฝํธ ํ๋ก์ ํธ ์์ฑ๊ณผ ๊ด๋ฆฌ

### ๐ tsconfig.json ํ์ผ ์ดํด๋ณด๊ธฐ
- `tsconfig.json` ํ์ผ์ ๋ณด๋ฉด ๋ค์์ฒ๋ผ ๊ตฌ์ฑ๋์ด์๋ค.

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

- `compilerOptions` ํญ๋ชฉ์ `tsc` ๋ช๋ น ํ์์์ **์ต์**์ ๋ํ๋ด๊ณ , `includes` ํญ๋ชฉ์ **๋์ ํ์ผ ๋ชฉ๋ก**์ ๋ํ๋ธ๋ค.
- `include`์ `["src/**/*"]`๋ `src` ํ์ ๋๋ ํฐ๋ฆฌ์ ์๋ ๋ชจ๋  ํ์ผ์ ์ปดํ์ผ ๋์์ผ๋ก ํฌํจํ๋ค๋ ์๋ฏธ์ด๋ค.

#### ๐ module ํค
- ์๋ฐ์คํฌ๋ฆฝํธ ๋ชจ๋์ ์น ๋ธ๋ผ์ฐ์ ์์๋ **AMD**(**asynchronous module definition**) ๋ฐฉ์์ผ๋ก ๋์ํ๊ณ , Node.js์ฒ๋ผ ์น ๋ธ๋ผ์ฐ์ ๊ฐ ์๋ ํ๊ฒฝ์์๋ **CommonJS** ๋ฐฉ์์ผ๋ก ๋์ํ๋ค.
- `tsconfig.json` ํ์ผ์์ `compilerOptions` ํญ๋ชฉ์ `module` ํค๋ ๋์ ๋์ ํ๋ซํผ์ด ์น ๋ธ๋ผ์ฐ์ ์ธ์ง Node.js์ธ์ง๋ฅผ ๊ตฌ๋ถํด ๊ทธ์ ๋ง๋ ๋ชจ๋ ๋ฐฉ์์ผ๋ก ์ปดํ์ผํ๋ ค๋ ๋ชฉ์ ์ผ๋ก ์ค์ ํ๋ค.

#### ๐ moduleResolution ํค
- `module`ํค์ ๊ฐ์ด `commonjs`์ด๋ฉด Node.js์์ ๋์ํ๋ ๊ฒ์ ์๋ฏธํ๋ฏ๋ก, **`moduleResolution`ํค๊ฐ์ ํญ์ `node`๋ก ์ค์ **ํ๋ค.
- ๋ฐ๋ฉด์ `module`ํค๊ฐ์ด `amd`์ด๋ฉด **`moduleResolution`ํค๊ฐ์ `classic`์ผ๋ก ์ค์ **ํ๋ค.

#### ๐ target ํค
- `target` ํค์๋ **ํธ๋์คํ์ผํ  ๋์ ์๋ฐ์คํฌ๋ฆฝํธ ๋ฒ์ ์ ์ค์ **ํ๋ค.

#### ๐ baseUrl๊ณผ outDir ํค
- `baseUrl`๊ณผ `outDir` ํค์๋ **ํธ๋์คํ์ผ๋ ES5 ์๋ฐ์คํฌ๋ฆฝํธ ํ์ผ์ ์ ์ฅํ๋ ๋๋ ํฐ๋ฆฌ๋ฅผ ์ค์ ํ๋ค.**

#### ๐ paths ํค
- `paths` ํค์๋ **์์ค ํ์ผ์ `import`๋ฌธ์์ `form` ๋ถ๋ถ์ ํด์ํ  ๋ ์ฐพ์์ผ ํ๋ ๋๋ ํฐ๋ฆฌ๋ฅผ ์ค์ ํ๋ค.**
- `import` ๋ฌธ์ ์ฐพ์์ผ ํ๋ ์์ค๊ฐ ์ธ๋ถ ํจํค์ง์ด๋ฉด `node_modules` ๋๋ ํฐ๋ฆฌ์์ ์ฐพ์์ผ ํ๋ฏ๋ก ํค๊ฐ์ `node_modules/*`๋ ํฌํจํ๋ค.

#### ๐ esModuleInterop ํค
- ์คํ์์ค ์๋ฐ์คํฌ๋ฆฝํธ ๋ผ์ด๋ธ๋ก๋ฆฌ ์ค์๋ ์น ๋ธ๋ผ์ฐ์ ์์ ๋์ํ๋ค๋ ๊ฐ์ ์ผ๋ก ๋ง๋ค์ด์ง ๊ฒ์ด ์๋๋ฐ, ์ด๋ค์ `CommonJS` ๋ฐฉ์์ผ๋ก ๋์ํ๋ ํ์์คํฌ๋ฆฝํธ ์ฝ๋์ ํผ๋์ ์ค ์ ์๋ค. ๊ทธ๋ ๊ธฐ ๋๋ฌธ์ AMD ๋ฐฉ์์ ์ ์ ๋กํด์ ๊ตฌํ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ๊ฐ์ ๊ฒฝ์ฐ๋ฅผ ์ฌ์ฉํ๋ ค๋ฉด `esModuleInterop`ํค ๊ฐ์ ๋ฐ๋์ `true`๋ก ์ค์ ํด์ผ ํ๋ค.

#### ๐ sourceMap ํค
- `sourceMap` ํค ๊ฐ์ด `true`์ด๋ฉด ํธ๋์คํ์ผ ํฐ๋ ํฐ๋ฆฌ์๋ `.js` ํ์ผ ์ด์ธ์๋ `.js.map` ํ์ผ์ด ๋ง๋ค์ด์ง๋ค.
- ์ด ์์ค๋งต ํ์ผ์ **๋ณํ๋ ์๋ฐ์คํฌ๋ฆฝํธ ์ฝ๋๊ฐ ํ์์คํฌ๋ฆฝํธ ์ฝ๋์ ์ด๋์ ํด๋นํ๋์ง๋ฅผ ์๋ ค์ค๋ค.**

#### ๐ downlevelIteration ํค
- ์์ฑ๊ธฐ(generator)๋ผ๋ ํ์์คํฌ๋ฆฝํธ ๊ตฌ๋ฌธ์ด ์๋๋ฐ, ์ด ๊ตฌ๋ฌธ์ด ์ ์ฑ์ ์ผ๋ก ๋์ํ๋ ค๋ฉด `downlevelIteration` ํค๊ฐ์ ๋ฐ๋์ `true`๋ก ์ค์ ํด์ผ ํ๋ค.

---

- [Chapter 2 ์ ๋ฆฌ](https://saseungmin.github.io/reading_books_record_repository/docs/typescript/do-it-typescript/chapter-2)

## ๐ Chapter 3: ๊ฐ์ฒด์ ํ์

### ๐ ํด๋์ค ์ ์ธ๋ฌธ
- ํ์์คํฌ๋ฆฝํธ๋ ๊ฐ์ฒด์งํฅ ์ธ์ด์์ ํํ ๋ณผ ์ ์๋ `class`, `private`, `public`, `protected`, `implements`, `extend`์ ๊ฐ์ ํค์๋๋ฅผ ์ ๊ณตํ๋ค.
- ๋ค์ ์ฝ๋๋ `name`๊ณผ `age`๋ผ๋ ์์ฑ์ ๊ฐ์ง ํด๋์ค๋ฅผ ์ ์ธํ๋ค.

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

### ๐ ์์ฑ์
- ํ์์คํฌ๋ฆฝํธ ํด๋์ค๋ `constructor`๋ผ๋ ์ด๋ฆ์ ํน๋ณํ ๋ฉ์๋๋ฅผ ํฌํจํ๋๋ฐ, ์ด๋ฅผ **์์ฑ์**๋ผ๊ณ  ํ๋ค.

```ts
class Person2 {
  constructor(public name: string, public age?: number) {};
}

let jack2: Person2 = new Person2('Jack', 32);
console.log(jack2); // Person2 { name: 'Jack', age: 32 }
```

### ๐ ์ธํฐํ์ด์ค ๊ตฌํ
- ํ์์คํฌ๋ฆฝํธ ํด๋์ค๋ ์ธํฐํ์ด์ค๋ฅผ ๊ตฌํํ  ์ ์๋ค.
- ํด๋์ค๊ฐ ์ธํฐํ์ด์ค๋ฅผ ๊ตฌํํ  ๋๋ ๋ค์์ฒ๋ผ `implements` ํค์๋๋ฅผ ์ฌ์ฉํ๋ค.

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

### ๐ ์ถ์ ํด๋์ค
- ์ถ์ ํด๋์ค๋ ์์ ์ ์์ฑ์ด๋ ๋ฉ์๋ ์์ `abstract`๋ฅผ ๋ถ์ฌ ๋๋ฅผ ์์ํ๋ ๋ค๋ฅธ ํด๋์ค์์ ์ด ์์ฑ์ด๋ ๋ฉ์๋๋ฅผ ๊ตฌํํ๊ฒ ํ๋ค.

```ts
abstract class AbstractPerson5 {
  abstract name: string;
  constructor(public age?: number) {}
}
```

### ๐ ํด๋์ค์ ์์
- ๋ค์ `Person5` ํด๋์ค๋ `AbstractPerson5` ์ถ์ ํด๋์ค๋ฅผ ์์ํด `AbstractPerson5`๊ฐ ๊ตฌํํ `age`๋ฅผ ์ป๊ณ , `AbstractPerson5`๋ฅผ ์์๋ฐ๋ ํด๋์ค๊ฐ ๊ตฌํํด์ผ ํ  `name` ์์ฑ์ ๊ตฌํํ๋ค.

```ts
abstract class AbstractPerson5 {
  abstract name: string;
  constructor(public age?: number) {}
}

class Person5 extends AbstractPerson5 {
  constructor(public name: string, age?: number) {
    super(age); // ๋ถ๋ชจ ํด๋์ค์ ์์ฑ์๋ฅผ ํธ์ถ
  }
}

let jack5: Person5 = new Person5('Jack', 32);
console.log(jack5); // Person5 { name: 'Jack', age: 32 }
```

### ๐ static ์์ฑ
- ๋ค์์ฒ๋ผ ์ ์  ์์ฑ์ ์  ํ๊ธฐ๋ฒ์ ์ฌ์ฉํด ๊ฐ์ ์ป๊ฑฐ๋ ์ค์ ํ  ์ ์๋ค.

```ts
class A {
  static initValue = 1;
}

let initVal = A.initValue; // 1
```

### ๐ ํ์ ๋ณํ
- ํ์์ด ์๋ ์ธ์ด๋ค์ ํน์  ํ์์ ๋ณ์ซ๊ฐ์ ๋ค๋ฅธ ํ์์ ๊ฐ์ผ๋ก ๋ณํํ  ์ ์๋ ๊ธฐ๋ฅ์ ์ ๊ณตํ๋ค. ์ด๋ฅผ **ํ์ ๋ณํ**(**type conversion**)์ด๋ผ๊ณ  ํ๋ค.

```ts
let person: object = { name: 'Jack', age: 32 };

(<{name:string}>person).name;
```

### ๐ ํ์ ๋จ์ธ
- ๊ทธ๋ฐ๋ฐ ํ์์คํฌ๋ฆฝํธ๋ ํ์ ๋ณํ์ด ์๋ **ํ์ ๋จ์ธ**(**type assertion**)์ด๋ผ๋ ์ฉ์ด๋ฅผ ์ฌ์ฉํ๋ค.
- ํ์ ๋จ์ธ๋ฌธ์ ๋ค์ ๋ ๊ฐ์ง ํํ๊ฐ ์๋ค.

```ts
interface INameable {
  name: string
};

let obj: object = { name: 'Jack' };

let name1 = (<INameable>obj).name;
let name2 = (obj as INameable).name;

console.log(name1, name2); // Jack Jack
```

- ๋์ ์ฐจ์ด๋ ํํ๋ง ๋ค๋ฅผ ๋ฟ ๋ด์ฉ์์ผ๋ก๋ ๊ฐ๋ค.

---

- [Chapter 3 ์ ๋ฆฌ](https://saseungmin.github.io/reading_books_record_repository/docs/typescript/do-it-typescript/chapter-3)
