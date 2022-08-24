## git,github 지식 정리

- # Git

  - [x] git이란 version control System으로서 변경된 모든 사항들을 찾는(tracking) 시스템이다.
        즉 모든 변경된 사항들을 주시하고 있는것으며 원하는 시점마다 버전을 만들고, 이들간에 자유롭게 돌아다닐수 있다. 내가 만든 버전 뿐만 아니라 동료가 만든 버전으로 이동할수 있고,
        동료와 내 버전을 비교해 서 최신 코드를 업데이트 할 수도 있다.

  - [x] git을 다루는 방법 2가지
        Cli : comand line interface : 터미널에 명령어를 직접 쳐서 git을 다룬다. (터미널 사용)
        Gui : graphic user interface : 버튼을 클릭해서 git을 다루는 방법 (GitHub desktop, 소스트리)

- # GitHub

  - [x] Git provider으로써 git 파일들 또는 git 변경 사항들을 업로드 하는 장소다.
        즉 파일을 업로드 하는 공간 Github 뿐만아니라 gitlab, bitbucket등도 있지만 Github가 가장 유명하다.

  - 로컬저장소와 github 연결방법<br>

    1. github에 저장소를 만든다. <br>
    2. 폴더를 만든다. <br>
    3. 커밋을 작성한다. <br>
    4. Git add . <br>
    5. Git commit -m ‘first commit’ <br>
    6. 로컬 저장소와 github의 저장소를 연결시킨다. Git add origin remote url. 이때 url은 github의 저장소 url이다.

- # Commit

      - [x] Commit :<br>

  point in time으로 기록(저장)하는 시점이다. 즉 변경사항들을 기록(저장) 한것.<br>

      - 사용방법 :
        1. 코드 작성 및 코드 수정
        2. Git add .  또는 git add 원하는 파일
        3. Git commit -m ‘커밋메세지’.    이때 -m은 메세지란 의미

- # Area

  - [x] Area :<br>
        <br>

  1. Working Area. : Vscode에서 코드를 작성하는 곳
  2. Staging Area : commit되기 직전에 모든 변경된 파일들은 staging area로 가게된다.(변경된것을 보여주는 곳) 즉 어떤 파일들이 commit 될건지, 어떤것들이 추가될건지
  3. Reposiroty Area : 최종적으로 저장되는 곳.

    <br>

- # 로컬저장소

  - [x] 로컬저장소 :<br>
        <br>

  - Git init을 하면 보이지 않는 .git이란 폴더가 생성되며, 이것을 로컬저장소라고 한다.
  - 로컬저장소에 내가만든 버전정보, 원격 저장소 주소 등이 저장된다.
  - 원격저장소에서 내 컴퓨터로 코드를 받아오면 로컬저장소는 자동으로 생긴다.
  - 한폴더에 하나의 로컬저장소만 유지해야한다. 바탕화면에(같은공간에) 여러개의 로컬저장소를 만들면 안됨

    <br>

- # 첫번째 버전 만들기

  1.  Git init을 통해 로컬저장소를 만든다. Ex) git init 입력
  2.  코드를 작성 한뒤, git add를 통해 변경된 파일중 올릴 파일들을 선택한다. ex) git add .
  3.  commit을 통해 하나의 버전을 만들어준다. ex) git commit -m 'first commit'
  4.  Git 사용자 정보 등록 (GitHub 닉네임과 이메일을 입력해준다.)
      1. Git config --global user.name “chiman”
      2. Git config - -global user.email rlaclghks123@naver.com

    <br>

- # 커밋 이모저모

  1.  커밋은 ‘의미 있는 변동사항’을 묶어서 만든다.
  2.  버튼클릭 버그를 고치는데 5개의 파일을 수정했다면 그 5가지를 묶어 커밋한다.
  3.  동료개발자(혹은 미래의나) 가 ‘버튼클릭버그’를 고치는데 어떤 파일을 수정했는지 손쉽게 파악 가능
  4.  커밋 메세지를 적는게 귀찮아도 꼭 시간을 들여 주는게 나중에 후회하지 않는다.

    <br>

- # 다른사람이 만든 저장소 받아오기1 : git clone

  1.  원하는 폴더명으로 폴더를 만든다.
  2.  터미널을 통해 현재 위치를 새로만든 폴더로 이동해준다. cd 새로운폴더
  3.  Git clone 받길 원하는 github repository url을 통해 가져온다.ex) git clone https://rlaclghks123.github… .
  4.  이때 마지막에 . 을 찍으면 현재폴더에 clone 한다는 의미이며, 점(.)을 찍지 않으면 현재폴더안에 새로운 폴더로 만들어 지게 된다.
  5.  내가 코딩중 다른사람이 코딩을 했으면, 버전이 달라진다(같은 저장소 사용) => 이를 합치기 위해 git pull origin … 을 사용한다.

    <br>

- # 다른사람이 만든 저장소 받아오기2 : Fork

  오픈소스 등 다수의 불특정 다수들은 fork사용 why? => 원본과 다른 저장소를 사용한다.

  - Fork 방법 (github Desktop 사용)

        1. 복사하길 원하는(같이 작업할 프로젝트) repository를 fork 해준다.
        2. Github Desktop의 add를 클릭한다.
        3. Clone Repository 선택
        4. 복사한 파일을 찾은뒤, 원하는 path 설정후 Clone해준다.
        5. 경로에서 폴더를 Vscode로 실행후 원하는 코딩을 한다.
        6. 수정 후 commit 및 push한다.
        7. 부모의 repository(같이 작업한 프로젝트의 main repository)로 가서 new pull request버튼을 클릭
        8. Base repository(main)를 확인하고 , head repository를 “나”로 지정한다.

    Pull request하면 된다.

    <br>

- # branch

  - master(본체)가 있으면 나뭇가지 처럼 뻣어나가서 여러가지 시도를 한 뒤, 괜찮으면 master로 합치고, 괜찮지 않을 경우 없앰으로서 master(본체)에 영향이 가지 않도록 하는 것. 원본에 피해 가지 않고, 여러가지 실험을 할 수 있는 시스템이다.

  - HEAD는 내가 지금 작업하는 로컬 브랜치를 의미한다.(현재 코드를 작성하는 위치)
  - Master branch : 가장 기본적인 branch이다.
  - CLI에서 명령어

    - Git branch 브랜치명 : 브랜치를 만든다. ex) git branch feature/button
    - Git checkout 브랜치명 : 원하는 브랜치명으로 이동한다. 이때 HEAD가 옮겨진다. Head: 현재위치
    - 생성과 동시에 브랜치로 접속 Ex) git checkout -b feature/button

    <br>

- # gitFlow

  - Git-flow는 Git이 새롭게 활성화되기 시작하는 Vincent Driessen이라는 사람의 블로그 글에 의해 널리 퍼지기 시작했고 현재는 Git으로 개발할 때 거의 표준과 같이 사용되는 방법론입니다.

  - 즉 Git-flow는 기능이 아니고 서로간의 약속인 방법론이라는 점입니다. Vincent Driessen도 언급했듯이 Git-flow가 완벽한 방법론은 아니고 각자 개발 환경에 따라 수정하고 변형해서 사용하라고 언급했습니다.

<br>

- [x] master: 기준이 되는 브랜치로 제품을 배포하는 브랜치
- [x] Develop : 개발 브랜치로 개발자들이 이 브랜치를 기준으로 각자 작업한 기능들을 합친다(Merge)
- [x] Feature : 단위기능을 개발하는 브랜치로 기능개발이 완료되면 develop 브랜치에 합친다(Merge)
- [x] Release : 배포를 위해 master 브랜치로 보내기 전에 먼저 QA(품질검사)를 하기위한 브랜치
- [x] hotFix : master브랜치로 배포를 했는데 버그가 생겼을 때 긴급 수정하는 브랜치

<br>

- # Issue

  - Github, gitlab과 같은곳에서 프로젝트가 해야하는데 아직 하지 않은일 or 사람들이 발견한 문제나 버그를 기록하는것.

  - 오픈 소스를 작업할때 보거나, 테스터들이 문제를 찾아서 이슈를 적을때 볼 수 있다.

  - 사용방법 : issue파트에서 작성하면 된다.

  - issue를 작성하고, pull request를 통해 어떤 issue를 해결했다. 라고 말하면 된다.

  - Lable을 달수있다. Ex) bug, invalid, question…

<br>

- # Pull Request : PR

- 원본 저장소 or develop브랜치 등 merge를 요구하는것.
- 최대한 혼자 merge하는것을 피하고 모든 머지는 PR을 통해서 한다.
- 동료가 내 PR을 보고 코드 리뷰를 할 수 있다.
- 오픈소스에 PR을 보낼때에는 기여안내문서(Contribution guideLine)을 반드시 참고 해야한다.

<br>

- # Ammend

- 방금 만든 커밋(바로 이전커밋)에 코드를 수정할수 있다.

- 사용방법<br>
  1. 코드수정
  2. Git add .
  3. Git commit --ammend
  4. vi파일로 넘어가는데 메세지를 수정하거나 또는 바로 나간다. Esc -> :wq
  5. 만약 esc가 안될경우 Ctrl+3 또는 Ctrl+[ 하면됨.

<br>

- # stash

- 변경 사항을 commit 하기전에 잠시 보관할수 있도록 하는 기능. 주로 코드 작성중 checkout을 할 경우 commit 하고싶지 않을때 사용

- 사용방법<br>

  1. 저장하기 : Git stash
  2. 저장된값 불러오기 : git stash apply stash@{index값}. Ex) git stash apply stash@{0}
  3. 저장된값 보기 : git stash list
  4. 저장된값 삭제하기 : git stash drop stash@{index값}. Ex) git stash drop stash@{0}
     <br>

- # Reset

- 작성한 커밋을 삭제하는 것이다.  
  <span style="color:red">반드시 혼자쓰는 브랜치에서만 사용해야한다. 같이 사용할 경우 꼬일 위험이 있기때문에 </span>

- 사용방법<br>

  1. 삭제할 commit의 id를 알아낸다. Git log or git log --oneline
  2. 종류를 선택 Hard, mixed
  3. 사용해준다.
  4. hard : 완전삭제
     1. 현재~ 원하는 부분(id)까지 Git reset --hard id Ex) git reset --hard d89289
     2. 제일 최근 커밋삭제 Git reset --hard HEAD^
  5. mixed : 삭제는 하지만, 작성한 코드는 stage에 남겨둠
     1. 현재~ 원하는 부분(id)까지 Git reset --mixed id Ex) git reset --mixed d89289
     2. 제일 최근 커밋삭제 Git reset --mixed HEAD^

<br>

- # Revert

- 커밋의 히스토리를 남기면서 삭제 하는것 . 같이 사용하는 브랜치에서도 사용 가능.  
  **만약 같이사용하는 브랜치면 무조건 reset 말고 revert 사용**

- 사용방법<br>

  1. Git revert --hard id
  2. Git revert --mixed id
  3. 바로 커밋되지 않도록 하기 : git revert --no-commit

<br>

- # Cherry-pick

- 수정사항이 너무 많아서 당장 PR할수 없을때 원하는 커밋 하나만 급하게 merge 시킬때 사용한다.
- 사용방법<br>

  - Git cherry-pick 가져올id Ex) Git cherry-pick e282828

<br>

- # Git log

- 어떻게 커밋이 되었는지, 커밋 이력을 볼 수 있다. Ex) git log
- 간단히 보는방법 Ex) git log - -oneline
- HEAD-> master : 컴퓨터에 커밋 된것이다. (여기서 Head는 “그 시점” 을 말한다. )
- origin/master : github의 원격저장소에 커밋된것이다.
- Git log를 나갈려면 q를 입력하면 된다.  
  <br>

- # Git status

- commit을 했는지 안했는지 status(상태)를 알아본다.
- commit을 하지 않은 상태에서 git status를 하면 modified : ~~ 부분이 빨간색이다.
- Commit을 했다면 git status 입력후 modified 부분은 초록색이 된다.

<br>

- # 상대방이 PR남겼을때 상대방 코드 보는법

- 상대방이 PR남겼지만 merge를 하지 않아 코드를 볼수 없을경우 checkout을 통해 볼수있다.
- 사용방법

1. 원격저장소에 상대방의 코드를 업데이트(fetch) 해준다. Git fetch origin --prune
   이때 --prune은 더이상 원격 저장소에 존재하지 않는 ref를 삭제한다는 의미
2. Git checkout 보고싶은 브랜치 git checkout develop
3. Git pull을 통해 상대방의 코드를 볼 수 있다.
   <br>
