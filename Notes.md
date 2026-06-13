# Git 학습 정리

## Git이란?
Git은 버전 관리 시스템(VCS, Version Control System)이다.

파일의 변경 이력을 저장하고 관리할 수 있으며, 필요할 경우 이전 버전으로 되돌아 갈 수 있다.


## GitHub란?
GitHub는 Git 저장소를 원격으로 저장하고 공유할 수 있는 플랫폼이다.

- Git: 버전 관리 도구, 프로그램
- GitHub: Git 저장소를 저장하고 공유하는 서비스

Git은 내 컴퓨터에서 동작하고, GitHub는 Git 저장소를 관리하는 역할을 한다.

---

## Local Repository와 Remote Repository

### Local Repository
개발자 개인 PC에 존재하는 Git 저장소
평소에는 Local Repository에 버전을 저장하며 작업한다.

Ex.
C:\git_study

### Remote Repository
팀원들과 공유하기 위한 Git 저장소
대표적인 Remote Repository에 버전을 저장하며 작업한다.

Ex.
https://github.com/jiwon28/git_study

---

## Commit
Commit은 Local Repository에 새로운 버전을 저장하는 작업이다.
의미있는 작업 단위가 완료될 때마다 Commit하는 것이 좋다.

Ex. 
- 기능 구현 완료
- 버그 수정 완료
- 문서 정리 완료

### Commit Message
commit 생성 시 반드시 작성해야 하는 메시지이다.
작업 내용을 이해할 수 있도록 작성해야 한다.

실습 예시
Git 학습 시작
README 수정
Day1 Git 학습 정리

### Commit Hash
각 Commit애는 고유한 ID가 부여된다.
이를 Commit Hash라고 한다.

실습 예시
230202
git log --oneline 명령어로 확인할 수 있다.

---

## Working Tree와 Staging Area

### Working Tree
Git이 관리하는 실제 프로젝트 폴더이다.
현재 실습에서는 다음 폴더가 Working Tree에 해당된다.
C:/git_study

### Staging Area
Commit 전에 변경 내용을 임시로 등록하는 공간이다.
Git은 Working Tree의 모든 변경사항을 Commit하지 않는다.
Staging Area에 등록된 파일만 Commit 대상이 된다.
따라서  원하는 파일만 선택적으로 Commit할 수 있다.

## Git Life Cycle
Git에서 파일은 다음 상태를 가진다.

Untracked
Git이 아직 추적하지 않은 새 파일

Staged
다음 Commit에 포함될 파일

Unmodified
Commit 이후 수정되지 않은 상태

Modified
Commit 이후 수정되었지만 아직 Staged 되지 않은 상태

### 상태 변화
새 파일 생성
↓
Untracked
↓
git add
↓
Staged
↓
git commit
↓
Unmodified
↓
파일 수정
↓
Modified
↓
git add
↓
Staged
↓
git commit
↓
Unmodified

---

## git init
현재 폴더를 Git 저장소로 생성한다.

---

## git status
현재 Git 상태를 확인한다.

---

## git add
변경사항을 Commit 대상으로 등록한다.

---

## git commit
현재 상태를 하나의 버전으로 저장한다.

---

## git push
Local REpository의 내용을 Remote Repository로 업로드한다.

---

## origin
현재 연결된 원격 저장소(Remote Repository)의 별명이다.
실습에서는 다음 저장소를 origin으로 연결했다.
https://github.com/jiwon28/git_study.git

---

## 실습을 통해 확인한 내용

### Local Repository 생성
git init

### 상태 확인
git status

### 파일 등록
git add .

### Commit 생성
git commit -m "Git 학습 시작"

### Commit 기록 확인
git log --oneline

### Github 업로드
git push -u origin main

---

## 실습 중 발생한 문제

## 문제
git push 실행 시 인증 오류 발생

Invalid username or token
Password authentication is not supported

## 원인
GitHub는 비밀번호 인증 방식을 지원하지 않는다.

## 해결
Git Credential Manager를 이용하여 GitHub 계정 인증을 진행하였다.

## 결과
git push -u origin main
명령을 성공적으로 수행하여 GitHub 저장소에 업로드하였다.

---

## git log
Commit 기록을 확인하는 명령어이다.

### 사용 예시
git log
git log --oneline

### 실습 결과
현재까지 생성된 Commit 목록을 확인

---

## git diff
파일 수정 전후 차이를 확인하는 명령어이다.

### 사용 예시
git diff

### 실습 결과
README.md 수정 후 변경 내용을 확인하였다.

---

## git remote
현재 연결된 원격 저장소를 확인하는 명령어이다.

### 사용 예시
git remote -v

### 실습 결과
현재 GitHub 저장소(origin)가 연결되어 있는 것을 확인하였다.

---

## git clone
원격 저장소를 내 컴퓨터로 복제하는 명령어이다.

### 사용 예시
git clone 저장소주소

### 실습 결과
GitHub 저장소를 새로운 폴더에 복제하였다.

---

## git fetch
원격 저장소의 최신 내용을 가져오기만 한다.
실제 파일에는 반영되지 않는다.

---

## git pull
원격 저장소의 최신 내용을 가져오고 현재 브랜치에 반영한다.
fetch + merge와 동일한 역할을 수행한다.

---

## git branch
브랜치를 생성하거나 확인하는 명령어이다.

### 사용 예시
** 어떤 branch가 있는지 확인
git branch

** 브랜치 생성
git branch feature/login

### 실습 결과
feature/login 브랜치를 생성했다.

---

## branch란?
독립적으로 작업할 수 있는 작업 공간

기존 코드에 영향을 주지 않고 새로운 기능을 개발하거나 버그를 수정할 때 사용한다.

Ex.
main
--> feature/login

작업 완료 후 main 브랜치에 병합(merge)할 수 있다.

### 사용 예시
git branch
git branch feature/login

### 이해한 내용
브랜치는 새로운 폴더가 아닌 현재 시점의 코드를 기준으로 만드는 별도의 작업 공간이다.

---

## git switch
브랜치를 이동하는 명령어이다.

### 사용 예시
git switch feature/login

### 실습 결과
main 브랜치에서 feature/login 브랜치로 이동하였다.

---

## git merge
브랜치의 작업 내용을 현재 브랜치에 합치는 명령어이다.

### 사용 예시
git merge feature/login

### 실습 결과
feature/login 브랜치의 내용을 main 브랜치에 병합하였다.

---

## Merge Conflict
같은 파일의 같은 부분을 서로 수정한 경우 발생하는 충돌이다. 

### 실습 결과
main 브랜치와 feature/login 브랜치에서
README.md를 각각 수정한 후 merge를 수행하였다.
merge 과정에서 Conflict가 발생하였다.

### 해결 방법
충돌 내용을 확인한다.
원하는 내용으로 수정한다.
저장 후 아래 명령어를 실행한다.
git add README.md
git commit

### 이해한 내용
Merge Conflict는 오류가 아니라
어떤 내용을 최종으로 사용할지 Git이 결정할 수 없을 때 발생한다.
개발자가 직접 최종 내용을 선택해야 한다.

---

## git checkout
브랜치를 이동하는 명령어이다.

### 사용 예시
git checkout feature/login
git checkout main

### 실습 결과
main 브랜치와 feature/login 브랜치 사이를 이동하였다.

### 이해한 내용
git switch와 동일하게 브랜치를 이동할 수 있다.
과거에는 git checkout을 사용했지만 현재는 git switch 사용을 권장한다.

---

## git reset
Staging Area에 등록된 내용을 취소하는 명령어이다.

### 사용 예시
git reset README.md

### 실습 결과
git add로 등록한 REAME.md를
Staging Area에서 제거하였다.

### 이해한 내용
git reset은 파일 내용을 삭제하지 않는다.

Staging Area에서만 제거하며
Working Tree의 내용은 그대로 유지된다.

### 추가로 이해한 내용
처음에는 git reset이 git add를 취소하는 명령어라 생각했지만,
git reset은 사용 방법에 따라 동작이 다르다.

#### git reset 파일명 
- Staging Area에서 제거
#### git reset --Soft HEAD~1
- 마지막 Commit 제거
- 파일 변경 내용 유지
#### git reset --hard HEAD~1
- 마지막 Commit 제거
- 파일 변경 내용 삭제

즉, git reset은 git add 취소뿐만 아니라 Commit을 되돌릴 때도 사용할 수 있다.

++ 추가
Git 입장에서는 HEAD 위치를 바꾼 것이고,
사용자 입장에서는 마지막 Commit을 삭제한 것처럼 보인다.

---

## git revert
특정 Commit을 취소하는 새로운 Commit을 생성하는 명령어이다.

### 사용 예시
git revert HEAD

### 실습 결과
git revert 학습 Commit 생성
이후
git revert Head 명령어 실행

이는 명령어를 실행하여 해당 Commit을 취소하는 Commit을 생성하였다.

### 이해한 내용
git revert는 기존 Commit을 삭제하지 않는다.
대신 특정 Commit을 취소하는 새로운 Commit을 생성한다.
실습 결과
git revert 학습
↓
Revert "git revert 학습"
형태의 Commit이 생성되는 것을 확인하였다.

---

## git rebase
브랜치의 시작 위치를 다른 Commit 기준으로 변경하는 명령어이다.

### 사용 예시
git rebase main

### 실습 결과
feature/rebase 브랜치에서 git rebase main 명령어를 실행하였다.
main 브랜치의 최신 Commit을 기준으로 feature/rebase 브랜치가 재배치되었다.

### 이해한 내용
git merge는 브랜치를 병합한다.
git rebase는 브랜치의 시작 위치를 변경하여 Commit 기록을 한 줄로 정리한다.
rebase 후에는 Commit Hash가 변경될 수 있다.

---

## Rebase Conflict
rebase 중 같은 파일을 수정한 경우 발생하는 충돌이다.

### 실습 결과
main 브랜치와 feature/rebase 브랜치에서 README.md를 각각 수정한 후 rebase를 수행하였다.

rebase 과정에서 Conflict가 발생하였다.

### 해결 방법
충돌 내용을 확인한다.
원하는 내용으로 수정한다.
저장 후 아래 명령어를 실행한다.
git add README.md
git rebase --continue

### 이해한 내용
rebase 중 Conflict가 발생하면 작업이 중단된다.

충돌을 해결한 후 git rebase -continue 명령어를 실행해야 나머지 rebase 작업이 계속 진행된다.

---

## git cherry-pick
특정 Commit 하나를 현재 브랜치로 가져오는 명령어이다.

### 사용 예시
git cherry-pick 커밋해시

### 실습 결과
feature/cherry-pick 브랜치에서 생성한 Commit을 Main 브랜치로 가져왔다.

### 이해한 내용
cherry-pick은 브랜치 전체를 가져오는 것이 아니다.

특정 Commit 하나만 선택하여 가져온다.

가져오는 과정에서 새로운 Commit이 생성되므로
원본 Commit과 Commit Hash가 다르게 생성된다.

---

## merge, rebase, cherry-pick 비교
세 명령어 모두 다른 브랜치의 작업을 가져오는 기능이지만,
목적과 동작 방식이 다르다.

### merge
브랜치 전체를 현재 브랜치에 합친다.

#### 사용 예시
git switch main
git merge feature/login

### 이해한 내용
feature/login 브랜치의 작업 내용을
main 브랜치에 합칠 때 사용한다.

## cherry-pick
특정 Commit 하나만 현재 브랜치로 가져온다.

### 사용 예시
git cherry-pick 커밋해시

### 이해한 내용
브랜치 전체를 가져오는 것이 아니라
원하는 Commit 하나만 선택하여 가져온다.

기존 Commit을 그대로 가져오는 것이 아니라
동일한 변경 내용을 가진 새로운 Commit을 생성한다.

따라서 Commit Hash는 새롭게 생성된다.

### 실습 결과
feature/cherry-pick 브랜치
git cherry-pick 학습
↓
main 브랜치
git cherry-pick 학습

동일한 내용이지만 서로 다른 Commit Hash를 확인하였다.

## rebase
현재 브랜치의 Commit을 다른 브랜치 최신 Commit 뒤로 이동한다.

### 사용 예시
git switch feature/rebase
git rebase main

### 이해한 내용
현재 브랜치에서 실행한다.

git rebase main 명령은
현재 브랜치의 작업 내용을
main 브랜치 최신 Commit 뒤로 이동시키는 의미이다.

### 실습 결과
main 브랜치와 feature/rebase 브랜치에서
각각 작업을 수행한 후 rebase를 진행하였다.

rebase 이후 feature/rebase 브랜치의 Commit이
main 브랜치 최신 Commit 뒤로 이동한 것을 확인하였다.

또한 Commit이 새로 생성되면서
Commit Hash가 변경되는 것을 확인하였다.

## merge와 rebase 차이
- merge : 브랜치는 합친다.
- rebase : 현재 브랜치 Commit의 위치를 이동한다.

merge는 Merge Commit이 생성될 수 있으며,
브랜치가 합쳐진 이력을 그대로 유지한다.

rebase는 Commit 이력이 직선 형태로 정리된다.

## merge와 cherry-pick 차이
- merge : 브랜치 전체를 가져온다.
- cherry-pick : 특정 Commit 하나만 가져온다.

## rebase와 cherry-pick 차이
- rebase : 현재 브랜치의 여러 Commit 위치를 이동한다.
- cherry-pick : 선택한 Commit 하나를 현재 브랜치에 복사한다.

### 현재 이해한 내용
- merge : 브랜치 전체를 합친다.
- cherry-pick : 원하는 Commit 하나만 복사한다.
- rebase : 현재 브랜치 Commit을 다른 브랜치 최신 Commit 뒤로 이동한다.

### 암기 포인트
merge = 브랜치 전체 합치기
cherry-pick = Commit 하나 복사
rebase = Commit 위치 이동