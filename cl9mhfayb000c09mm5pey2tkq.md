# [TypeScript] Installation & basics

# TypeScript for HTML/CSS/JS

### installation
```
npm install -g typescript
```

### create an folder ending with `.ts`

### auto complier for js
```
tsc -w
```

### How to use typescript in html
```
<script src="compiledAsJS.js"></script>
```

# TypeScript for React
- adding TS 
```
npm install --save typescript @types/node @types/react @types/react-dom @types/jest
```
- installing React with TS 
```
npx create-react-app my-app --template typescript
```

# TypeScript for Vue
```
vue add typescript
```

- to use

```
<script lang="ts">
  
</script>
```

# TypeScript
```
let 이름 :string = 'kim'

let 이름 :string[] = ['kim', 'park']
let 나이 :{ age : number } = { age : number }

let 이름 :string | number = 'kim';

type nameType = string | number;
let 이름 :nameType = 'kim';

type NameType = 'kim' | 'park;
let 이름 :NameType = 'kim';

function 함수명(x :number) :number{
  return x * 2

//에러
function 함수명(x :number | string) {
  return x * 2
}

//가능
function 함수명(x :number | string) {
  if (typeof x === 'number'){
    return x * 2
  } 
}
}

type Member = [number, boolean];
let john:Member = [100, false]

type MyObject = {
  name? : string,
  age : number
}
let 철수 :MyObject = { 
  name : 'kim',
  age : 50
}

type MyObject = {
  [key :string] : number,
}
let 철수 :MyObject = { 
  age : 50,
  weight : 100,
}

class Person {
  name;
  constructor(name :string){
    this.name = name;
  }
}
```