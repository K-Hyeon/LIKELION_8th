## CRUD#1
##### Django를 활용해 Create, Read, Update, Delete를 구현해 봅시다.

### CRUD 개념 이해


### GET/POST 이해
* GET/POST
#### : 클라이언트에서 서버로 요청을 보내는 방법
** GET
#### > Data를 "URL"에 포함시켜 전송
#### > 전송하는 길이에 제약 ㅇ
#### > Caching 가능 (REST에서 데이터 조회에 활용) 
#### -> READ에서 활용

** POST
#### > Data를 "Body"에 넣어 전송(URL에서 노출X)
#### > 전송하는 길이에 제약 X
#### > Caching 불가능(REST에서 데이터 생성에 활용)
#### -> CREATE / UPDATE에서 활용

* CREATE : 새로운 객체를 생성해 Data를 저장
** 객체 생성
~~~
if request.method == 'POST':
	post = Designer()
~~~
** 입력 Data 저장
~~~
post.name = request.POST['name'] 
post.address = request.POST['address']…
~~~
** 입력 Data 저장
~~~ 
post.save()
~~~

* UPDATE : 정보 수정이 필요한 객체를 찾아 Data를 새롭게 저장
** 객체 탐색
~~~
post=get_object_or_404(Designer, pk = designer_id)

if requset.mothod == 'POST':
~~~
** 입력 Data 저장
~~~
post.name = request.POST['name']
post.address = request.POST['address']…
~~~
~~~
post.save()
~~~

* DELETE : 제거가 필요한 객체를 찾아 삭제
** 객체 탐색 : post = get_object_or_404(Designer, pk = designer_id)
** 객체 삭제 : post.delete()
** Home으로 이동 : return redirect('home') 
