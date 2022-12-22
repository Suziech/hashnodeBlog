# [Git] Rebase

### What is git rebase?
- Rebasing is the process of moving or combining a sequence of commits to a new base commit. Rebasing is most useful and easily visualised in the context of a feature branching workflow.

merge대신 rebase를 사용해서 commit을 한개로 유지할 수 있다.

### @ local Main

`git pull origin main`

### @ local feature

- `git rebase -i main`
- 제일 오래된 commit 'pick' 그리고 나머지 commit들은 s 입력해서 squash 진행
- conflict가 있으면 해결 후 `git push origin feature`