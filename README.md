# NBC_week6_1
	** 전체 조회와 선택 조회 api는 인증을 진행하지 않기 때문에 이를 나타내기 위해 경로를 api/posts로 구별했습니다.

* 작성한 API 명세

|API 명|Method|URL|Request Header|Request|Response|Response Header|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|회원가입|POST|api/user/signup||{"username": "part", "password": "partial123"}|{ ‘msg’ : ‘완료’,‘status’ : 200 }||
|로그인|POST|api/user/login||{"username": "part", "password": "partial123"}|{ ‘msg’ : ‘완료’,‘status’ : 200 }|Header : {"Authorization" : "Bearer... "}|
|전체 게시글 조회|GET|api/posts|||[ {"title": "title from part", "username": "part", "contents": "content from part", "createdAt": "2023-06-28T10:00:04.032185", "modifiedAt": "2023-06-28T10:00:04.032185"},  {"title": "good", "username": "part", "contents": "no, bad", "createdAt": "2023-06-28T09:59:48.081672", "modifiedAt": "2023-06-28T10:00:56.025748"} ]||
|선택 게시글 조회|GET|api/posts/{id}|||{"title": "title from part", "username": "part", "contents": "content from part", "createdAt": "2023-06-28T10:00:04.032185", "modifiedAt": "2023-06-28T10:00:04.032185"}||
|게시글 생성|POST|api/post|Header : {"Authorization" : "Bearer... "}|{ ‘title’ : ‘제목’,‘contents’ : ‘내용’}|{‘title’ : ‘제목’,‘username’ : ‘KHY’,‘contents’ : ‘내용’,"createdAt": "2023-06-28T10:00:04.032185", "modifiedAt": "2023-06-28T10:00:04.032185"}||
|게시글 수정|PUT|api/post/{id}|Header : {"Authorization" : "Bearer... "}|{ ‘title’ : ‘제목 수정’,‘contents’ : ‘내용 수정’ }|{‘title’ : ‘제목 수정’,‘username’ : ‘KHY’,‘contents’ : ‘내용 수정’,"createdAt": "2023-06-28T10:00:04.032185", "modifiedAt": "2023-06-28T10:00:04.032185"}||
|게시글 삭제|DELETE|api/post/{id}|Header : {"Authorization" : "Bearer... "}||{ ‘msg’ : ‘삭제 성공’,‘status’ : 200 }||
 
