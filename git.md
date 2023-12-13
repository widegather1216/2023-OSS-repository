<h1>깃설정</h1>

## 주요 설정 변수
<p>기본 편집기 설정 core.editor ['code --wait' | 'notepad']</p> 
<p>줄 바꿈 자동변환 core.autocrlf[true,flase]</p>
<p>사욜자 이름 설정 user.name 사용자 이름 -> ex) user.name admin</p>  
<p>사용자 이메일 성정 user.email</p>  
<p>기본 브런치 이름 init.defaultBranch 브런치 이름 -> ex) init.defaultBranch main</p>

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


# 저장소 생성
