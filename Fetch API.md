## Fetch API
### < 비동기 처리 >
#### * 들어온 요청들을 순차적으로 실행시킨다면?
#### ** 앞에 들어온 작업이 시간이 오래 걸리는 작업일 시 뒤에 있는 작업들이 밀리게 된다.
#### * 이런 작업들을 그대로 실행시키면서 뒤에 있는 코드들을 실행시키는 것이 바로 비동기처리이다.
#### * Promise 객체를 사용한다.
#### ** 대기
#### ** 이행 
#### ** 거부
#### * 두 가지 패턴이 존재한다.
#### * async, await 키워드를 활용한
~~~
async function asyncFunction(){
        await[Promise 객체]
}
~~~
#### * [Promise 객체]
#### : .then(콜백함수), .catch(콜백함수)


### < Fetch API >
#### * Fetch API는 네트워크 통신을 위해서 제공되는 API이다.
#### * Promise 객체를 반환한다.
#### * Request, Response라는 두 개의 객체를 사용한다.


### < 실습 >
~~~
// Promise의 세 가지 상태
// 1. Pending (대기)
// 2. Resolved (이행)
// 3. Rejected (거부)

function promiseTest1(timer) {
    // Promise 객체를 new 키워드를 통해 만들어줍니다.
    let promiseObj = new Promise((resolve, reject) => {
        setTimeout(() => {
            // resolve 함수를 통해 메시지를 반환해줍니다.
            resolve(`Timer : ${timer}`)
        }, timer);
    });

    // 반환된 메시지는 then 함수를 통해 익명함수의 매개변수
    // 여기서는 value로 들어가게 되고,
    // console.log(value)로 출력됩니다.
    promiseObj.then((value) => console.log(value));

}

funtion promiseTest2(timer) {
    // status를 랜덤으로 만듭니다.
    // Math.floor() : 바닥함수 -> 소수점이하를 버립니다.
    // Math.random() : 0~1 사이의 랜덤한 숫자를 반환합니다.
    const status = Math.floor(Math.random() * 10) % 2;
    let promiseObj = new Promise((resolve, reject) => {
        // 랜덤으로 뽑은 status가 1이면 resolve
        // status가 0이면 reject로 메시지를 반환합니다.
        setTimeout(() => {
            if (status === 1) resolve('성공!');
            else reject('실패ㅠ');
        }, timer)
    })
~~~
~~~
// Fetch API로 JSON Plaveholder 테스트
const url = "https://jsonplaceholder.typicode.com/posts";
fetch(url)
  .then(response => response.json())
  .then(json => console.log(json))

// Fetch API로 post 요청 날리기
// 생성할 POST 객체
let newPost = {
      title: 'foo',
      body: 'bar',
      userId: 1
};
    
fetch(url, {
    // HTTP 요청 메소드 사용 가능
    method: 'POST',
    // body는 직렬화해서 전송!!
    body: JSON.stringify(newPost),
    // Header를 추가해서 우리가 보내는 데이터에 대한 정보를 서버에
    headers: {
      "Content-type": "application/json; charset=UTF-8"
    }
})
    .then(response => {
        console.log("response 타입: " + typeof(response));
        return response.json();
    })
    .then(json => {
        console.log("response.json() 타입: " + typeof (json));
        console.log(json))
    })
~~~
