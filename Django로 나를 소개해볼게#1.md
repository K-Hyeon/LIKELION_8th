## Django로 나를 소개해볼게 #1
##### Model과 Admin에 대해 알아 봅시다.
### < Model 이해 >
* Model이란?
#### : 데이터에 접속하고 관리하도록 도와주는 객체

* Model 생성 & 적용
#### 1. models.py : #모델명의 첫 글자는 무조건 대문자 !
~~~
<div>
class Designer(models.Model):
    image = models.ImageField(upload_to = 'images/')
    name = models.CharField(max_length = 50)
    address = models.CharField(max_length = 255)
    description = models.TextField()
<div>
~~~
#### 2. Terminal
#### DB가 알아 듣도록 번역하기
~~~
python manage.py makemigrations(+App 이름)
~~~
#### 번역할 내용을 DB에 적용
~~~
python manage.py migrate(+App 이름)
~~~

### < Model과 Database의 연동 이해 & 실습 >



### < Admin 파악 >
* Admin 기능
#### : Django는 웹 서비스를 관리를 위한 admin 기능 기본 제공

* Admin에게 Model 알려주기
~~~
from .models import Designer
~~~
~~~
admin.site.register(Designer)
~~~
