# [JavaScript] parseInt

> The parseInt() function parses a string argument and returns an integer of the specified radix (the base in mathematical numeral systems).

`parseInt()`는 string argument를 분석하여 정수(int)를 return 해준다.

### Syntax
> parseInt(string)<br>
parseInt(string, radix)

문제를 풀다가 3진법을 10진법으로 바꿔주어야 하는 부분이 있었다. 

`201.toString(10) (201은 3진법임)`

하지만 계속 잘못 된 숫자가 나왔고 실력이 좋으신 분의 도움을 받아 `parseInt()`의 존재에 대해 알게 되었다!!

사실 위의 식(toString)은 10진법인 정수를 뭘로 어떤 진법으로 바꾸는가를 해결해 주는 식이였다.
> n.toString(binary / tarnary / decimal ...)

다른진법의 수를 10진법, 즉 정수로 바꿔주려면 parseInt를 사용해주어야 한다.

```
parseInt(내가 바꾸고싶은 n진법의 수, 현재 진법) 즉, parseInt(201, 3) // expected :  19
```

분명히 몇일 뒤 까먹을게 분명하니 다시 한번 또 풀어봐야지!! 🤓