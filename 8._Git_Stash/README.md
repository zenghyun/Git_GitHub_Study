## Git Stash
커밋하지 않은 변경사항들을 임시 저장하도록 해주고 불필요한 커밋으로 이력이 지저분해지는 것 없이 나중에
돌아올 수 있게 해준다. 

일반적으로, 아직 완성되지 않았거나 커밋할 준비가 되지 않은 것에 대해서도 커밋을 할 수 있다.

<br>

```
git stash
```
어느 시점에서, 커밋하지 않은 모든 변경사항, 등록했거나 또는 등록하지 않은 변경사항을 모두 stash 한다. 

즉, 변경사항을 기억했다가 워킹 디렉토리의 변경사항을 되돌리는 것이다. 그래서 더이상 그 변경사항을 보지 못하지만 stash에서는 여전히 사용 가능해서 나중에 돌아와서 되찾을 수 있게 해준다.

<br>

## Git stash pop 
```
git stash pop

⭐️ 특정 stash만 pop 하기 
git stash pop stash@{num}
```
stash에서 가장 최근에 stash한 변경사항들을 삭제하고 어디에 있든지 내 복사본에 다시 적용할 수 있게 해준다. (변경사항들을 적용하면 자동으로 stash에서 삭제된다.)

또한 몇몇 변경사항을 stash하기 위해 git stash를 사용할 수 있고 잠시 후 다른 branch나 stash 했던 동일한 branch에 다시 적용할 수도 있다.  

<br>

## Git stash apply
``` 
git stash apply 

⭐️ 특정 stash만 apply 하기 
git stash apply stash@{num}
```
git stash pop과 비슷하지만 apply는 stash 영역에 stash를 남겨둔다. 

즉, 변경사항들은 여전히 stash에 있고, 여러 곳에 변경사항들을 다시 적용할 수 있게 해준다. 

<br>

## Git stash list 
```
git stash list 
```

내가 등록한 stash 목록들을 볼 수 있다. 

<br>

## Git stash drop 
```
git stash drop stash@{num}
```
git stash drop 다음에 stash 식별자 또는 인덱스를 넣으면 된다.

<br>

## Git stash clear
```
git stash clear
```
이 명령은 stash에 있는 모든 것을 없애버린다. 