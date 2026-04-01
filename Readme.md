#Codyssey
# 터미널 작업 로그
![이미지설명](./log.jpg) ** 이렇게하면 images에 있는 사진을 넣을수 있음.
![txt파일설명](./txt/택스트.txt)

# Github로 보내기 **중요**
## 1. 사진 파일을 저장소에 추가
git add log.jpg
## 2. 사진 추가했다는 메시지 남기기
git commit -m "docs: 실습 로그 스크린샷 추가"
## 3. GitHub로 보내기
git push -v

# 과제 (E-1)
## README.md란?
README.md는 프로젝트의 설명서 같은 파일
github에 보이는 첫 페이지!!

## 1. 제출 저장소
 - 공개로 설정한다
 - 저장소 링크만으로 아래 산출물 전부 확인 가능
  - 1. github 저장소 만들기
    2. Pubilc(공개)로 설정
    3. 과제파일 올리기 // 커멘드+s or ctrl+s 필수!!!
        1) git add .            //변경된 모든파일을 스테이징에 담음 
        2) git commit -m "내용"  //내용에는 파일 설명 / 내가 기억할 수 있는 이름
        3) git status           //내가 올릴 파일 확인 ** 초록색 및 저장필수!!!
        4) git remote -v        //깃허브 주소 다시 확인
        5) git push -v          //github에 올리기

## 2. 기술 문서 (README.md 등)
### 프로젝트 개요(미션 목표 요약)
    - 개발 환경 세팅을 스스로 수행
    - 터미널 CLI, Docker 컨테이너, Git 버전 관리의 핵심 원리를 이해, 재현 가능한 개발 환경을 구축

### 실행 환경(OS/쉘/터미널, Docker 버전, Git 버전)
![실행환경확인](./images/실행환경.png) 

```bash
sonjehyun1231743@c5r9s7 Codyssey % sw_vers && sysctl -n machdep.cpu.brand_string
ProductName:            macOS
ProductVersion:         15.7.4
BuildVersion:           24G517
Intel(R) Core(TM) i5-8600 CPU @ 3.10GHz
sonjehyun1231743@c5r9s7 Codyssey % echo $SHELL
/bin/zsh
sonjehyun1231743@c5r9s7 Codyssey % docker --version
Docker version 28.5.2, build ecc6942
```
    - OS:       macOS 15.7.4                        // sw_vers && sysctl -n machdep.cpu.brand_string
    - Shell:    /bin/zsh                            // echo $SHELL
    - Docker:   ocker version 28.5.2, build ecc6942 // docker --version
    - Git:      git version 2.53.0                  // git --version


### 수행 항목 체크리스트(터미널/권한/Docker/Dockerfile/포트/볼륨/Git/GitHub)
[v] 터미널 기본 조작 및 폴더 구성 (mkdir, ls, cd)
![터미널](./images/터미널%20기본조작%20및%20폴더구성.png)
```bash
sonjehyun1231743@c5r9s7 Codyssey % mkdir work #work 디렉토리 생성
sonjehyun1231743@c5r9s7 Codyssey % ls #Codyssey안에 있는 파일이름 확인
images          Readme.md       txt             work
sonjehyun1231743@c5r9s7 Codyssey % ls -l #파일의 정보 확인
total 8
drwxr-xr-x  3 sonjehyun1231743  sonjehyun1231743    96 Apr  1 23:39 images
-rw-r--r--  1 sonjehyun1231743  sonjehyun1231743  2701 Apr  1 23:52 Readme.md
drwxr-xr-x  3 sonjehyun1231743  sonjehyun1231743    96 Apr  1 23:42 txt
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743    64 Apr  2 01:32 work
sonjehyun1231743@c5r9s7 Codyssey % cd work #work안으로 들어감
sonjehyun1231743@c5r9s7 work % pwd #work의 절대 주소 확인
/Users/sonjehyun1231743/Codyssey/work
sonjehyun1231743@c5r9s7 work % cd .. #work의 상위폴더인 Codyssey로 이동
sonjehyun1231743@c5r9s7 Codyssey % pwd #Codyssey의 절대 주소확인
/Users/sonjehyun1231743/Codyssey
```

[v] 파일 및 디렉토리 권한 변경 실습 (chmod)
![권한](./images/chmod.png)
```bash
sonjehyun1231743@c5r9s7 E1 % pwd # work에 E1만듬
/Users/sonjehyun1231743/Codyssey/work/E1
sonjehyun1231743@c5r9s7 E1 % ls -l # D1 D2 D3권환 확인
total 0
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D1
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D2
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D3
sonjehyun1231743@c5r9s7 E1 % chmod u-r D1 # chmod로 u(User)에게 r(Read)능력을 뻄
sonjehyun1231743@c5r9s7 E1 % ls-l # 띄어쓰기 주의
zsh: command not found: ls-l
sonjehyun1231743@c5r9s7 E1 % ls -l #권한 확인
total 0
d-wxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D1 #D1에서 u부분에 r사라진 모습
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D2
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D3
sonjehyun1231743@c5r9s7 E1 % chmod u+r D1 # chmod로 u(User)에게 r(Read)능력을 다시 넣음
sonjehyun1231743@c5r9s7 E1 % ls -l
total 0
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D1 # 원상 복구
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D2
drwxr-xr-x  2 sonjehyun1231743  sonjehyun1231743  64 Apr  2 01:41 D3
```

[v] Docker 설치 및 환경 점검 (docker info)
![도커](./images/docker.png)
```bash
onjehyun1231743@c5r9s7 e1 % docker --version # 도커 유무/버전 확인
Docker version 28.5.2, build ecc6942
sonjehyun1231743@c5r9s7 e1 % docker info | tail -5 # 도커 상태 리포트
WARNING: DOCKER_INSECURE_NO_IPTABLES_RAW is set
   Base: 192.168.239.0/24, Size: 24
   Base: 192.168.242.0/24, Size: 24
   Base: 192.168.247.0/24, Size: 24
   Base: fd07:b51a:cc66:d000::/56, Size: 64

sonjehyun1231743@c5r9s7 e1 % docker images #도커 설계도 목록을 보여줌
REPOSITORY    TAG       IMAGE ID       CREATED      SIZE
hello-world   latest    e2ac70e7319a   8 days ago   10.1kB
sonjehyun1231743@c5r9s7 e1 % docker ps -a #현재 만들어진 모든 컨테이너의 상테를 보여줌 (-a == ALL)(아이디/이미지/명령어/생성시점/현재상태/포트/컨테이너 이름)
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
628eae8260a9   hello-world   "/hello"   28 minutes ago   Exited (0) 28 minutes ago             recursing_williamson
sonjehyun1231743@c5r9s7 e1 % docker logs   #컨테이너 안 모든 로그를 화면에 띄움
docker: 'docker logs' requires 1 argument

Usage:  docker logs [OPTIONS] CONTAINER

Run 'docker logs --help' for more information #컨테이너가 사용하는 리소스를 실시간 중계
sonjehyun1231743@c5r9s7 e1 % clear
CONTAINER ID   NAME      CPU %     MEM USAGE / LIMIT   MEM %     NET I/O   BLOCK I/O   PIDS  
```

[v] Dockerfile 기반 웹 서버 컨테이너
![도커파일](./images/터미널%20기본조작%20및%20폴더구성.png)
```bash

```

[v] 포트 매핑을 통한 브라우저 접속 확인(2회)
![포트](./images/터미널%20기본조작%20및%20폴더구성.png)
```bash

```

[v] Docker 볼륨을 이용한 데이터 영속성 검증
![볼륨](./images/터미널%20기본조작%20및%20폴더구성.png)
```bash

```

[v] Git 설정 및 GitHub 저장소 연동 완료
![깃허브](./images/터미널%20기본조작%20및%20폴더구성.png)
```bash

```
### 검증 방법(어떤 명령으로 무엇을 확인했는지) + 결과 위치 링크
    - 결과 위치 링크 방법: ![설명](이미지.png)
### 트러블슈팅 2건 이상(문제 → 원인 가설 → 확인 → 해결/대안)
    **문제**        
    **원인/가설**    
    **확인**        
    **해결/대안**
    (확인 -> 문제해결 실패-> 다시 원인/가설)
### 기술 문서만 읽어도 전체 수행 내용 파악 가능
    **목표**
    **환경**    
    **과정**
    **결과**