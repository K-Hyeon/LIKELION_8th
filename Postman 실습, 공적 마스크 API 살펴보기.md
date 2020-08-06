## REST API 실습, Open API


### < [JSONPlaceholder](http://jsonplaceholder.typicode.com/) >
#### * Fake online REST API를 제공해주는 사이트
#### * REST API를 테스트, 프로토타이핑 가능
#### * 실습할 내용 : GET, POST, PUT, PATCH, DELETE
#### ** Resources, Routes에 주목
### < URL의 구성 >
#### * 프로토콜 : http, https, file 등
#### * 호스트주소 : www.navaer.com, www. google.com
#### * 파일경로 : /home, /index.html
#### * Query parameter : ?id=1&postld=1(검색, 필터링, 데이터 교환 시 사용)
 

### < Postman 실습 >
#### 1. '+' 버튼(Untitled Request)
#### 2. GET 매소드로 요청([http://jsonplaceholder.typicode.com/posts](http://jsonplaceholder.typicode.com/posts))
#### 3. 'Send' 버튼
#### 4. '+' 버튼
#### 5. 같은 URL을 POST 매소드로 요청
#### 6. GET 매소트의 8번 글을 복사
~~~

  {
    "userId": 1,
    "id": 8,
    "title": "dolorem dolore est ipsam",
    "body": "dignissimos aperiam dolorem qui eum\nfacilis quibusdam animi sint suscipit qui sint possimus cum\nquaerat magni maiores excepturi\nipsam ut commodi dolor voluptatum modi aut vitae"
  }
  ~~~
#### 7. POST 매소드에서 (Body - raw - JSON)에 붙여넣기
#### 8. 'Send' 버튼
#### 9. "comments": [], 을 추가
~~~

  {
    "userId": 1,
    "id": 8,
    "comments": [],
    "title": "dolorem dolore est ipsam",
    "body": "dignissimos aperiam dolorem qui eum\nfacilis quibusdam animi sint suscipit qui sint possimus cum\nquaerat magni maiores excepturi\nipsam ut commodi dolor voluptatum modi aut vitae"
  }
  ~~~
  #### 결과
~~~
  {
  "userId": 1,
  "id": 101,
  "comments": [],
  "title": "dolorem dolore est ipsam",
  "body": "dignissimos aperiam dolorem qui eum\nfacilis quibusdam animi sint suscipit qui sint possimus cum\nquaerat magni maiores excepturi\nipsam ut commodi dolor voluptatum modi aut vitae"
}
~~~
#### 10. http://jsonplaceholder.typicode.com/posts/n
#### : id가 n인 POST를 가져옴
#### PATCH 매소드는 보내는 것만 수정되지만 PUT 매소드는 그대로 바꿔짐
 
### < Open API >


### < 공적마스크 API 살펴보기 >
