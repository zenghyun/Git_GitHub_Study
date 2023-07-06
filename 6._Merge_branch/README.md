## Merge branch 

### Merging
Branching makes it super easy to work within self-contained contexts, but often we want to incorporate changes from one branch into another 

**git merge 명령을 사용하여 이 작업을 수행할 수 있습니다**

### - 특정 커밋이 아닌 분기를 병합합니다.

### - 우리는 항상 현재 HEAD 브랜치에 병합합니다.

<br>

```
git switch master 

git merge branch-name
```
<br>

## 병합하는데 발생할 수 있는 문제들

### 1. master에서 branch한 이후 내가 작업한 것들을 병합시키려고 할 때 master에서 다른 작업을 이미 commit 한경우 

<br>

```
          (master)
        -- commmit 1
master
        -- commit 1 -- commit 2 
                     (new branch) <- HEAD
```
 
 ### 2. 병합 충돌 ( 한 브랜치에서 누군가가 파일을 수정했고, 병합하고 있는 두 번째 브랜치에서 누군가 동일한 파일을 삭제한 경우 )

 **깃은 자동적으로 병합하는 방법을 알지 못해서 어떤 것을 유지하고 어떤 것을 제거해야 하는지 결정하지 못한다.**

 <br>

 ```
 CONFLICT (content): Merge conflict in blah.txt
 Automatic merge failed; fix conflicts and then commit the result.
 ```

 ### Resolving Conflicts 
 Whenever you encounter merge conflicts, follow these steps to resolve them: 

 1. Open up the file(s) with merge conflicts
 2. Edit the file(s) to remove the conflicts. Decide which branch's content you want to keep in each conflict. Or keep the content from both. 
 3. Remove the conflict "markers" in the document
 4. Add your changes and then make a commit! 

