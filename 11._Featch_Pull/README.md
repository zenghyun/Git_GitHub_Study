# Fetch & Pull

### Remote Tracking Branches 
"이 원격 저장소와 마지막으로 통신할 때 x 분기가 가리키는 위치는 여기입니다."

<"remote">/<"branch"> 패턴을 따릅니다.
- origin / master는 origin이라는 원격 리포지토리의 마스터 브랜치 상태를 참조합니다.
- upstream / logoRedesign은 upstream(공통 원격 이름)이라는 이름의 원격에서 logoRedesign 분기의 상태를 참조합니다.

<br>

### Remote Branches 

```
git branch -r 
// ex origin/master
```
Run git branch -r to view the remote branches our local repository knows about.

```
git checkout origin/main 
```
github에서 git clone해서 받아온 시점의 상태를 확인할 수 있음 or 마지막 push 이후 상태를 볼 수 있음


<br>


리포지토리를 복제하면 해당 시점의 프로젝트에 대한 모든 데이터와 Git 기록이 있습니다. 그러나 그것이 내 작업 공간에 모두 있다는 의미는 아닙니다!

github repo에는 pupies라는 브랜치가 있지만 git branch를 실행하면 내 컴퓨터에서 볼 수 없습니다! 내가 보는 모든 것은 마스터 브랜치입니다. 무슨 일이야?

```
git branch
*master
```

**git branch -r 하면 모든 branch를 볼 수 있다.**

즉, 내 로컬 저장소는 모든 브랜치에 대해 알고 있으며 원격 추적 참조가 있다. 내 저장소는 그것들을 알고 있지만, 나는 완전한 브랜치를 보지 못한다. 

보려면 어떻게 해야할까? 

### It's super easy! 
Run git switch <"remote-branch-name"> to create a new local branch from the remote branch of the same name. 

git switch puppies makes me a local puppies branch AND sets it up to track the remote branch origin/puppies. 

```
git switch puppies
```

git switch 명령 다음에 아직 로컬에는 존재하지 않을수도 있지만 원격 브랜치에는 있는 이름으로 브랜치 이름을 써주면, 깃이 로컬에서 그 브랜치를 만들고, 동일한 이름의 원격 브랜치를 추적하도록 자동으로 설정한다는 것입니다.

<br>


### Note! 
the new command git switch makes this super easy to do! 
It used to be slightly more complicated using git checkout 

```
git checkout --track origin/puppies
```
<br>

## Git Fetch 
git fetch는 원격 변경 사항을 가져옵니다. ( 깃허브 저장소에서 항목들을 로컬 저장소로 가져옵니다. )

fetch를 사용하면 원격 저장소에서 변경 사항을 다운로드할 수 있지만 이러한 변경 사항은 작업 파일에 자동으로 통합되지 않습니다.

변경 사항을 로컬 리포지토리에 병합하지 않고도 다른 사람들이 작업한 내용을 볼 수 있습니다.

"가서 Github에서 최신 정보를 얻으십시오. 그러나 내 작업 디렉토리를 망치지 마십시오."라고 생각하면 됩니다.

```
git fetch <remote>
```

git fetch <"remote"> 명령은 특정 원격 저장소에서 분기와 기록을 가져옵니다. 원격 추적 분기만 업데이트합니다.

git fetch origin은 원본 원격 저장소에서 모든 변경 사항을 가져옵니다.

또한 하나의 브랜치만 fetch할 수도 있습니다.

```
git fetch <remote> <branch>
```

### 변경된 사항 확인법 

```
git checkout remote/branch
```

<br>

## Git Pull 
git pull은 원격 저장소에서 변경 사항을 검색하는 데 사용할 수 있는 또 다른 명령입니다. 가져오기와 달리 pull은 원격에서 검색된 모든 변경 사항으로 HEAD 분기를 실제로 업데이트합니다.

"Github에서 데이터를 다운로드하고 해당 변경 사항으로 내 로컬 리포지토리를 즉시 업데이트합니다."

```
git pull <remote> <branch>
```
pull 하려면 git pull <"remote"> <"branch">를 사용하여 풀하려는 특정 원격 및 분기를 지정합니다. git merge와 마찬가지로 이 명령을 어디에서 실행하느냐가 중요합니다. **우리가 실행하는 분기가 무엇이든 변경 사항이 병합되는 위치입니다.**

git pull origin master는 오리진의 마스터 브랜치에서 최신 정보를 가져오고 해당 변경 사항을 현재 브랜치에 병합합니다.

<br>

## Git Pull 및 Merge 충돌 
가끔 깃허브에 없는 로컬 작업을 할 때가 있고, 깃허브에는 우리 로컬에 없는 커밋이 있을 수 있습니다. 따라서 풀 다운할 때 충돌이 발생할 수 있습니다.

<br>

## An even easier syntax!
가져올 특정 원격 또는 분기를 지정하지 않고 git pull을 실행하면 git은 다음을 가정합니다.
- remote는 기본적으로 origin으로 설정됩니다.
- 분기는 현재 분기에 대해 구성된 추적 연결로 기본 설정됩니다.

참고: 이 동작을 구성할 수 있으며 추적 연결을 수동으로 변경할 수 있습니다.

대부분의 사람들은 그런 것들을 건드리지 않습니다.

```
git pull
```