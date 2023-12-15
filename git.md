<h1>깃설정</h1>

## 주요 설정 변수
<p>기본 편집기 설정 -> core.editor ['code --wait' | 'notepad']</p> 
<p>줄 바꿈 자동변환 -> core.autocrlf[true,flase]</p>
<p>사욜자 이름 설정 -> user.name 사용자 이름 -> ex) user.name admin</p>  
<p>사용자 이메일 성정 -> user.email</p>  
<p>기본 브런치 이름 -> init.defaultBranch 브런치 이름 -> ex) init.defaultBranch main</p>

## 설정명령과 구조

### 설정명령 구조
설정명령의 구조 -> $ git config --설정범위 설정변수 설정값

### 설정 범위
- System 모든 사용자
- global 현재 사용자의 모든 저장소
- local 현자 사용자의 현재 저장소


## 줄바꿈 설정

### 설정 명령어
$ git config --global core.autocrlf true -> 줄바꿈 처리를 자동으로 지정  
$ git config --get core. autocrlf -> 줄바꿈 처리 방법을 조회  
$ git config --global core.safecrlf false -> 줄바꿈 안전 설정을 false르 지정  
$ git config --get core.safecrlf -> 줄바꿈 안전 설정을 조회

### 줄바꿈 설정 필요이유
플랫폼 별로 줄 끝을 인식하는 방법의 차이가 존재
- 윈도우에서는 cr(carriage return)과 lf(line feed)로 한 줄의 끝을 인식 -> autocrlf를 true로 지정
- 맥과 리눅스에서는 lf(line feed)로 한 줄의 끝을 인식 -> autocrlf를 input으로 지정

### 줄바꿈 안전 설정
설정이 잘못 됨나면 add나 commit에서 줄바꿈 경고 메세지가 발생히거나 오류가 발생 할 수 있으니 주의 -> safecrlf를 윈도우의 경우 false로 지정해야하고 맥과 리눅스의 경우 input으로 지정
<hr>


## 저장소 생성
- $ git init or $ git init . -> 현재 폴더를 git repository로 만들어서 사용
- $ git init basic -> 현재 폴더 하부에 basic 폴더를 생성하고 git repository로 사용

<hr>

## 리눅스 기초 명령어

### 폴더
- $ pwd -> print working directory(현재폴더표시)
- $ cd -> change directory(폴더이동)
- $ mkdir -> make directory(폴더 생성)

### 파일 관련
- $ touch filename -> 지정한 이름으로 빈파일 생성
- $ cat fname -> fname의 파일 내용 표시
- $ cp a b -> 파일 a를 b로 복사
- $ mv f1 f2 -> 파일 f1을 f2로 이름 변경
- $ rm fname -> fname 파일을 삭제
- $ rm -rf dname -> 디렉토리(폴더삭제) -> -r은 디렉토리 내부의 모든 내용삭제, -f는 강제로 파일이나 디렉토리를 삭제
- $ rm -rf .git -> 전체 폴더를 삭제하거나 .git 삭제

### echo(입력 및 출력)
- $ echo git bash -> 터미널에 git bash라는 문자열을 출력
- $ echo 'print()' -> 알번 문자열이 아닌 괄호등 특수기호 출력이 필요하다면 따옴표가 필요

### cat(concatenate)
- $ cat file1 -> file1의 내용 출력
- $ cat file1 fil2 -> file1과 file2의 내용을 출력
- $ cat file1 file2 | [more, head, tail] -> | 바 이후 명령어 대로 출력
- more은 페이지별로 head는 처음부터 10번째 줄까지 tail은 끝에서부터 10번째까지 출력

### ls
- $ ls -l -> 파일의 상세정보
- $ ls -a -> 숨김 파일 표시
- $ ls -t -> 파일들은 생성 시간 순으로(최신순) 표시
- $ ls -rt -> 파일들을 생성 시간 순으로(과거순) 표시
- $ ls -f 파일 표시시 마지막 휴형에 나나태는 파일명을 끝에 표시

  ### > 기호
  <p> > 기호 : 기존의 있는 파일 내용을 지우고 저장</p>
  <p> >> 기호 : 기존 파일 내용 뒤에 덧붙여서 저장</p>
  <p> < 기호 : 파일의 데이터를 명령어에 입력</p>

  #### 예시
  echo aaa > a.txt -> a.txt 파일에  aaa를 복사<br>
  echo bbb > a.txt -> a.txt 파일에 bbb를 추가<br>
  cat file 1 file2 > file3 file1과 file2를 합쳐 file3에 저장<br>
  cat file4 >> file3 -> file3에 file4의 내용 추가<br>
  cat < file1 -> file 1의 결과 출력<br>

  <hr>

# 깃 커밋과 로그
깃의 세가지 영역  
- 작업 디렉토리(working directory, working tree)
- 스테이징 영역(staging area, index)
- 깃 저장소(git repository)
작업 디렉토리에서 스테이징 열역으로 옮기려 add를 사용
스테이징 영역의 파일을 깃 저장소로 옮기기 위해 commit 사용

## 커밋 명령어
- $ git add fname -> 파일을 스테이징 영역으로 추가
- $ git commit fname -> 파일을 깃 저장소로 커밋

### 커밋의 추가 명령어
<p>-m 'message' -> 커밋 메세지를 입력 -m 명령어를 사용하지 않으면 기본 편집기가 열려 커밋 메세지를 입력</p>
<p> -a, --all -> 추가와 커밋을 함께 실행</p>
<p>ex) $ git commit -am 'message'</p>


## 로그 이력
- $ git log -> 로그 이력을 표시
- $ git log --oneline -> 로그 이력을 한줄로 표시
- $ git log [--patch, -p] -> 로그 이력과 함꼐 파일의 변화를 표시
- $ git log --graph ->  문자 그림으로 로그 이력 그리기
- $ git log --reverse -> 오래된 커밋부터 표시(--graph와 함께 사용 불가능)
- $ git log --all -> 모든 브랜치의 로그 이력 표시
- $ git log -n 최근 n개의 로그 이력 표

## 커밋 조회 git show
- $ git show -> 마지막 커밋[HEAD]의 커밋 정보 표시
- $ git show --oneline -> 커밋과 로그 한 줄과 파일 차이 표시
- $ git show -s -> 파일 차이는 생략
- $ git show [HEAD] -> 지정한 헤드의 커밋 정보 표시
- $ gir show [commitID] 지정한 commitID의 커밋 정보 표시


## cehckout
- $ git checkout HEAD ~ -> HEAD 이전 커밋으로 이동
- $ git checkout -    -> 바로 이전에 있던 checkout으로 이동
- $ git checkout main -> 브랜치의 마지막 커밋으로 이동
<br>
- HEAD는 현재 분기의 가장 최근의 커밋을 의미
- HEAD~, HEAD^, HEAD~1, HEAD^1 HEAD 바로 이전 커밋을 의미
- HEAD~~, HEAD^^, HEAD~2, HEAD~^ HEAD의 두개 전 커밋을 의미

<hr>

## 파일비교 diff
- $ git diff -> 스테이지 영역과 작업 영역을 비교
- $ git diff [--staged,--cached] (HEAD)-> 깃 저장소 HEAD와 스테이지 영역을 비교
- $ git diff HEAD -> 깃 저장소 HEAD와 작업영역을 비교
- $ git diff HEAD~ HEAD -> 헤드 바로 전 커밋과 헤드 상태를 비교
- $ git diff HEAD~2 HEAD -> 헤드 두개 전 커밋과 헤드 상태를 비교

## 파일 삭제와 복원

### 파일삭제 rm
- $ rm fname -> 작업 디렉토리에서 파일을 삭제
- $ gir rm fname -> 작업 디렉토리와 스테이징 영역에서 모두 파일을 삭제
- $ gir rm --cached fname -> 스테이징 영역에서 파일을 삭제

### 파일복원 restore
- $ git restore fname -> 작업 디렉토리의 파일을 스테이징 영역의 파일상태로 복원
- $ git restore --staged fname -> 깃 저장소의 파일로 스테이징 영역의 파일을 복원
- $ git restore --source=HEAD --staged --worktree fname -> 깃 저장소의 최신 커밋 상태의 파일로 작업 디렉토리와 스테이징 영역의 파일을 복원
- $ git resotre --source=HEAD fname -> 깃 저장소의 파일로 작업디렉토리를 복원
- $ git resotre --source=HEAD -- staged fname -> 깃 저장소의 파일로 스테이징 영역으로 복원

<hr>

# 태그
- $ git tag -a v1.0.0 -m 'first version' -> 작성한 사람의 이메일, 날짜, 매세지 등의 정보를 포함
- $ git tag -a v1.0.0 -> 기본 설정된 편집기로 메세지 편집
- $ git tag -> 예전 태그부터 표시
- $ git show v1.0.0 -> 태그의 정보를 표시
- $ git tag -d v1.0.0 -> 태그를 삭제

## 브랜치
브런치는 분기를 의미 버전관리를 위해 필요  
저장소 생성시 기본인 브랜치는 main <br>

### 브랜치 명령어
- $ git branch -M newBname -> 이미 생성된 저장소의 브랜치 이름을 수정
- $ git branch bname -> 브랜치를 생성 HEAD 이동은 X
- $ git switch -c bname -> 브랜치를 생성하고 HEAD를 거기로 이동
- $ git checkout -b bname -> 브랜치를 생성하고 HEAD를 거기로 이동
- $ git branch -> 커밋이 발생한 브랜치 목록 조회
- $ git branch -v -> 브랜치마다 마지막 커밋ID와 메세지도 함께 표시
- $ git switch bname -> HEAD를 지정한 브랜치로 이동
- $ git checkout bname -> HEAD를 지정한 브랜치로 이동
- $ git switch -  -> HEAD를 이전에 있던 브랜치로 이동
- $ git checkout -  -> HEAD를 이전에 있던 브랜치로 이동
- $ git branch [-d, --delete] bname -> 지정한 병합되어있는 브랜치를 삭제
- $ git branch -D bname -> 병합이 안되어있어도 브랜치를 삭제
- $ git branch --merged -> 현재 브랜치를 기준으로 병합된 브랜치를 표시
- $ git branch --no --merged -> 현재 브랜치를 기준으로 병합되지 않은 브랜치를 표시
- $ git branch --merged bname -> 지정한 브랜치를 기준으로 병합된 브랜치를 표시
- $ git branch --no --merged bname -> 지정한 브랜치를 기준으로 병합되지 않은 브랜치를 표시

<hr>

# 원격저장소 복제 clone
- $ git clone 복사된 주소 -> 원격저장소와 동일한 이름으로 복제
- $ git clone 복사되 주소 새폴더명 -> 지정한 이름으로 하부폴더를 생성하고 원격저장소를 복제
- $ git remote -> 원격 저장소 목록 조회
- $ git remote -v -> 원격저장소 정보 목록 표시
- $ git remote add nname URL -> 원격저장소 별칭 저장
- $ git remote show nname -> 자세한 정보 조회
- $ git remote rename nname nnname -> 별칭수정
- $ git remote rm name -> 삭제

## push pull
- push는 원격 저장소로 저장을 의미
- pull은 원격 저장소에서 지역 저장소로 당겨오는걸 의미
- $ git push <저장소별칭명> <브랜치명> -> 한번 사용하고 나면 $ git push만으로 사용가능
- $ git fetch <저장소별칭명> -> 원격 자장소에서 로컬로 소스를 가져옴
- $ git merge <저장소별칭명>/main -> fetch후 병합


<hr>

### 오픈소스소프트웨어
- 누구나 특별한 제한없이 코드를 보고 사용 할 수 있는 오픈소스 라이선스를 만족하는 SW
- OSI애서 라이선스를 관리
- 소프트웨어의 소스코드를 자유롭게 읽고 수정 및 재배포가 가능
- 저작권은 존재하므로 원저작자가 허용하는 범위에따라 SW를 사용

## 임시저장 stash
커밋할 필요 없이 파일의 변경사항을 숨기거나 잠시 저장할 수 있는 강력한 도구<br>
기본적인 세가지 영역이 아닌 임시저장소에 따로 보관함

### stash 명령어
- $ git stash
- $ git stash -m 'message'
- $ git stash save
- $ git stash save 'message'
(--keep-index, -k) 스테이징 영역은 제외하고 작업폴더만 저장
(--include-untracked, -u) untracked 파일도 포함해서 저장
- $ git stash apply (stash@{n}) -> 작업 디렉토리 내용만 다시 복사 
- $ git stash apply --index (stash@{n}) -> 스테이지 영역도 함꼐 복사
-p, --patch 옵션 -> 변경된 모든 사항을 저장하는게 아니라 대화형 프롬프트로 stash애 저장할 것을 따로 지정 가능
- $ git stash list -> stash 목록 조회
- $ git stash show @{n}-> 최신 커밋과 stash의 차이를 표시
- $ git stash show @{n} -p-> 최신 커밋과 stash의 차이를 표시(내용도 함께 표시)
- $ git stash pop -> 최근 stash 내용을 가져와 반영하고 삭제
- $ git stash pop stash@{n} -> 지정한 임시저장소 내용을 가져와 반용하고 삭제
- $ git stash deop -> 최근 임시저장된 내용을 삭제
- $ git stash drop stash@{n} -> 지정한 임시저장 내용을 삭제
- $ git stash clear -> 모든 임시저장 내용을 삭제
- $ git clean -> untracked 파일 삭제 -f 옵션을 주면 무조건 삭제

<hr>

## merge
- $ git merge
- $ git merge --no-ff 병합할 브랜치명 -> 3way 병합 수행
- $ git merge --ff-only 병합할 브랜치명 -> fast-forward인 경우에만 병합
- $ git merge --squash 병합할 브랜치명 -> 현재 브랜치에서 커밋 하나만 생성해서 병합(병합되는 브랜치 이력을 남기지 않음)
- $ git merge --abort -> 병합취소(두 브랜치에서 모두 파일 수정이 있다면 충돌하므로 취소하고 해결한 후 다시 진행 )

### 병합 종류
- fast-forward merge의 경우 현재 브랜치가 병합할 대상 커밋의 직접적인 조상일 경우 진행되며 간단히 main(master)의 위치가 그 커밋으로 이동되는 형태로 병합 진행
- 3-way 병합은 새로운 커밋을 이용하여 두 기록을 합치는 방식으로 진행
