## Reflogs (Reference Log)
git은 분기 및 기타 참조의 팁이 repo에서 업데이트된 시점을 기록합니다.

git reflog 명령을 사용하여 이러한 참조 로그를 보고 업데이트할 수 있습니다.

### Limitations 
Git은 로컬 활동에 대한 reflog만 유지합니다. 공동 작업자와 공유되지 않습니다.

Reflogs도 만료됩니다. Git은 약 90일 후에 오래된 항목을 정리하지만 구성할 수 있습니다.
 

 ## Git Reflog
 git reflog 명령은 show, expire, delete 및 exists 하위 명령을 허용합니다.
 Show는 일반적으로 사용되는 유일한 변형이며 기본 하위 명령입니다.

 git reflog show는 특정 참조의 로그를 표시합니다(기본값은 HEAD임).

 예를 들어 메인 브랜치의 팁에 대한 로그를 보려면 git reflog show main을 실행할 수 있습니다. 

 ```
 git reflog show HEAD

 git reflog
 ```

 ### Reflog References 
특정 git ref에 액세스할 수 있는 이름은 name@{qualifier}입니다. 이 구문을 사용하여 특정 ref 포인터에 액세스하고 체크아웃, 재설정 및 병합을 비롯한 다른 명령에 전달할 수 있습니다.

 ```
 name@{qualifier}
 ```

 ### Timed References 
 Every entry in the reference logs has a timestamp associated with it. We can filter reflogs entries by time/date by using time qualifiers like:
 - 1.day.ago
 - 3.minutes.age
 - yesterday
 - Fri,  12 Feb 2021 14:06:21 - 0800

```
git reflog master@{one.week.ago}
git checkout bugfix@{2.days.ago}
git diff main@{0} main@{yesterday}
```

### Reflog Rescue
때때로 reflog 항목을 사용하여 손실된 것처럼 보이고 git log에 나타나지 않는 커밋에 액세스할 수 있습니다.

### Reflog로 rebase 취소하기 
```
git reset --hard <commit-hash>
```


