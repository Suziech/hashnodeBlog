# [Git] conflict ๐ฅ

> ์ฒ์์ผ๋ก team project๋ ์ด๋ป๊ฒ ๊ด๋ฆฌ๋๋์ง ๋ฐฐ์ธ ์ ์๋ ๋ ์ด์๋ค. ๊ทธ ์ค์ conflict๋ ๋ฌด์์ด๊ณ  ์ด๋ป๊ฒ ํ๋์ง ์๊ฒ ๋์๋๋ฐ ์์ด๋ฒ๋ฆฌ๊ณ  ์ถ์ง ์์์ ๋ธ๋ก๊ทธ์ ์์ฑํ๋ค.

# ๊ฐ๋
- branch์ branch์ merge๊ณผ์ ์์, ๋์ผํ ๋ด์ฉ์ ๊ฐ์ ๋ค๋ฅด๊ฒ ๋ณ๊ฒฝํ ์ด๋ ฅ์ด ์์ ๋ ๋ณ๊ฒฝ ์ด๋ ฅ๋ค๋ผ๋ฆฌ ๋ฐ์ํ๋ ์ถฉ๋

# ๋ฐ์๊ณผ์ 
1. feature A๊ฐ ์์ ์๋ฃ(Hello Dog) ๋ค, github์ผ๋ก `git push origin feature/A` -> `pull request` -> `merge`
2. feature B๋ ์์ ์๋ฃ(Hello Cat) ๋ค, github์ผ๋ก `git push origin feature/B` -> `pull request` -> ๐ฅ conflict ๋ฐ์!

3. local์ master๋ ์์ง ์๋ฐ์ดํธ ๋์ด์์ง ์๋ ์ํฉ์ด๋ผ github์ ์๋ master์ ๋ง์ถฐ ์ค ํ, conflict๋ฅผ ํด๊ฒฐํด์ผํจ

4. 3๋ฒ์ ์ํด์ ๋ก์ปฌ์์ ์์ branch๋ฅผ main์ผ๋ก ๋ฐ๊พผ ํ(`git checkout main`) main์ local๋ก pull ํ๊ณ  (`git pull origin main`) ์ฐ๋ฆฌ๊ฐ ๋ณ๊ฒฝํด ์ฃผ๊ณ  ์ถ์ feature B๋ก ๋ค์ branch๋ฅผ ๋ณ๊ฒฝ(`git checkout feature/B`) ๊ทธ๋ค์ ๋ง์คํฐ์ ์๋ ์์ ๋ด์ญ์ B์๊ฒ ํฉ์ณ์ผ ํจ(`git merge main`) 

์ ๋ฆฌํ๋ฉด<br>
`git checkout main`<br>
โฌ๏ธ<br>
`git pull origin main`<br>
โฌ๏ธ<br>
`git checkout feature/B`<br>
โฌ๏ธ<br>
`git merge main`<br>

5. Conflict ํด๊ฒฐ(์ฝ๋ ์์ )

6. add -> commit -> push

# ํด๊ฒฐ๋ฐฉ๋ฒ
  ```
<<< (current change)
=== (๊ตฌ๋ถ์ )
>>> (incoming change)
```

- conflict๊ฐ ์๋ ๋ถ๋ถ์ ์์ ๊ฐ์ด ํ์ํด ์ฃผ๋๋ฐ ์  ํ์๋ค์ ๋ค ์ ๊ฑฐํ ๋ค, ์ํ๋ ์ต์ข ํํ๋ก ๋ง๋ค๊ณ  **SAVE**.

> ์๊พธ save๋ฅผ ๊น๋จน๊ณ  git add commit push๋ฅผ ์งํํด ์ฃผ์ด ์๋ฌด๊ฒ๋ ๋ณํ์ง ์์ ํผ๋์ค๋ฌ์ ๋ค. ์ ์ฅํ๋๊ฒ์ ๊ผญ ๊ธฐ์ตํ์!

