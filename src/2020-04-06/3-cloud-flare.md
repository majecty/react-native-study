# CloudFlare로 서버 만들기

## 서버와 IP 주소

서버로 사용되는 모든 컴퓨터는 숫자 4개로 된 공개된 IP 주소를 할당 받는다.

프로그래밍을 하지 않으면 IP 주소에 익숙하지 않겠지만 가끔 IP 주소를 보여주는 서비스들이 있다.
서버로 사용하지 않는 컴퓨터나 핸드폰도 인터넷을 사용할 때 IP 주소가 할당되는데, 이 IP가 지역별로 나뉘어져있고, 잘 바뀌지 않기 때문에 유저를 구분하는 용도로 보여주는 것이다.
집에서 공유기를 사용하면 공유기에 공개된 IP주소가 할당되고, 공유기에 연결된 컴퓨터들은 인터넷에 정보를 요청할 때 공유기의 공개 IP를 함께 사용한다.

## 서버 OS 빌리기 VS 서버 서비스 사용하기

개인이 항상 켜져있는 서버를 관리하기 힘들기 때문에 보통 컴퓨터를 관리해주는 곳의 서비스를 사용한다.
남의 컴퓨터를 관리해주거나 자신이 가진 컴퓨터를 대여해주는 곳을 IDC (Internet Data Center)라고 한다.
요즘은 컴퓨터를 직접 대여하는 게 아니라 컴퓨터 안에 가상의 컴퓨터를 만들어서 대여해주는 서비스들이 많아졌다. 아마존의 AWS, 구글의 GCloud, MS의 Azure, 네이버의 Naver cloud platform 들이 있다. 노트북 성능의 1/10정도의 성능의 서버를 빌리는데 한달에 만 원 정도 한다.

서버 컴퓨터를 빌리면 거의 모든 것을 할 수 있는 자유가 있지만, 간단한 서버 프로그램을 만든다면 더 적합한 서비스들이 있다.
그 중 하나가 Cloudflare의 Workers다.
자바스크립트로 간단한 프로그램을 작성하면 Cloud flare의 서버 컴퓨터에서 동작시켜주는 서비스다.

Cloudflare의 Workers는 JavaScript 코드를 쓸 수 있고, 하루에 100,000개의 요청까지는 무료로 쓸 수 있기 때문에 연습용으로 쉽게 사용할 수 있다.

    
## Cloud flare Workers

이 링크 https://workers.cloudflare.com/ 에 들어가자.

로그인하면 [대시보드](https://dash.cloudflare.com)창이 뜰 것이다. 여기서 Workers로 들어가서 "Create a Worker" 버튼을 누르자.

## Hello world

맨 처음 워커를 만드면 다음과 같은 스크립트가 써져있을 것이다.

```js
addEventListener('fetch', event => {
  event.respondWith(handleRequest(event.request))
})

/**
 * Respond to the request
 * @param {Request} request
 */
async function handleRequest(request) {
  return new Response('hello world', {status: 200})
}
```

이 페이지를 저장한 뒤 배포해보자. 웹브라우저로 해당 페이지에 들어가면 hello world를 볼 수 있다.
