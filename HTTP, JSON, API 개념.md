# HTTP, JSON, API, REST API

## HTTP(Hyper Text Transfer Protocol)

#### * Hyper Text : 참조를 통해 한 문서에서 관련된 다른 문서들로 넘나들며 원하는 정보를 얻을 수 있게 해주는 텍스트
#### ex) 유튜브

#### * Transfer Protocol : 인터넷을 통해서 정보를 주고받을 떄 지켜야하는 규칙 

#### * HPPT의 구성 : Request 요청, Response 응답

### < HTTP의 요청 메소드>
#### * GET(읽기) : URL에 표시된 리소스를 가져오기
#### * POST(쓰기) : body에 정보를 담아 서버에 입력
#### * PUT(수정) : URL에 표시된 리소스와 바꿔 치기
#### * PATCH(수정) : PUT과 다르게 일부만 수정
#### * DELETE(삭제) : URL에 표시된 특정 리소스를 삭제


## JSON(Java Script Object Notation)
#### * Key : Value 형식
##### 파이썬의 딕셔너리와 비슷한 형태임

#### * 데이터 교환 
#### : JSON 형식을 자주 사용, 이전에는 XML이라는 형식도 사용했었다. 

### < JSON의 특징 >
#### 1. 기존 XML보다 가볍다.
#### 2. 많ㅇ은 프로그래밍 언어가 지원한다.
#### 3. 전송 시 : 직렬화 과정을 거친다.
#### 4. 수신 시 : 역직렬화 과정을 거친다.


### < 슬습 > 
#### 1. Chrome 접속 -> F12 -> Console
#### 2. [MDN json](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON) -> [JSON TEXT](https://mdn.github.io/learning-area/javascript/oojs/json/superheroes.json) ->  super_hero라는 변수에 담음
#### members안에는 리스트가 들어있고, 하나의 오브젝트에는 한사람을 표현 !
``` 
 let super_hero = {
  "squadName" : "Super Hero Squad",
  "homeTown" : "Metro City",
  "formed" : 2016,
  "secretBase" : "Super tower",
  "active" : true,
  "members" : [
    {
      "name" : "Molecule Man",
      "age" : 29,
      "secretIdentity" : "Dan Jukes",
      "powers" : [
        "Radiation resistance",
        "Turning tiny",
        "Radiation blast"
      ]
    },
    {
      "name" : "Madame Uppercut",
      "age" : 39,
      "secretIdentity" : "Jane Wilson",
      "powers" : [
        "Million tonne punch",
        "Damage resistance",
        "Superhuman reflexes"
      ]
    },
    {
      "name" : "Eternal Flame",
      "age" : 1000000,
      "secretIdentity" : "Unknown",
      "powers" : [
        "Immortality",
        "Heat Immunity",
        "Inferno",
        "Teleportation",
        "Interdimensional travel"
      ]
    }
  ]
 }
``` 
~~~
super_hero.members
~~~
~~~
super_hero["members"]
~~~
#### members의 첫번째 리스트
~~~
super_hero.members[0]
~~~
#### 3. 직렬화
~~~
JSON.stringify(super_hero);
~~~
#### 4. 역직렬화
~~~
JSON.parse(serialized);
~~~

## API(Application Programming Interface) 
#### * Application : 우리가 사용하는 다양한 서비스들
#### * Programming Interface : 서비스들이 제공해주는 데이터들에 접근하고 사용할 수 있도록 도와주는 도구.
#### -> TV의 리모컨 같은 존재

### < API의 종류 >
#### * SOAP : Simple Object Access Protocol
#### * REST : Representational State Transfer
#### * GraphQL : Graph Query Language

### < RST > 
#### * REST는 하나의 아키텍쳐
#### * 소프트웨어 아키텍처 : 소프트웨어를 설계하는 지침과 원칙
##### 물론 꼭 전부 다 지켜야 하는 법이 아니기 때문에 완전히 Restful한 API는 많지 않다.

### <REST의 구성요소>
#### * 자원
#### : URL에 매치되어 있는 데이터들(리소스)
#### * 행위
#### : GET, PATCH, POST, PUT, DELETE
#### * 표현

