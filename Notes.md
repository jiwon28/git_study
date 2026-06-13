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

Midified
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