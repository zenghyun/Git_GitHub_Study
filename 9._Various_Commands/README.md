# Various Commands

## Git Checkout
```
git checkout <commit-hash>

or

git checkout HEAD~? (1개, 2개, 3개 ~~~ )
```
내가 입력한 commit hash 시점으로 돌아갈 수 있다. (돌아가서 확인이 가능하다.)

<br>

## Detached HEAD
이럴 때 당황하지 마세요! 그것은 나쁜 것이 아닙니다!

**두 가지 옵션이 있습니다.**
1. 분리된 HEAD에 머물면서 이전 커밋의 내용을 검사합니다.
둘러보기, 파일 보기 등
2. HEAD를 다시 부착하기 전에 있던 곳을 떠나서 다시 돌아갑니다.
3. 새 분기를 만들고 전환합니다. HEAD가 더 이상 분리되지 않으므로 이제 변경 사항을 적용하고 저장할 수 있습니다.

**git check commit hash**를 하면, 분리된 헤드로 다시 돌아간다. 
여기서 내가 확인하고 싶은 것을 확인할 수 있고, switch를 사용해 돌아갈 수도 있고, master 또는 원하는 branch로 돌아갈 수 있다. 또는 과거에 commit을 기반으로 하는 새 branch도 만들 수 있다. 

<br>

## 다시 돌아가는 법 
```
git switch master

git switch - 
```

**git switch -** 를 사용하면 내가 가장 최근에 있던 branch로 이동한다. 

<br>

## Git Checkout HEAD <file>
```
git checkout HEAD <file> or <file>s

or

git checkout -- <file> or <file>s
```
파일의 변경 사항을 취소할 수 있는 명령어이다.

위의 명령어를 사용하면 내가 마지막으로 commit 한 시점의 파일 내용으로 돌아가게 된다. 

<br>

## Git Restore
git restore is a brand new Git command that helps with undoing operations.

Because it is so new, most of the existing Git tutorials and books do not mention it, but it is worth knowing! 

Recall that git checkout does a million different things, which many git users find very confusing. git restore was introduced alongside git switch as alternatives to some of the uses for checkout.

<br>

git restore로 할 수 있는 첫 번째 작업은, 저장소의 마지막 커밋 이후의 변경 사항을 삭제하는 것이다. 

```
git restore <file-name>
```
이 명령어를 사용하면 가장 최근의 commit 이후의 파일로 복원된다.

<br>

```
git restore --source HEAD~? <file-name>
```
해당 file의 내용을 헤드에서 커밋 ?개 전에 있던 모습으로 복원한다. 

<br>

git restore로 할 수 있는 두 번째 작업은, 스테이지된 파일을 언스테이지 하는 것이다. 

```
git restore --staged <file-name>
```

예를 들어, git add .를 통해 모든 파일을 stage에 올렸을 때 특정 파일만 unstage 하고 싶으면 
이 명령어를 사용하면 된다. 

<br>

## Git Reset
git reset 명령은 저장소를 특정 커밋으로 다시 재설정한다.

📌 일반 재설정 
<br>

```
git reset <commit-hash>
```

commit 기록만 삭제되고 변경사항은 삭제되지 않는다. 변겅 사항은 여전히 워킹 디렉토리에 남아있다. 

이 방법은 잘못된 branch에 commit을 했을 때 유용하다. 

이 명령어를 실행 후 내가 원하는 branch에 가서 다시 commit하면 되는 것이다. 

<br>

📌 강한 재설정 
<br>

```
git reset --hard <commit-hash>
```
commit과 변경 사항까지 워킹 디렉토리에서 제거 시킨다.

<br>

## Git Revert(되돌리기)
<br>

```
git revert <commit-hash>
```

git revert와  git reset은 변경 사항을 취소한다는 점에서는 같지만 다른 부분이 있다. 

revert와 reset은 모두 commit에서 변경 사항을 취소하지만, 그렇게 만드는 방법은 다르다. 

reset은 commit을 완전히 제거하고 브랜치 포인터를 뒤로 이동시킨다.

 반면 revert은 완전히 새로운 commit을 만든다. 그 새로운 commit에서 이전 commit의 변경 사항을 취소한다. 

 즉 revert는 commit의 기록은 남겨두지만, 변경 사항은 취소하는 것이다. 