---
layout: single
title:  "[yeardream] ch1 git/github"
categories : git,github
---

# git, github



- VCS(Version Control System ) == SCM(Source Code Mamagement) < SCM(Software Configuration Management: 형상관리)

### Linus Torvalds 가 제작

- 압도적 업계 1위

### git 특징

- 단순한 구조와 빠른 속도
- 분산형 저장소 지원
- 비선형적 개발(수천개의 브랜치)가능

### ### git 장점

- 소스코드를 주고받기 없이 동시 작업이 가능 -> 생산성 증가
- 수정 내용은 commit 단위로 관리, 배포 뿐 아니라 원하는 시점으로 checkoutrㅏ능
- 새로운 기능 추가는 branch로 개발하여 편안한 실험이 가능
- 성공적으로 개발이 완료되면 merge하여 반영
- 인터넷이 연결되지 않아도 개발 가능

### git object

- blob : 파일 하나의 내용에 대한 정보
- tree : blobsㅏ subtreed의 메타데이터 (디렉토리 위치, 속성, 이름등)
- commit : 커밋 순간의 스탭샷

### git process flow and command

![git process flow and command](/Users/castle1/Downloads/posts/images/git:github/git process flow and command.png)

### git 과 github 는 같지 않다.

### 클라우드 원격 리포지토리 서비스

- github 
- bitbucket
- gitlab



### conventional commits

- 링크 : https://www.conventionalcommits.org/ko/v1.0.0/
- commit 제목은 commitd을 설명하는 하나의 구나 절로 완성
- `importance of capitalize`
- `prefix` 꼭 달기
  		- feat : 기능 개발 관련
  		- fix : 오류 개선 혹은 버그 패치
  		- docs : 문서화 작업
  		- test : test 관련
  		- conf : 환경설정 관련
  		- build : 빌드 관련
  		- ci : continuous integration 관련

### 커밋시 주의할점

- commit은 동작 가능한 최소단위로 자주 할것
- 해장 작업단위에 수행된 모든 파일 변화가 해당 commit에 포함되어야 한다.
- 모두가 이해 가능한 log 작성
- open source contribution사 영어가 강제, 그렇지 않다면 팀 내 사용 언어를 따라 사용할것
- 제목은 축약하여 쓰되, 내용은 문장형으로 작성하여 추가 설명할것.
- 제목과 내용은 한 줄 띄워 분리할것.
- 내용은 commit의 구성과 의도를 충실히 작성



# git practice(macOS)

- github : https://github.com/
- new repository![new repository](/Users/castle1/Downloads/posts/images/git:github/new repository.png)

### .gitignore

- gitignore 생성 링크 : https://www.toptal.com/developers/gitignore
- git이 파일을 추적할때 어떤 파일이나 폴더 등을 추적하지 않도록 명시하기 위해 작성
- 해당 문서에 작성된 리스트는 수정사항이 발생해도 git이 무시하게 된다.
- 특정 파일 확장자를 무시하거나 이름에 패턴이 존재하는 경우, 또는 특정 디렉토리 아래의 모든 파일을 무시할 수 있다.

### Documents 폴더에서 진행

- terminal 실행
- cd Documents : Documents 폴더로 이동
- mkdir practic_dev : practic_dev 폴더생성
- cd practic_dev : practic_dev로 이동

### vim

- vim 사용

- vim 모드

  - normal mode : `esc`를 누른상태

    ![vim normal mode](/Users/castle1/Downloads/posts/images/git:github/vim normal mode.png)

  - insert mode : 노말모드에서 `i`

    ![vim insert mode](/Users/castle1/Downloads/posts/images/git:github/vim insert mode.png)

  - command mode : 노말모드에서 `:(콜론)` 입력한 상태

    ![vim command mode](/Users/castle1/Downloads/posts/images/git:github/vim command mode.png)

  - visual mode : `v` 또는 `ctrl-v`를 누른상태

    ![vim visual mode](/Users/castle1/Downloads/posts/images/git:github/vim visual mode.png)

### vim 단축키

![vim-shortkey-keyboard](/Users/castle1/Downloads/posts/images/git:github/vim-shortkey-keyboard.png)

### git clone

![git clone](/Users/castle1/Downloads/posts/images/git:github/git clone.png)

- 주소 복사 : https://github.com/castle-1/practic.git

- git 에서 처음 clone 할시 토큰을 발행해야한다.

  - settings -> Developer settings -> personal access tokens -> tokens(classic)

    ![access token](/Users/castle1/Downloads/posts/images/git:github/access token.png)

    - 터미널에서 비밀번호 입력시 토큰값으로 입력

- git clone https://github.com/castle-1/practic.git

  ![git clone2](/Users/castle1/Downloads/posts/images/git:github/git clone2.png)

- 클론한 pracitc 폴더로 이동
  - cd practic

- 항상 상태체크
  - git status

### READNE,md

- 프로젝트와 Repository를 설명하는 책의 표지와 같은 문서
- 나와 동료, 이 Repository의 사용자를 위한 문서

### .gitignore 

- touch .gitignore : gitigonre 생성

- vi .gitignore : gitignore 실행

- https://www.toptal.com/developers/gitignore 에서 생성

  ![gitignore_io](/Users/castle1/Downloads/posts/images/git:github/gitignore_io.png)

- 생성된 gitignore를 복사/붙여넣기

- normal mode 에서 `:wq`  -> 저장을 의미

- git status : 상태 확인

   ![git status](/Users/castle1/Downloads/posts/images/git:github/git status.png)

- git add .gitignore 
  - git add : 작업 디렉토리(working directory)상의 변경 내용을 스테이징 영역(staging area)에 추가하기 위해 사용하는 git 명령어

- 다시 상태확인

  - git status

    ![git status2](/Users/castle1/Downloads/posts/images/git:github/git status2.png)

- git commit

  - perfix 작성후 저장 : conf : create .gitignore

    ![gitignore commit](/Users/castle1/Downloads/posts/images/git:github/gitignore commit.png)

- git push

  - git push origin main

    ![push](/Users/castle1/Downloads/posts/images/git:github/push.png)

- 깃허브에서 확인

### hello_world.py 생성

- touch hello_world.py : 확장자가 파이썬인 hello_world 생성
- vi hello_world.py : hello_world.py 실행
- print('hello world') 작성후 저장
- cat hello_world.py
  - cat cat: 파일 내용을 터미널에 출력하거나 여러 파일을 하나로 합치는 명령어![cat](/Users/castle1/Downloads/posts/images/git:github/cat.png)

- python hello_world.py

  - hello_world.py 실행

    ![python hello_world](/Users/castle1/Downloads/posts/images/git:github/python hello_world.png)

- git status
- git add hello_world.py
- git status
- git commit
- git push origin main
- github 에서 확인!
