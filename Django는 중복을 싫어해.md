## Django는 중복을 싫어해
##### URL과 Template을 효율적으로 관리하는 법을 알아 봅시다.

### < URL Include 이해 & 구현 >
* URL Include 
#### : App 별로 URL을 관리할 수 있도록 구조화

* URL Include
#### 1. App : App 폴더 내에 urls.py 생성 후,
~~~
from django.urls import path
from .import views

Urlpatterns = [~~~]
~~~
#### 1. Project/urls.py
~~~
    from django.urls import path include
 
     urlpatterns = [
     path('url/', include('app이름.urls'))
     ]
~~~

### < Template 상속 구현 >

