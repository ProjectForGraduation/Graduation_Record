### 유저등록하는 html페이지
`http://13.124.115.238:8080/insertUser`

### 글등록하는 html페이지 
> user_id:7로만 전송

`http://13.124.115.238:8080/insertContents`
### GET 모든유저보기
`http://13.124.115.238:8080/user`
### GET 모든글보기
`http://13.124.115.238:8080/contents/all`

### GET 모든글보기 (로그인 되어있을경우)
_req.body_

- user_id
- 전체글보기라도 user_id가 있어야 그글을 좋아요했는지 안했는지 


_res.json_

- contents의 모든속성
- user_info.user_name

### POST user_id인 사람 글쓰기
`http://13.124.115.238:8080/contents/:id`

_req.body_

- content_text
- share_range
- location_range
- has_image
	- 0 : 이미지 없음
	- 1 : 이미지 첨부함

### POST like
`http://13.124.115.238:8080/contents/like`
_req.body_

- content_id
- user_id
- is_like
  - contents에 좋아요 안했을 경우에는 null
  - null일 경우에는 1을 보내주고
  - 좋아요가 되있으면 0을 보내줌
  - 기본적으로 글보기했을때 좋아요는 null인 상태이니깐 클라이언트에서 판단해서 1이나 0을 보내줘야함


### PUT
`PUT http://13.124.115.238:8080/contents/:contents_id`

- req.body post와 동일
- 이미지 없던 글에서 이미지 있는 글로 업데이트 하는거 아직안함

### DELETE
`DELETE http://13.124.115.238:8080/contents/:contents_id`
