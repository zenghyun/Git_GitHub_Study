# 추가하기와 커밋하기 

## 추가하기 

git init : 비어있는 깃 저장소를 생성하거나 기존 저장소를 다시 초기화한다. 

git status : 저장소의 상태를 보고해주는 명령어 만약, 저장소를 갖고 있지 않다면 깃 저장소 정보가 없다는 메시지를 알려준다. 

<br>

## 커밋하기 

git commit : 그 시점의 체크포인트를 저장하기 위해 사용하는 명령어 

```
git commit -m "내가 적고싶은 변경 사항" 
```

<br>

git add : 다음 커밋에 포함할 변경사항들을 선택하거나 하이라이트 하기 위해 사용한다.

```
git add 내가 변경한 파일 이름1 파일 이름2 
```

<br>

```
Working Directory => git add => Staging Area => git commit => Repository 
```
<br>

Working Directory : 내가 작업하고 있는 디렉토리를 가리킨다. ( 내가 만들었던 다수의 변경사항들을 볼 수 있다. )

Staging Area : 커밋하기 전에 변경사항들을 등록하는 곳 

<br>

working tree clean : 워킹 디렉토리에 있는 폴더에서 변경된 모든 것들을 깃이 알고 있고 깃이 추적하고 있으며 업데이트 했다는 뜻

----

<br>

git log : git status와 마찬가지로 정보들을 검색하는 명령어이며, 깃 저장소에 대한 커밋 정보들을 검색한다. 