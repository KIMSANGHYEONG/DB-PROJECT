# DB-PROJECT

# Project



## 커뮤니티


첫 화면 : 로그인 해야 게시판으로 넘어갈 수 있음

* 로그인
* 회원가입

회원가입 시 화면 :

| **아이디**   |      |
| ------------ | ---- |
| **비밀번호** |      |
| **닉네임**   |      |



로그인 시 메인화면 : 다음 중 선택 가능

| 글 목록 | 글 쓰기 | 내 글 |
| ------- | ------- | ----- |



글 목록 : 

* READ를 이용해 모든 글목록 불러오기

글 쓰기 : 

* INSERT를 통한 데이터 삽입

내 글

* READ를 이용해 내가 쓴 글 불러오기
* UPDATE로 내가 쓴 글 수정 가능
* DELETE를 이용해 글 삭제 가능



## TABLE


![image](https://user-images.githubusercontent.com/81346173/168541651-b97169f9-70f5-454b-97b1-c018ca5a7be1.png)


## 요구사항 명세서

1. 커뮤니티에 □회원, □작성자 또는 □관리자로 가입 하려면 ○아이디, ○비밀번호, ○닉네임을 입력해야 한다.
2. 회원과 작성자는 아이디로 식별한다.
3. 글은 글 번호로 식별한다.
4. 댓글은 댓글 번호로 식별한다.
5. 회원은 여러 글에 대해 댓글을 달 수 있고, 하나의 글에 여러 회원이 댓글을 달 수 있다.
6. □댓글에 대한 ○댓글 번호, ○글 번호, ○닉네임, ○댓글을 유지해야한다.
7. 각 글은 한 작성자가 작성하고, 작성자는 여러 글을 작성할 수 있다.
8. □글에 대한 ○글 번호, ○닉네임, ○제목, ○본문을 유지해야한다.
9. 관리자는 회원과 작성자를 관리할 수 있다.
10. 관리자는 모든 글과 댓글에 대해 삭제할 수 있다.
11. 관리자는 아이디로 식별한다.

## 릴레이션 스키마
![image](https://user-images.githubusercontent.com/81346173/169763206-e71bcd33-9d8a-49e8-a7fc-472d428f9759.png)

## 테이블
CREATE TABLE 회원(
  회원아이디 VARCHAR(20) NOT NULL,
  비밀번호 VARCHAR(20) NOT NULL,
  닉네임 VARCHAR(20) NOT NULL,
  PRIMARY KEY(회원아이디)
);

CREATE TABLE 관리자(
  관리자아이디 VARCHAR(20) NOT NULL,
  비밀번호 VARCHAR(20) NOT NULL,
  닉네임 VARCHAR(20) NOT NULL,
  PRIMARY KEY(관리자아이디)
);

CREATE TABLE 작성자(
  작성자아이디 VARCHAR(20) NOT NULL,
  비밀번호 VARCHAR(20) NOT NULL,
  닉네임 VARCHAR(20) NOT NULL,
  PRIMARY KEY(작성자아이디)
);

CREATE TABLE 댓글(
  댓글번호 INT
