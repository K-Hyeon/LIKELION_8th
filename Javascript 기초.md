## Javascript 기초 문법
### < 주의사항 및 자습 안내>
#### * [W3C School](https://www.w3schools.com/)
#### * [MDN Document](https://developer.mozilla.org/ko/docs/Web/javaScript)
#### * [생활코딩 WEB2 - Jacascript](https://opentutorials.org/course/3085)
#### * [ofcourse](https://ofcourse.kr/)


### < Jacascript >
#### * 웹페이지를 동적으로 만들 때 사용하는 언어
#### * 객체 기반의 스크립트 언어
#### * 할 수 있는 일이 괸장히 많다.
#### ** Browser API - DOM, 위치정보, audio, 화면공유 등 Browser에서 제공하는 API들
#### ** 2D, 3D 그래픽 작업 - NullSchool
#### ** 클라이언트 뿐만 아니라 서버도 JS로 가능 - Node.js
#### * 스크립트 언어 + 인터프리터 방식 (파이썬과 동일)
#####  입력 후 바로 결과 확인이 가능하다.
##### 브라우저에 내장된 엔진으로 즉시 해석된다.
#### * 사용법1 : HTML 내부에서 <script>태그내에 사용
#### * 사용법2 : .js 파일로 만들고, <script src="파일경로">를 사용해서 불러오기
#### * Javascript 사용법
#### 1. html:5로 문서를 생성



### < 변수 >
#### * 사용가능한 데이터 타입 : Boolean, Null, Undefined, Number, String, Symbol, Object
#### * var : 권장하지 않는 변수 선언 방식
#### - Hoisting
#### - Function scope 변수(타 언어와 다른 점)
#### - 중복 선언 가능
#### - 예측하기 어려운 코드를 만들 수 있다.
#### * let : block scope 변수(타 언어와 비슷하게 동작)
#### * const : 변하지 않는 데이터를 저장(ex. 파이, 객체)
#### * 실습
#### 1. Chrome -> F12 -> Console
~~~
let booleanVal = true
let numberVal = 0
let nullVal = null
let undefinedVal = undefined
let stringVal = ''
let person = {
  name : "홍길동",
  phoneNumber : "010-0000-0000",
  email : "hong@hong.com"
  }
  ~~~
  ~~~
  booleanVal
-> true
typeof(booleanVal)
-> "boolean"
typeod(numberVal)
-> "number"
typeof(nullVal)
-> "object"
typeof(undefined)
-> "undefined"
null * 2
-> 0
undefined * 2
-> NaN(Not a Number)
typeof(stringVal)
-> "string"
typeof(person)
-> "object"
~~~


### < 반복문 >
#### for 문
~~~
for (let i = 0; i < 10; i++) {
  console.log(i)
}
~~~
#### for of 문
~~~
const oddNums = [1, 3, 5, 7, 9, 11];
for(const i of oddNums){
  console.log(i);
}
~~~
#### while 문
~~~
let i = 0;
while (i < 10) {
  console.log(i);
  i++;
}
~~~


### < 조건문 >
#### promt를 사용한 Input
~~~
let score = prompt("점수를 입력하세요. 1", 0);
~~~
score
~~~
~~~
if(score >= 90) {
    console.log("A+");
} else if (score >= 80){
    colsole.log("B+");
} else {
  console.log("C+");
}
~~~
~~~ 
score = prompt("점수를 입력하세요. 2", 0);
if (score >= 90) {
    console.log("A+");
} else {
    // 아래와 같이 실행할 문장이 한 문장이라면
    // 중괄호를 생략해도 된다
    if (score >= 80)
      colsole.log("B+");
   else 
      console.log("C+");
}
~~~


### < DOM 다루기 >
#### * DOM : Document Object Model
#### * 웹페이지에 접근할 수 있게 해주는 일종의 인터페이스
#### * Javascript와 별개
#### * Javascript에 DOM을 조작할 수 있는 API가 존재
#### * DOM 다루기 - Node 선택하기
~~~
let idObj = document.getElementById("main");
let classObj = document.getElementsByClassName("sfbgx");
let selectorObj = document.querySelector("#main");
~~~
~~~
let selectorObj = document.querySelector("#.sfbgx");
~~~
#### * DOM 다루기 - 속성 변경하기
##### 1. 원하는 부분을 copy, 붙여넣기 하면 해당 경로가 나옴
~~~ 
let twoDoHee = document.querySelector("<경로 붙여넣기>")
twoDoHee.style = "color:yellow; background-color:black;"
twoDoHee.innerText = "허태정"
~~~
~~~
selectorObj.style = "color:yellow";
selectorObj.innerText = "허태정";
selectorObj.innerHTML = '<a href="https://www.naver.com>네이버</a>';
aTag.href = "https://www.naver.com";
~~~ 
#### 새로운 노드 추가하기
~~~
let newNode = document.createElement("p");
newNode.innerText = "new P tag";
let link = document.querySelector("원하는 위치 복사 붙여넣기")
link.appendChild(newNode);
~~~

### < 함수 >
#### 기본적인 형태
~~~
funtion ver1_appendNewNode(target, tag="p", text="기본값") 
{
  let newTag = document.createElement(tag);
  newTag.innerText = text;

  target.appendChild(newTag);
}
~~~
##### 여러번 반복하면 계속 추가됨.
~~~
let targetNode = document.querySelector("복사 붙ㅇ녀넣기")
ver1_appendNewNode(targetNode)
ver1_appendNewNode(targetNode, "a");
ver1_appendNewNode(targetNode, "a", "나는 기본값이 아니야");
~~~
#### 익명함수
~~~ 
let ver2_appendNewNode = function(target, tag="p", text="기본값")
    let newTag = dopcument.createElement(tag);
    newTag.innerText = text;
    
    target.appendChild(newTag);
}
~~~
~~~
ver2_appendNewNode(targetNode)
~~~
#### 화살표 함수
~~~
let ver3_appendNewNode = (target, tag="p", text="기본값") => {
    let newTag = dopcument.createElement(tag);
    newTag.innerText = text;
    
    target.appendChild(newTag);
}
~~~
~~~
ver3_appendNewNode(targetNode)
~~~
    
