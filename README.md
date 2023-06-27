# NBC_week6_1

* 작성한 API 명세
  * 링크: https://www.notion.so/06-20-6-1-4c5c4929fb6d40b49b4d71401696dfd0?pvs=4#856ae5d6490744d58544c71d6a6eb54b
 
====================================== 
 1. 회원 가입 API (/api/user/signup)
    - username과 password를 json 형식으로 보내 글자 수, 입력 제한 등에 대한 유효성 검사를 하고 적합하면 DB에 저장합니다.
 
 2. 로그인 API (/api/user/login)
    - username과 password를 json 형식으로 보내 글자 수, 입력 제한 등에 대한 유효성 검사와 DB 존재 유무를 판단하여 존재한다면 JWT를 생성하여 이를 통해 제한된 기능(게시, 수정, 삭제)을 가능하게 합니다.

 3. POST API
 
 a. 전체 조회 (/api/post**s**)      --  토큰 없이 api 만으로도 기능 사용 가능
 
 b. 선택 조회 (/api/post**s**/{id}) -- 토큰 없이 api 만으로도 기능 사용 가능

	** 전체 조회와 선택 조회의 api는 인증을 진행하지 않기 때문에 이를 나타내기 위해 경로를 post's'로 구별했습니다.
 
 c. 글 게시  (/api/post)        -- header에 JWT를 등록하고 title과 contents를 json 형식으로 전송하여 글 게시
 
 d. 글 수정  (/api/post/{id})   -- header에 JWT를 등록하고 수정할 title과 contents를 json 형식으로 전송하여, 수정할 글 번호를 @PathVariable로 전송하여 글 수정
 
 e. 글 삭제  (/api/post/{id})   -- header에 JWT를 등록하고 삭제할 글 번호를 @PathVariable로 전송하여 글 삭제
