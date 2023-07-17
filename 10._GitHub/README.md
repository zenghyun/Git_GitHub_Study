# What is Github?
Github는 git 저장소를 위한 호스팅 플랫폼입니다. Github에 나만의 Git 리포지토리를 배치하고 어디서나 액세스하고 전 세계 사람들과 공유할 수 있습니다.

호스팅 리포지토리 외에도 Github는 Git에 고유하지 않은(그러나 매우 유용한) 추가 협업 기능을 제공합니다. 기본적으로 Github는 사람들이 저장소를 공유하고 협업할 수 있도록 도와줍니다.

<br>

## Cloning
So far we've created out own Git repositiories from scratch, but often we want to get a local copy of an existing repository instead.

To do this, we can clone a remote repositiory hosted on Github or similar websites. All we need is a URL that we can tell Git to clone for use.

```
git clone <URL>
```

git clone은 여러분의 컴퓨터에 없는 저장소를 여러분의 컴퓨터로 가져옵니다. 

<br>

### Git Clone에 권한이 필요한가요? 
리포지토리가 공개된 경우 누구나 Github에서 리포지토리를 복제할 수 있습니다. 리포지토리를 시스템에 로컬로 복제하기 위해 소유자 또는 공동 작업자일 필요는 없습니다. Github의 URL만 있으면 됩니다.

Github 리포지토리에 자신의 변경 사항을 적용하는 것은 완전히 다른 이야기입니다!
그렇게 하려면 권한이 필요합니다!

**git clone은 모든 호스팅 저장소에서 사용가능하다는 것을 잊으면 안됩니다.**

<br>

## Remote
Github에 무엇이든 푸시하기 전에 Github의 원격 저장소에 대해 Git에게 알려야 합니다. 푸시할 "목적지"를 설정해야 합니다.

Git에서는 이러한 "대상"을 원격이라고 합니다. 각 원격은 단순히 호스팅된 저장소가 있는 URL입니다.

<br>

## Viewing Remotes


```
git remote -v
```
<br>

To view any existing remotes for you repository, we can run git remote or git remote -v (verbose. for more info)

This just displays a list of remtoes. If you haven't added any remotes yet, you won't see anything!

<br>

## Adding A New Remote 
A remote is really two things: a URL and a label. 

To add a new remote, we need to provide both to Git. 

```
git remote add <name> <url>
```

<br>

```
git remote add origin
https://github.com/blah/repo.git 
```

**표준 이름은 origin입니다.**

<br>

### Origin? 
Origin is a conventional Git remote name, but is is not at all special. 

It's just a name for a URL.

When we clone a Github repo, the default remote name setup for us is called origin. You can change it. Most people leave it.

<br>

## Pushing 
Now that we have a remote set up, let's push some work up a Github! To do this, we need to use the git push command. 

We need to specify the remote we want to push up to AND the specific local branch we want to push up to that remote. 

<br>

```
git push <remote> <branch>
```

<br>

### Push In Detail
While we often want to push a local branch up to a remote branch of the same name, we don't have to!

To push our local pancake branch up to a remote branch called waffle we could do: **git push origin pancake:waffle**

### 기존 branch를 다른 branch에 push하는 방법
```
git push <remote>
<local-branch>:<remote-branch>

git push origin pancake:waffle
```
<br>

git push를 쓰고, origin 같은 원격을 쓰고, 로컬 브랜치를 특정하고, :를 쓰고, 원격 브랜치를 씁니다. 

**이렇게 하면 로컬 브랜치를 다른 이름의 원격 브랜치로 푸시할 수 있습니다.**

<br>

## The -u option
-u 옵션을 사용하면 푸시하는 브랜치의 업스트림을 설정할 수 있습니다. 로컬 브랜치를 Github의 브랜치에 연결하는 링크로 생각할 수 있습니다.

git push -u origin master를 실행하면 로컬 마스터 브랜치의 업스트림이 설정되어 원본 리포지토리의 마스터 브랜치를 추적합니다.

```
git push -u origin master
```

<br>

## master branch -> main branch
master branch로 만든 것을 main branch로 이름을 바꾸는 법 

```
git branch -M main
```
