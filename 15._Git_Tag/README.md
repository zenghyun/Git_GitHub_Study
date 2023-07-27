## Git Tags 
태그는 Git 기록의 특정 지점을 가리키는 포인터입니다.

태그로 특정 순간을 표시할 수 있습니다. 태그는 프로젝트에서 버전 릴리스를 표시하는 데 가장 자주 사용됩니다.

태그는 변경되지 않는 분기 참조로 생각하십시오. 태그가 생성되면 항상 동일한 커밋을 참조합니다. 커밋에 대한 레이블 일뿐입니다.

### The Two Types
우리가 사용할 수 있는 두 가지 유형의 Git 태그가 있습니다: lightweight tags와 annotated tags

lightweight tags는... lightweight 입니다. 특정 커밋을 가리키는 이름/레이블일 뿐입니다.

주석이 달린 태그는 작성자의 이름과 이메일, 날짜, 태깅 메시지(예: 커밋 메시지)를 포함한 추가 메타 데이터를 저장합니다.


## Semantic Versionging 
시맨틱 버전 지정 사양은 소프트웨어 릴리스를 위한 표준화된 버전 지정 시스템을 설명합니다. 개발자가 소프트웨어 릴리스에 의미를 부여할 수 있는 일관된 방법을 제공합니다(이 릴리스는 얼마나 큰 변화입니까?).

버전은 마침표로 구분된 세 개의 숫자로 구성됩니다.

```
2.4.1 

2: MAJOR RELEASE
4: MINOR RELEASE
1: PATCH RELEASE
```

### Initial Release
Typically, the first release is 1.0.0

### Patch Release
패치 릴리스에는 일반적으로 새로운 기능이나 중요한 변경 사항이 포함되어 있지 않습니다. 일반적으로 코드 사용 방식에 영향을 미치지 않는 버그 수정 및 기타 변경 사항을 나타냅니다. 

```
1.0.1
```

### Minor Release
마이너 릴리스는 새로운 기능이 추가되었음을 의미하지만 프로젝트는 여전히 이전 버전과 호환됩니다. 주요 변경 사항이 없습니다. 새로운 기능은 선택 사항이며 사용자가 직접 다시 작성하도록 강요해서는 안 됩니다.

마이너 릴리스는 신기능이 추가됐을 때 배포합니다.

```
1.1.0
```

### Major Release
주요 릴리스는 더 이상 이전 버전과 호환되지 않는 중요한 변경 사항을 의미합니다. 기능이 제거되거나 크게 변경될 수 있습니다.

```
2.0.0
```

## Viewing Tags and Searching
```
git tag
```
git tag는 현재 저장소의 모든 태그 목록을 인쇄합니다.

tag는 깃 커밋 히스토리에 존재하는 특정 순간, 커밋을 가리키며 일부러 바꾸지 않는 이상 항상 같은 지점을 가리킵니다.

***
```
git tag -l "*beta*"  => tag 사이에 beta가 있는 모든 tag를 검색
git tag -l "v17*" => v17로 시작하는 모든 tag를 검색 
```
git tag -l을 사용한 다음 와일드카드 패턴을 전달하여 특정 패턴과 일치하는 태그를 검색할 수 있습니다. 예를 들어 git tag -l "*beta*"는 이름에 "beta"가 포함된 태그 목록을 출력합니다.

## Checking Out Tags 
특정 태그에서 저장소의 상태를 보려면 git checkout <tag>를 사용할 수 있습니다. 이것은 우리를 분리된 HEAD에 넣습니다!

```
git checkout <tag>
```

## git diff 

```
git diff <tag1> <tag2>
```

두 tag 사이의 변경사항을 확인할 수 있다. 

## Creating Lightweight Tags 
Lightweight Tags 를 생성하려면 git tag <tagname>을 사용하십시오. 기본적으로 Git은 HEAD가 참조하는 커밋을 참조하는 태그를 생성합니다.

```
git add 
git commit - m
git tag <tagname>
```