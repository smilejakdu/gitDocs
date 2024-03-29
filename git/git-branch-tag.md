# git branch tag



###

### git branch 를 생성하게 될때 , 태그를 설정할 수 있을까 ?? 만약에 git branch issue808 으로 생성한다고 하면 , 위와 같이 issue808 로 생성하게 되면 무슨 브런치인지 알 수 없게 됩니다.

git branch 를 생성하게 될때, 태그를 설정할 수 있을까?

만약에 git branch issue808 로 생성한다고하면,&#x20;

무슨 브런치인지 알 수 없게 됩니다.

그래서 git 브랜치를 생성할 때 태그를 설정할 수 있습니다. 브랜치를 생성하는 동시에 태그를 설정하면 브랜치 이름과 태그 이름이 일치하여 브랜치를 쉽게 식별할 수 있습니다.

#### 브랜치 생성 시 태그 설정 방법

**1. `git checkout` 명령어 사용**

```
git checkout -b <브랜치 이름> -m "<태그 메시지>"
```

예시:

```
git checkout -b issue808 -m "Issue #808 해결을 위한 브랜치 생성"
```

**2. `git tag` 명령어 사용**

```
git checkout <브랜치 이름>
git tag <태그 이름>
```

예시:

```
git checkout issue808
git tag issue808-start
```

#### 브랜치와 태그의 관계

* 브랜치는 Git 저장소의 특정 지점을 나타냅니다.
* 태그는 Git 저장소의 특정 커밋을 식별하는 데 사용됩니다.

**브랜치에 태그를 설정하면:**

* 브랜치와 태그가 특정 커밋을 가리킵니다.
* 브랜치 이름을 기억하기 어려울 때 태그를 사용하여 브랜치를 쉽게 식별할 수 있습니다.

#### 태그 설정 시 고려 사항

* 태그는 변경할 수 없습니다. 새로운 태그를 만들어야 합니다.
* 태그는 삭제할 수 있습니다.
* 태그는 다른 사람과 공유할 수 있습니다.

#### 추가 정보

* Git 브랜치 및 태그에 대한 자세한 내용은 다음 링크를 참조하십시오.
  * Git 브랜치: [https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merg%3C/0%3Eing)
  * Git 태그: [https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Reposito%3C/1%3Ery)

#### 질문

브랜치 및 태그 설정에 대한 궁금한 점이 있으면 언제든 질문해주세요.\
