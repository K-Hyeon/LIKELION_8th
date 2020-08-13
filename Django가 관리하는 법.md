## Django가 관리하는 방법
##### 템플릿 언어를 활용해 여러 페이지를 관리하고 Static File을 활용하는 방법에 대해 알아 봅시다.
### < Bootstrap 적용 >
* Bootstrap이란?
#### : Front-End 개발을 빠르고 쉽게 할 수 있는 오픈 소스 Framework
#### > 누구나 쉬운 사용 가능
#### > 반응형 CSS 제공
#### > 모든 최신 브라우저와 호환
#### > PC & 모바일 디자인 제공


### < URL / Template 언어 이해 & 구현 >
* URL 관리는 어떻게?
#### : Django의 URL 관리는 urls.py의 urlpatterns에서 담당
####  Path의 구조 path('URL',views 내부의 함수, name="url의 이름"),
#### > 'URL' : 페이지 주소(ex.introduce/, new/)
#### > 함수 : url이 불렸을 때 실행할 함수(ex.views.home)
#### > name : 해당 path를 대표하는 이름(ex.name = "home")

* Template 언어란?
#### : Python 변수 & 문법을 HTML에서 쓸 수 있도록 Django에서 제공하는 언어



### < Static 파일 (Image,CSS)이해
* Static File이란?
#### 이미지나 CSS, JS파일처럼 내용이 고정되어 있어, 응답을 할 때 파일 그대로를 보내주면 되는 파일
##### Static : 앱 서비스를 위해, 개발자가 준비해두는 파일
##### Media : 웹 서비스 이용자들이 업로드하는 파일

* Static File 처리하기
#### 1. Static 폴더 생성 : App폴더 내에 static 폴더 만들기 & 파일 생성
#### 2. Settigs.py(Static 설정)
~~~ 
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'App 이름', 'static'
     ] #Static File 들이 들어있는 경로

STATIC_ROOT = os.path.join(BASE_DIR, 'static')
#static File을 모을 디렉토리
~~~
#### 3. Static 파일 모으기 : python manage.py collectstatic
