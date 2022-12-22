# [JavaScript] const {value} = event.target;

# const {value} = event.target;
> 아니.. 이게 뭐지? 내가 알던 `const`선언과 다르다! 이건 어떻게 해석해야 할까?

역시 Stack Overflow! 궁금증이 해결되었다.
[https://stackoverflow.com/questions/55188257/const-name-value-event-target-what-does-this-mean](Link)

아래는 예시이다.
```
let person = {
  name: 'David',
  age: 15,
  job: 'Programmer'
}

const { name, age } = person; // Takes the property/method from the object

console.log(name); // Prints 'David'
console.log(age); // Prints '15'
```

해석은 "person이라는 object에서 name과 age를 가져와라! 로 할 수 있다.

그러므로
`const {value} = event.target;`는 

> event.target 에서 value를 가져와라! 

로 해석할 수 있는것!

```
const{ 엄마는외계인 } = 베스킨라빈스 // 베스킨라빈스에서 엄마는 외계인을 가져와라!!!
```