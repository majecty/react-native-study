# Electron fiddle

이전에 JavaScript가 한 때 힙한 언어라고 했었다.
JavaScript는 웹브라우저에서 사용하기 위한 언어로 만들어졌고,
지금도 웹브라우저에서 사용할 수 있는 유일한[^1] 언어다.
자바스크립트의 async한 특징으로 서버에서 사용되기 시작하면서 회사에 필요한 모든 개발을 JavaScript로 할 수 있게 되었다.

[^1]: 다른 언어를 쓰려는 시도는 계속되고 있다.

JavaScript를 사랑하는 사람들은 더 많은 일들을 JavaScript로 하기를 원했고, 결국 윈도우즈나 맥, 리눅스에서 돌아가는 어플리케이션도 JavaScript로 작성하기를 원했다.
결국 웹브라우저를 통째로 실행파일 안에 집어 넣어서 데스크탑 앱을 만들었다.

## Electron

chrome 브라우저와, 서버용 JavaScript 실행하는 도구인 node를 하나로 합쳐 윈도우즈, 맥, 리눅스용 데스크톱 어플리케이션을 쉽게 만드는 도구다. 유명한 개발자 도구인 VS Code, 업무용 메신저로 유명한 slack, 게임용 메신저로 유명한 Discord, 화상통화 어플리케이션인 Skype가 Electron을 사용한다.

## Electron Fiddle

Electron Fiddle은 Electron을 쉽게 테스트하는 환경이다.
쉽게 다른 라이브러리를 사용할 수 있고, 실행파일도 바로 만들 수 있다.
오늘 실습은 Electron Fiddle을 사용한다.