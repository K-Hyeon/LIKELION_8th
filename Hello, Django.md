## Hello, Django 
##### 가상환경, PIP, 그리고 Django에 대해 알아보고 페이지를 출력해 봅시다.

### < 가상환경 & PIP 이해 >
* 가상환경이란?
#### : 자신이 원하는 Python환경 구축을 위해 필요한 모듈만 담아 놓은 바구니

* PIP란?
#### : Python으로 작성된 패키지 소프트웨어를 관리하는 패키지 관리 시스템



### < Django 프로젝트 생성 & 구조파악 >

* VS Code 단축키 모음
##### [터미널 생성] : Ctrl + Shift + ~
##### [터미널에서 이전에 썼던 명령어 불러오기] : 터미널에서 윗 화살표 키 누르기
##### [현재 커서 위치의 코드 복사] : Ctrl + D (여러 줄 복사도 가능)
##### [현재 커서 위치의 코드 이동] : Alt + 윗 화살표 또는 아래 화살표

* 가상환경 명령어 모임
##### [가상환경 생성] : python-m venv <가상환경 이름>
##### [가상환경 활성화] 
##### : 윈도우 -> source <가상환경 이름>/Script/activate 
##### Linux, Mac -> source <가상환경 이름>/Bin/activate
##### [가상환경 끄기] : deactivate

* Django 명령어 모음 
##### [Django 패키지 설치] : pip install django
##### [Django 프로젝트 생성] : django-admin startproject <프로젝트명>.
##### (마지막에 온점을 붙이지 않으면 새로운 폴더가 생성되지 않습니다.)
##### [Django App 생성] : python manage.py startapp <App 이름>
##### [Django 로컬서버 시작] : python manage.py runserver

### <실습>
#### 1. 비주얼 스튜디오 실행 후 터미널 열기 (Ctrl + Shift + ~)
#### 2. Ctrl + Shift + p / Terminal:Select/Gitbash
#### 3. 폴더 열기(Dreamary_Class)
#### 4. 터미널에 붙여넣기
~~~
echo "# Dreamary_Class" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/K-Hyeon/Dreamary_Class.git
git push -u origin master
~~~
#### 5. 새폴더 -> gitignore
#### 6. 검색창에 gitignore.io -> VisualStudioCode Django Python -> 생성 -> 복사해서 gitignore에 붙여넣기
#### 7. 터미널에 코드 작성
~~~
git add .
~~~
~~~
git commit -m "Add Gitignore"
~~~
~~~
git push origin master
~~~
~~~
python3 -m venv venv
~~~
~~~
source venv/bin/activate
~~~
~~~
pip install django
~~~
~~~
pip install --upgrade pip
~~~
~~~
django-admin startproject dreamaryproject .
~~~
~~~
python manage.py runserver
~~~
~~~
python manage.py startapp page
~~~


* Django의 Project & App
#### : 하나의 Project == 하나의 Web Site
#### Project 안의 의미 있는 기능들을 각각의 App으로 관리

#### [Project]
#### settings.py : 전체 프로젝트를 관리하는 설정 파일
#### urls.py : 프로젝트의 URL 관리 파일
#### wsgi.py, asgi.py : 프로젝트를 서비스하기 위한 파일
#### __init__.py : 해당 디렉토리가 Python Package의 일부임을 Python에게 알려주는 파일
#### [App]
#### views.py : 웹 요청을 받고, 전달받은 데이터를 처리해서 가공하는 파일
#### models.py : Database와 관련된 다양한 역할 수행
#### admin.py : 관리자 관련 파일
#### apps.py : Project에게 App의 존재 알려줄 때 활용되는 파일


* Home 페이지 출력하기
#### 1. settings.py
#### : Project에게 App의 존재 알리기
#### 2. Templates
#### : User에게 보여줄 HTML 파일 만들기
#### 3. views.py
#### : 요청이 들어오면 HTML 파일을 열어주는 함수 정의
#### 4. urls.py
#### : url 요청을 views와 연결하기


### < Local Server에서 페이지 출력 >
