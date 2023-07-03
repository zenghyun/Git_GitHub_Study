## Branch 

### 브랜치란 무엇인가? 
브랜치 깃은 프로젝트에서 일종의 타임라인 같은 것이라고 생각할 수 있다. 
브랜치는 우리가 원할 때마다 별도의 콘텍스트를 생성할 수 있게 해준다. 이를 통해 새로운 것을 시도해 볼 수도 있고, 동시에 다양한 아이디어들을 가지고 작업할 수도 있다. 

한 브랜치에서 어떤 작업을 하든 다른 브랜치에는 영향을 미치지 않는다. 

<br>

## Master branch
새로운 프로젝트를 생성했을 때, 자동으로 생성되는 기본 브랜치 이름 

<br>

## Master? Main? 
In 2020, Github renamed the default branch from master to main. 
The default Git branch name is still master, though the Git team is exploring a potential change. We will circle back to this shortly

## What'is Head? 
Head는 깃 용어 중 하나이며, 특히 저장소에서 현재 우리의 위치를 가리키는 포인터이다. 그리고 브랜치 레퍼런스를 가리킨다. 

<br>

## Git branch 
이 명령은 저장소에 있는 현재 존재하는 브랜치 목록을 보여주고, 새 브랜치를 생성하거나 다른 브랜치로 이동하지는 않는다. 
```
git branch 
```
<br>

## Creating branches 
'git branch 브랜치 이름' 명령은 HEAD가 현재 가리키고 있는 브랜치에 새 브랜치를 생성한다.

이는 어디에서 작업하고 있는지, 브랜치를 생성할 때 HEAD가 생성하는 브랜치에 어떤 영향을 미치는지 말해준다. 

현재 브랜치의 위치, 우리가 작업하고 있는 브랜치는 아주 중요한 것이고 아주 큰 차이를 만든다.

※ branch-name은 공백을 포함하면 안된다.

### 📌 작업하는 브랜치가 어디에서 분기된 것인지가 굉장히 중요하다.
```
git branch branch-name
```

<br>

## Switching Branches
Once you have created a new branch, use git switch branch-name to switch to it 

```
git switch branch-name
```

<br>

## Another way of switching ? (옛날 방식이지만 여전히 작동한다.)
### checkout이 너무 많은 기능을 수행하자 branch를 이동하는 명령어만 따로 빼놓은게 switch이다.
Historically, we used git checkout branch-name to switch branches. This still works.

The checkout command does a milion additional things, so the decision was made to add a standalone switch command which is much simpler. 

You will see older tutorials and docs using checkout rather than switch. Both now work.

<br>

## Creating & Switching 
Use git switch with the -c flag to create a new branch AND switch to it all in one go. 

Remember -c as short for "create"

```
git switch -c branch-name 
```
위의 명령어를 사용하면 브랜치를 생성하고 그 브랜치로 이동하는 작업을 한번에 실행할 수 있다. 
<br>

## git commit -a -m 
git commit -a -m 명령어는 git에서 수정된 모든 파일을 스테이징(Staging) 영역에 추가하고 커밋(commit)하는데 사용된다. 

```
git commit -a -m
```

## git branch -d branch-name 
branch를 삭제할 때 쓰는 명령어 

branch를 삭제하기 위해서는 다른 branch로 이동한 후에 진행해야 한다. 
```
git branch -d branch-name
```

<br>

## git branch -D branch-name 
병합 상태에 상관없이 브랜치를 강제 삭제하고 싶을 때 사용하는 명령어
```
git branch -D branch-name
```

<br>

## git branch -m branch-name
삭제할 때와 다르게 이름을 변경하려면 그 브랜치에서 작업해야 한다. 
```
git branch -m branch-name
```


