# Quest 00. 형상관리 시스템

## Introduction
* git은 2021년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics
* git
  * `git clone`, `git add`, `git commit`, `git push`, `git pull`, `git branch`, `git stash` 명령
  * `.git` 폴더
* GitHub

## Resources
* [Resources to learn Git](https://try.github.io)
* [Learn Git Branching](https://learngitbranching.js.org/?locale=ko)
* [Inside Git: .Git directory](https://githowto.com/git_internals_git_directory)

## Checklist
* 형상관리 시스템은 왜 나오게 되었을까요?
  * 프로그램을 만들다 보면, 잘못 만들어서 다시 소스코드를 이전 상태로 되돌릴 필요도 있고, 변경된 이력을 확인할 필요가 있습니다. 그리고 여러명의 개발자들이 동시에 같은 소스코드를 개발하면서 충돌에 대한 처리가 필요해서 형성관리 시스템이 나오게 되었습니다.
    * 형성관리 시스템 즉 버전 관리 시스템이 필요한 이유
      * 개발 하는 동안 소스 코드의 변경 사항을 보존하기 위해
        * 버그 및 문제점이 발생했을 때 추적에 유용
        * 과거 특정 시점의 소스 파일 및 디렉토리의 내용을 손쉽게 확인 가능
        * 과거 특정 시점의 소스 파일로 손쉽게 되돌릴 수 있음
      * 협동 작업을 가능하게 하기 위해
        * 대부분의 프로젝트는 팀 단위이기 때문에 전체 팀원이 하나의 소스를 가지고 효율적으로 작업할 수 있는 도구가 필요함
        * 인터넷을 이용한 전세계 개발자들이 협업을 하여 개발하는 오픈 소스 프로젝트에 필수
* git은 무엇일까요? 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란
  * git이란 소스 코드를 효율적으로 관리하기 위해 만들어진 '분산형 버전 관리 시스템'이다.
  * 분산형 버전관리 시스템이란 하나의 중앙서버가 존재하고, 여러 클라이언트들이 각자의 로컬 저장소에 중앙 서버의 전체 사본을 가지고 작업하는 것을 말한다.
    * git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?
* git과 GitHub은 어떻게 다를까요?
  * git은 로컬에서 버전 관리 시스템을 운영하는 방식이고, Github는 저장소를 깃허브에서 제공해주는 클라우드 서버를 이용한다.
    * git
      * 로컬에서 관리되는 버전 관리 시스템 (VCS : Version Control System)
      * 소스코드 수정에 따른 버전을 관리해주는 시스템
    * Github
      * 클라우드 방식으로 관리되는 버전 관리 시스템(VCS)
      * 자체 구축이 아닌 빌려쓰는 클라우드 개념
      * 오픈소스는 일정 부분 무료로 저장 가능, 아닐 경우 유료 사용
* git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?
  * git clone
    * local에 아무것도 없는 상태에서 원격저장소의 데이터를 가져오는 것을 의미한다.
    * ```bash
        git clone "url 주소"
      ```
  * git add
    * git이 추적하고 있는 수정된 파일이 working directory에서 staging area에 저장된다.
    * ```bash
        git add . # 현재 디렉토리의 모든 변경 내용을 스테이징 영역으로 넘기고 싶을 때

        git add -A # 작업 디렉토리 내의 모든 변경 내용을 몽땅 스테이징 영역으로 넘기고 싶을 때
      ```
  * git commit
    * staging area에 있는 파일을 커밋한다. 즉 변경 사항을 로컬 저장소에 기록하는 것을 말한다.
    * ```bash
        git commit -m "Commit message" #commit message를 추가해서 staging area에 있는 파일을 커밋한다.
      ```
  * git push
    * 원격 저장소에 코드 변경분을 업로드하기 위해서 사용하는 명령어이다.
    * ```bash
        git push "저장소명" "브랜치명" 
      ```
  * git pull
    * local에 이미 있고, 원격저장소의 수정상태를 반영하기 하고 자동으로 로컬 브랜치에 (Merge)까지 수행해주는 명령어이다.
    * ```bash
        git pull origin master
      ```
  * git branch
    * 독립적으로 어던 작업을 진행하기 위해 사용하는 명령어이다.
    * ```bash
        git branch "branchname" # 로컬에 새로운 브랜치를 생성하는 명령어

        git branch -a # 로컬과 리모트의 모든 브랜치 목록을 보여준다.

        git branch "-l or --list" # 로컬에 존재하는 브랜치를 리스트로 보여준다. 

        git branch -v # --verbose 옵션. 로컬 브랜치의 정보를 마지막 커밋 내역과 함께 보여준다.
      ```
  * git stash
    * git add 명령어를 실행해 스테이지로 옮긴 파일이건 아니건 모두 임시 저장해준다.
    * 아직 완료하지 않은 일을 commit하지 않고 나중에 다시 꺼내와 마무리할 수 있다.
    * ```bash
        git stash # 새로운 stash를 스택에 만들어 하던 작업을 임시로 저장한다.

        git stash list # 저장한 stash 목록을 확인할 수 있다.

        git stash apply # 최근에 했던 작업을 다시 가져온다.

        git stash apply --index # staged 상태였던 파일을 다시 가져온다.

        git stash drop # 최근에  stash를 제거한다.

        git stash pop # 적용과 동시에 스택에서 해당 stash를 제거할 수 있다.
      ```
* git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?
  * Object
    * git은 기본적으로 키-값(key-value)저장소로 볼 수 있다. git에 데이터를 추가시, git은 객체(object)를 생성한 후 해당 객체 내용의 SHA-1해시값을 key로써 사용하게 된다. 따라서 git 내에 모든 내용물은 해당 해시값을 이용하여 찾아볼 수 있게 되어 있다.
    * git 에서의 object의 종류에는 4가지가 존재한다.
      * blob
      * tree
      * commit
      * tag
  * Commit
    * 파일 및 폴더의 추가/변경 사항들에 대해 기록을 하는 것
    * 시간 순으로 저장이 되며 최근 커밋부터 거슬러 올라가면 과거 변경 이력과 내용을 확인 할 수 있다.
    * 영문/숫자로 이루어진 40자리의 고유 이름이 붙으며 고유 이름을 통해 각 커밋을 구분한다.
  * Head
    * 현재 체크아웃된 브랜치의 가장 최신커밋을 가리킨다.
    * 현재 자신이 바라보고있는 commit을 가리킨다.
  * Branch
    * 독립적으로 어떤 작업을 진행하기 위한 개념
    * 각각의 브랜치는 다른 브랜치의 영향을 받지 않기 때문에, 여러 작업을 동시에 진핼할 수 있다.
    * 커밋 사이를 가볍게 이동할 수 있는 어떤 포인터
  * Tag
    * 커밋을 참조하기 쉽도록 알기 쉬운 이름을 붙이는 것
    * 한 번 붙인 태그는 브랜치처럼 위치가 이동하지 않고 고정 됨
    * 주로 릴리즈 버전을 표시하는데 주로 사용
* 리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?
  * `reset`을 사용해 커밋을 취소(삭제)하는 방법
    * 사용법
      * `git log`를 이용해 취소할 커밋전의 hash코드를 알아낸다.
      * `git reset --hard "hash코드"`를 통해 강제로 HEAD의 위치를 바꾼다.
      * `git push -f origin "브랜치 명"`을 통해 원격 저장소에 강제로 push를 한다.
    * 정리
      * 강제로 푸시를 밀어 넣는 방법으로 이미 원격 저장소에 올라간 커밋을 삭제하는 방법이기 때문에 협업하는 상황에서 쓰기 좋은 방법이 아니다.
      * 커밋기록을 바꾸기전에 clone해간 협업자들은 push시 충돌에러가 발생
  * `revert`를 사용해 커밋 내용을 되돌리는 방법
    * 사용법
      * `git log`를 이용해 되돌아갈 커밋의 hash코드를 알아낸다.
      * `git revert "hash코드"`를 통해 변경사항을 지정한다.
        * `git revert --no-commit HEAD~n..` : HEAD부터 지정한 지점까지 커밋을 남기지않고 revert 실행
        * `git commit -m "커밋 메시지"` : --no-commit옵션을 사용하면 최종적으로 따로 commmit 실행
      * `git push origin "브랜치 명"` 을 통해 원격 저장소에 push를 한다.
    * 정리
      * 커밋 기록을 삭제하는 것이 아닌 '커밋의 변경사항을 되돌린다'는 커밋을 만들어 주는 방식
      * 원격 저장소에 revert한 커밋내용이 남아있다.

## Quest
* GitHub에 가입한 뒤, [이 커리큘럼의 GitHub 저장소](https://github.com/KnowRe-Dev/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
* Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
  * 앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
* 이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
* `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

## Advanced
* Mercurial은 어떤 형상관리 시스템일까요? 어떤 장점이 있을까요?
* 실리콘밸리의 테크 대기업들은 어떤 형상관리 시스템을 쓰고 있을까요?
