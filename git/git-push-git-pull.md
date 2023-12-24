# git push git pull 문제

<figure><img src="../.gitbook/assets/스크린샷 2023-12-22 오후 9.49.51.png" alt=""><figcaption></figcaption></figure>

git pull origin dev -no-rebase

git config pull.rebase false

git push&#x20;

Git에서 'divergent branches'라는 메시지는 로컬 브랜치와 원격 브랜치가 분기한 상태에서 다시 병합해야 할 필요가 있다는 것을 의미합니다. 이 메시지는 로컬에서의 커밋과 원격 브랜치에서의 커밋이 서로 다를 때 나타납니다.

이 문제를 해결하기 위해, 로컬 브랜치의 변경 사항을 원격 브랜치와 어떻게 병합할지 결정해야 합니다. 주로 사용되는 방법은 다음과 같습니다:

#### 1. Merge 방식 사용

Merge 방식은 로컬과 원격 브랜치의 변경 사항을 병합하여 새로운 커밋을 생성합니다. 이 방법은 변경 이력을 그대로 유지합니다.

```bash
git pull origin dev --no-rebase
```

#### 2. Rebase 방식 사용

Rebase 방식은 로컬에서의 커밋을 원격 브랜치의 최신 커밋 이후로 "재배치"합니다. 이 방법은 변경 이력을 깔끔하게 유지할 수 있지만, 공유된 브랜치에서 rebase를 사용할 때는 주의가 필요합니다.

```bash
git pull origin dev --rebase
```

#### 3. Fast-forward만 허용

이 옵션은 fast-forward 병합만 허용합니다. 즉, 로컬 브랜치의 커밋이 원격 브랜치의 커밋을 추월하지 않았을 때만 병합이 가능합니다.

```bash
git pull origin dev --ff-only
```

#### 기본 설정 변경

`git config`를 사용하여 기본 병합 방식을 설정할 수 있습니다. 예를 들어, 항상 merge 방식을 사용하고 싶다면, 다음 명령어를 실행하세요:

```bash
git config pull.rebase false
```

이 설정을 한 후에는 `git pull origin dev`를 실행할 때마다 merge 방식을 사용하게 됩니다.

#### 주의사항

* **커밋 충돌**: 병합 과정에서 충돌이 발생할 수 있습니다. 충돌이 발생하면, 충돌을 해결하고 병합을 완료해야 합니다.
* **공유된 브랜치에서의 Rebase 사용 주의**: rebase는 공유된 브랜치의 이력을 변경하기 때문에, 다른 사람들이 같은 브랜치에서 작업하고 있다면 주의해야 합니다. 다른 팀원들과 협의 없이 공유된 브랜치에서 rebase를 사용하면 혼란을 야기할 수 있습니다.
