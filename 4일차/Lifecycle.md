# LifeCycle

브라우저의 라이프사이클과 용어들을 정리합니다.

아주 아주 중요함!!! 프론트엔드의 필수 중의 필수! 덕목입니다.

면접자가 이렇게 물어 볼 수도 있습니다.
브라우저로 네이버(https://www.naver.com)에 접속하여 사용자가 화면을 제공받을때 까지 어떤 일이 일어나는지 간단하게 설명해보라고 합니다.

이걸 아느냐 모르느냐가. Coder(코더)와 Developer(개발자)의 차이를 판가름하는 첫 발걸음 입니다.

1. 브라우저 주소창에 `https://naver.com`입력하는데 이는 다음을 의미합니다.
 - `http 프로토콜`로 `ssl`로 내 요청과 응답을 암호화해서 naver.com이라는 `도메인`과 매핑되는 서버(`223.130.195.200`)로 가서 응답을 받아와~
 - 브라우저는 먼저 도메인 `naver.com`를 컴퓨터가 이해할 수 있는 주소인 `IP`로 변환해야 합니다. 내 컴퓨터에도 저장할 수 있지만 세상에 수 많은 도메인을 저장할수는 없는 노릇입니다. 그래서 우리는 한 컴퓨터에 저장(몰빵)해 놓기로 약속했습니다. 그래서 이 컴퓨터에 `도메인`을 전송하면 곧바로 그 컴퓨터에 그 도메인과 매핑되어 있는 `IP` 주소를 응답해줍니다. 그 컴퓨터를 우리는 DNS(Domain Name Server)로 부르기로 했습니다. 따라서 사용자가 입력한 `Domain`을 `DNS`에서 `IP`로 받아옵니다.

2. 받아온 IP로 데이터를 요청합니다. -> 서버가 요청을 받고 응답해줍니다. (추후에 심화과정으로 이 단계에서 CORS에 대해 공부하셔야 합니다.)

3. 데이터가 도착했습니다! 데이터 예시(`<!DOCTYPE html><html><head><meta>..........</meta></head></html>`) -> 로딩...

4. 브라우저의 렌더링 엔진이 위의 `html`을 브라우저가 이해하기 쉬운 `DOM(트리)`으로 변환합니다.

5. 그 과정에서 추가로 불러와야하는 리소스를 불러와야 한다면 불러온 뒤 파싱합니다. (css, javascript, image 등...)

5.2. CSS는 `CSSOM`로 변환합니다.

5. 위의 `DOM`과 `CSSOM`을 가지고 화면에 그려줍니다.