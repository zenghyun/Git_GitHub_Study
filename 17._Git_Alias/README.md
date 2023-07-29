## Adding Aliases
Git 별칭을 쉽게 설정하여 Git 경험을 좀 더 간단하고 빠르게 만들 수 있습니다.

예를 들어 "git commit"을 입력하는 대신 별칭 "git ci"를 정의할 수 있습니다.

또는 사용자 지정 형식의 커밋 로그를 출력하는 사용자 지정 git lg 명령을 정의할 수 있습니다.

```
.gitconfig 

[alias]
    s = status
    l = log
    showmebranches = branch 
    cm = commit -m
```

[Git Alias Guthub Repo](https://github.com/GitAlias/gitalias)
[Must Have Git Aliases Blog Post](https://www.durdn.com/blog/2012/11/22/must-have-git-aliases-advanced-examples/)
[The Ultimate Git Alias Setup](https://gist.github.com/mwhite/6887990)