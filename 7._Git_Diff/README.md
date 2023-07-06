## Git Diff 
git diff 명령을 사용하여 커밋, 분기, 파일, 작업 디렉토리 간의 변경 사항을 볼 수 있습니다!

우리는 종종 git status 및 git log와 같은 명령과 함께 git diff를 사용하여 리포지토리에 대한 더 나은 그림과 시간이 지남에 따라 변경된 방식을 얻습니다.

Git Diff는 저장소에서 어떤 작업도 하지 않습니다. (git status나 git log처럼 아무런 영향도 미치지 않습니다. 순수하게 정보를 주는 명령어 입니다.)

<br>

```
git diff
```

<br>
이 명령은 다음 커밋을 위해 스테이지에 등록되지 않은 워킹 디렉토리의 변경사항을 모두 나열합니다. 

따라서 워킹 디렉토리와 스테이지 영역 간 변경 사항을 비교합니다.

<br>

## Git Diff HEAD

이 명령은 마지막 커밋, 가장 나중에 실행된 커밋부터 워킹 디렉토리에 있는 모든 변경사항의 목록들을 나열해줍니다. 

```
git diff HEAD
```

git diff HEAD를 실행하면, HEAD가 가리키는 최신 커밋과 워킹 디렉토리 간의 차이를 보여줍니다.

<br>
    
## Git Diff --Staged  or --cached 
두 옵션 모두 스테이지에 등록된 변경사항만을 보여줍니다. 

```
git diff --staged

git diff --cached
```

<br>

## Diff-ing Specific Files 
diff의 범위를 특정 파일이나 파일들로 좁혀서 확인할 수 있습니다. 

```
git diff HEAD [filename]

git diff --staged [filename]
```

<br>

## Comparing Branches 
gif diff를 사용해서 두 브랜치를 비교할 수도 있습니다. 

```
git diff branch1..branch2

or 

git diff branch1 branch2
```
<br>

## Comparing Commits  
두 커밋 간에 어떤 것이 변경되었는지 알려줍니다. 

```
git diff commit1..commit2

or

git diff commit1 commit2 
```