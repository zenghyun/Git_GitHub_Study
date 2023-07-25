## Git rebase
There are two main ways to use the git rebase command: 
- as an alternative to merging
- as a cleanup tool

git rebase와 git merge 두 명령어 모두 두 개의 브랜치를 하나로 병합하는 기능을 제공합니다.

## Rebasing!
We can instead rebase the feature branch onto the master branch. This moves the entire feature branch so that it BEGINS at the tip of the master branch. All of the work is still there, but we have re-written history.

Instead of using a merge commit, rebasing rewrites history by creating new commits for each of the original feature branch commits.

```
git switch feature
git rebase master
```

feature branch의 베이스는 master branch의 끝부분이 됩니다. 

즉, master branch가 끝나는 지점에서 feature branch가 시작하고 깔끔한 결과물을 얻게 됩니다. 

rebase를 하면 merge commit를 생성하는 대신 history를 재구성합니다.

git rebase master를 하면 master branch 자체를 rebase하는 것이 아니라 master branch 위로 내 branch를 올리는 작업입니다. 

즉, feature branch에 있는 commit들은 재생성되고 history는 master branch 끝에서 새롭게 쓰이는 것이다. 

### Rebase를 하면 안되는 경우 
다른 사람과 공유된 커밋을 리베이스하지 마십시오. 커밋을 이미 Github에 푸시한 경우.. 팀의 아무도 해당 커밋을 사용하지 않는다는 확신이 들지 않는 한 리베이스하지 마십시오.

다시 말해, 만약 여러분이 깃허브에 어떤 브랜치를 푸시했고 다른 사람들이 이미 여러분의 커밋을 자기 컴퓨터로 당겨 갔다고 생각해보세요.

여러분이 리베이스 하는 순간 히스토리가 재작성되니 커밋이 새로 생성되는 것입니다.

다른 개발자들의 컴퓨터에 반영된 깃 히스토리를 다시 서로 맞추는 건 무척 번거롭습니다. 

다른 이들의 히스토리엔 없는 커밋을 여러분이 가지게 되는 것이기 떄문이죠. (반대로 다른 사람이 가지고 있는 커밋은 내게는 없습니다.)

즉, 이미 공유한 커밋을 리베이스하지 마세요.

리베이스는 다른 사람들에겐 없는 커밋이 내 컴퓨터에 있을 때 사용하세요. 

버그를 고치든 기능을 추가하든 무엇이든지 간에 피처 브랜치에서 작업을 한다면 그 피처 브랜치를 마스터 브랜치로 아니면 다른 브랜치로 리베이스 하는 것은 괜찮습니다.

마스터 브랜치를 건드는 것은 아니니까요. 새 베이스로 삼으려는 브랜치를 변경하지 않아요

이미 얘기했든 리베이스 명령어를 실행하는 브랜치가 변경되는 브랜치 입니다. 

## Interactive Rebase 

### Rewriting History
때로는 커밋을 다시 작성, 삭제, 이름 변경 또는 재정렬(공유하기 전에)하고 싶을 때가 있습니다. 

git rebase를 사용하여 이 작업을 수행할 수 있습니다!


```
git rebase -i HEAD~n
```


-i 옵션과 함께 git rebase를 실행하면 대화형 모드로 들어가 커밋을 편집하고, 파일을 추가하고, 커밋을 삭제하는 등의 작업을 수행할 수 있습니다. 커밋을 다시 작성하려는 시점을 지정해야 합니다.

또한 다른 브랜치로 리베이스하지 않는다는 점에 유의하십시오. 대신, 현재 기반이 되는 HEAD에 일련의 커밋을 리베이스하고 있습니다.

### What Now? 
In our text editor, we'll see a list of commits alongside a list of commands that we can choose from. Here are a couple of the more commonly used commands:

- pick : use the commit
- reword : use the commit, but edit the commit message
- edit : use commit , but stop for amending
- fixup : use commit contents but meld it into previous commit and discard the commit message
- drop : remove commit