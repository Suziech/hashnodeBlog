# [CSS] Add gradation effect to your text!

[๐ linear-gradient() MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient)

# ๊ธ์จ์ ๊ทธ๋ผ๋ฐ์ด์ ํจ๊ณผ๋ฃ๊ธฐ ๋ฐฉ๋ฒ! 
1. ์ผ๋จ ์์๋ก `<h1>` tag๋ฅผ ์ฌ์ฉํ์ฌ ๊ธ์จ๋ฅผ ์์ฑ
2. CSS์ ์์์ `background`์์ฑ์ `linear-gradient`๋ฅผ ์จ์ฃผ๊ณ  ๊ทธ๋ผ๋ฐ์ด์ ๋ฐฉํฅ(to right)์ ์จ์ค ํ ์ํ๋์๊น์ ๋ฃ์ด์ค๋ค. 
3. `-webkit-background-clip: text;`์ ์ถ๊ฐ! ์ด ๋ถ๋ถ์ด ๋ฐ๋ก ๊ธ์จ์ ์๊น์ ๋ฃ์ด์ค ์ ์๋ค! 
4. `color: transparent;`๋ฅผ ์ถ๊ฐ๋ก ๋ฃ์ด์ค๋ค. 
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669274053950/u7ttT193u.png align="left")

```html
<!--html-->
<h1>์๋ํ์ธ์! ๋ง๋์ ๋ฐ๊ฐ์ต๋๋ค. ์ ๊ธฐํ๋ค์!</h1>
```
```css
/*css*/
h1 {
    background:linear-gradient(
      to right,
      red,
      orange,
      yellow,
      green,
      blue,
      indigo,
      purple
    );
-webkit-background-clip: text;
  color: transparent;

}
```
> ์ค์ค ๋๋ฌด ์ ๊ธฐํด! CSS๋ ์ด๋ฐ๊ฒ ์ ๋ง ์ฌ๋ฏธ์๋๋ฏ ๐ค