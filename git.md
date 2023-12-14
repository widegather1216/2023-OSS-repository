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



