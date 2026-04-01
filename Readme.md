#Codyssey
# 터미널 작업 로그
![로그 이미지](./log.jpg) ** 이렇게하면 images에 있는 사진을 넣을수 있음.

# Github로 보내기 **중요**

## 1. 사진 파일을 저장소에 추가
git add log.jpg

## 2. 사진 추가했다는 메시지 남기기
git commit -m "docs: 실습 로그 스크린샷 추가"

## 3. GitHub로 보내기
git push

# 과제 (E-1)
## README.md란?
README.md는 프로젝트의 설명서 같은 파일
github에 보이는 첫 페이지!!

## 1. 제출 저장소
 - 공개로 설정한다
 - 저장소 링크만으로 아래 산출물 전부 확인 가능
  - 1. github 저장소 만들기
    2. Pubilc(공개)로 설정
    3. 과제파일 올리기
        1) git add .            //변경된 모든파일을 스테이징에 담음 
        2) git commit -m "내용"  //내용에는 파일 설명 / 내가 기억할 수 있는 이름
        3) git status           //내가 올릴 파일 확인 **
        4) git remote -v        //깃허브 주소 다시 확인
        5) git push -v          // 