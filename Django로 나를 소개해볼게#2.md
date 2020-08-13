## Django로 나를 소개해볼게 #2
##### QuerySet & Method에 대해 알아보고, PK, get_object_or_404를 활용해 봅시다.

### QuerySet, Method 이해 & 구현
* QuerySet 이란?
#### : 전달받은 모델의 객체 목록
** views.py 
~~~
##### # Model의 존재 알려주기
from .models import Designer
~~~
##### # Queryset을 Templates로 보내기
~~~
def home(request):
    designers = Designer.objects.all()
    return render(request, 'home.html' ,{'designers':designers})
~~~


### PK, Path Convertor, get_object_404 이해
* Detail Page 구현
** 각각의 글을 어떻게 분류하지? -> PK(Primary Key)
** urls.py에서 글마다 Path를 만들어야 하는 건가? -> Path Convertor
** 만약 없는 글을 불러오려고 하면 어쩌지? -> get_object_or_404

* PK(Primary Key)
#### : Model을 통해 생성된 객체들을 구분할 수 있는 "고유한" Key


* Path Convertor
#### : 여러 객체의 url를 "계층적으로" 다룰 수 있도록 도와주는 도구

* get_object_or_404
#### : Object를 가져오려 했는데 없을 경우 나타나는 에러

* Detail Page 구현 정리
#### 1. Server에게 특정 객체를 달라고 Request
#### 2. 이에 대한 URL을 서버에게 알림
#### 3. 객체 반환 or 404 Error 호출

