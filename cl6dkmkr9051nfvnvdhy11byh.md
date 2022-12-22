# [Git] conflict 💥

> 처음으로 team project는 어떻게 관리되는지 배울 수 있는 날이였다. 그 중에 conflict란 무엇이고 어떻게 하는지 알게 되었는데 잊어버리고 싶지 않아서 블로그에 작성한다.

# 개념
- branch와 branch의 merge과정에서, 동일한 내용을 각자 다르게 변경한 이력이 있을 때 변경 이력들끼리 발생하는 충돌

# 발생과정
1. feature A가 작업 완료(Hello Dog) 뒤, github으로 `git push origin feature/A` -> `pull request` -> `merge`
2. feature B도 작업 완료(Hello Cat) 뒤, github으로 `git push origin feature/B` -> `pull request` -> 💥 conflict 발생!

3. local의 master는 아직 업데이트 되어있지 않는 상황이라 github에 있는 master와 맞춰 준 후, conflict를 해결해야함

4. 3번을 위해서 로컬에서 작업 branch를 main으로 바꾼 후(`git checkout main`) main을 local로 pull 하고 (`git pull origin main`) 우리가 변경해 주고 싶은 feature B로 다시 branch를 변경(`git checkout feature/B`) 그다음 마스터에 있는 작업 내역을 B에게 합쳐야 함(`git merge main`) 

정리하면<br>
`git checkout main`<br>
⬇️<br>
`git pull origin main`<br>
⬇️<br>
`git checkout feature/B`<br>
⬇️<br>
`git merge main`<br>

5. Conflict 해결(코드 수정)

6. add -> commit -> push

# 해결방법
  ```
<<< (current change)
=== (구분선)
>>> (incoming change)
```

- conflict가 있는 부분을 위와 같이 표시해 주는데 저 표시들을 다 제거한 뒤, 원하는 최종 형태로 만들고 **SAVE**.

> 자꾸 save를 까먹고 git add commit push를 진행해 주어 아무것도 변하지 않아 혼동스러웠다. 저장하는것을 꼭 기억하자!

