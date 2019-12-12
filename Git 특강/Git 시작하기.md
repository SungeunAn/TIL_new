# Git

> Git은 분산형 버전 관리 시스템(DVCS)이다.
>
> 소스코드 형상 관리 도구로, 코드의 이력을 관리할 수 있다.



## Git 로컬 저장소 활용하기

> Git은 `repository(저장소)`로 각각 프로젝트를 관리한다.

### 0. 기본 설정

.git 파일 있는 상태에서 우클릭 > `Git Bash Here`로 커맨드창 띄워야 한다.

Git에서 이력을 남기기 위해 작성자(author) 정보를 추가한다. 매 컴퓨터에서 최초로 한 번만 설정하면 된다.

```bash
$ git config --global user.name 유저네임
$ git config --global user.email 이메일
```

### 1. 저장소 생성

```bash
$ git init 
Initialized empty Git repository in C:/Users/student/Desktop/TIL/.git/

(master) $
```

> 커밋 대상 파일을 `staging area`로 이동시킨다.
>
> 즉, 이력을 남길 파일을 담아 놓는 것이다.

```bash
$ git add . (모든 파일 업로드)
$ git add images/ (특정 파일만 업로드)
$ git add git.md (특정 파일만 업로드)
```

.은 현재 디렉토리 폴더를 뜻한다.

항상 `git status`를 통해 상태를 확인하자.

```bash
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    1205/Git.md -> "1205/Git \354\213\234\354\236\221\355\225\230\352\270\260.md"
```

### 3. `commit`

> Git에서 이력을 남기기 위해  `commit`진행

```bash
$ git commit -m 'Git 기초'
[master 9634077] Git 기초
 1 file changed, 5 insertions(+)
 rename 1205/Git.md => "1205/Git \354\213\234\354\236\221\355\225\230\352\270\260.md"
```

이력을 확인하기 위해서는 `git log`를 활용한다.

```bash
$ git log
commit 9634077eb9d6edc4d1877bbc30228543cf892dd9 (HEAD -> master)
Author: Sungeun <asg0221@snu.ac.kr>
Date:   Thu Dec 5 12:48:32 2019 +0900

    Git 기초

```



# Git 원격 저장소 활용하기

## 0. 기본 설정

> 원격 저장소를 생성한다. (예 - 깃허브)

## 1. 원격 저장소 등록

`origin`이라는 이름으로 해당 url을 원격 저장소로 등록한다. 최초 한 번만 하면 된다.

```bash
git remote add origin https://github.com/SungeunAn/TIL.git
```

```bash
$ git remote -v
origin  https://github.com/SungeunAn/TIL.git (fetch)
origin  https://github.com/SungeunAn/TIL.git (push)
```

앞으로 변경되는 사항이 있으면 항상 **add, commit, push**를 실행한다.

```bash
 $ git push -u origin master
```



## 기타

coursera - ML/DL 대학원론수업 느낌

udacity - ML 조금 쉽게 다가감

edx

모두의 딥러닝



