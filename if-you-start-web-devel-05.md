# 개알못인 당신이 웹개발을 시작한다면 (5) - 기초 자료 구조

개발을 알지 못하는 당신이 웹 개발을 시작한다면, 이런 것들을 주축으로 공부하시면 좋을 것 같다는 안내서를 작성하고 있습니다.

1편: 프론트엔드와 백엔드 - https://goo.gl/7GLeQN
2편: 데이터베이스와 네트워크 - https://goo.gl/d16511
3편: 기본 개발 도구 - https://goo.gl/wWgqyw
4편: 기초 자료 구조 - https://goo.gl/ch4paX
5편(끝): 리눅스, 도커, AWS - https://goo.gl/KTd8WP


오늘로 벌써 다섯 번째 글이네요.  이번 편으로 연재를 일단락 지으려 합니다. 기대보다 많은 분들이 호응해 주셔서 부담감이 더 커졌지만, 저로서는 꽤 즐거운 연재였습니다. 역시나 어떤 개인 취향의 선택에 대해서 상세한 의견을 묻는 질문에는 답변을 않고 있는데요, 왜냐하면,  그런 취향의 선택의 문제에 있는 것들로 이런저런 얘기를 하다 보면, 자칫 언어 전쟁(Language War)으로 번지는 경우가 많기 때문입니다. 그저 다른 사람의 취향과 그 나름의 이유가 있으면 그런가 보다 하면 되고, 내 의견이 그 의견과 다르더라도, 굳이 남을 설득할 필요는 없습니다.  커피숍에 갔는데, 친구가 라테를 마신다고 해서, "아, 커피는 아메리카노지, 무슨 라테를 마셔?" 이러고 싸우시는 분 없겠죠? 충분히 성숙한 언어나 도구들은 기능상의 장단점은 어차피 상향 평준화돼 있기에 가르는 것이 큰 의미가 없고, 점점 취향의 영역으로 가게 됩니다. 제 나름 이런저런 경험을 해보고 취향 판단을 섞어 하나의 길을 제시하는 것이지, 최고의 길을 안내해 드리는 것은 아니오니, 잘 참고하셔서 너그러이 이해해주시면 감사하겠습니다.

이번 편에는 이제껏 설명드린 주제들로 잘 만든 웹 서비스를 실제로 다른 사람들이 접근할 수 있도록 운용하는 환경에 대해 살펴볼게요. 특히 버거운 내용이라 아주 가벼이 키워드만 꼽고 넘어가겠습니다.

## 리눅스 (Linux)

웹 개발을 모르시더라도, 리눅스(Linux)라는 운영체제는 다 들어보셨을 거예요. 운영체제는, 우리가 쓰는 컴퓨터에 바탕이 되는 시스템으로, 이 운영체제 위에서 우리가 쓰는 응용 프로그램들이 구동되지요. 스마트 폰을 쓰더라도 안드로이드나 iOS 같은 운영체제가 있고, 그 위에 각종 앱을 깔아서 쓰는 것과 마찬가지로, 우리가 만드는 웹 애플리케이션도 서버의 운영체제 위에서 실행됩니다. 그러면 애플리케이션을 만드는 입장에서는 푸시 알림을 받는 설정이나 화면 밝기 조정 같은 일반적인 일들에 대해서는 신경 쓰지 않고 애플리케이션 본연의 기능에만 집중할 수 있습니다. 나머지 보통의 일들은 운영체제가 다 해주는 거지요.

웹 서비스는 어딘가 데이터센터에 있는 물리적 서버에 서버용 운영체제를 돌리면서, 그 위에 실행해서 운용합니다. 서버용 운영 체제로, 상용 고가 유닉스 시스템을 선호하는 곳도 있지만, 언젠가부터 리눅스가 많이 쓰이지요. 이제는 심지어, 금융권인 카카오 뱅크에서도 x86에 리눅스를 쓰는 게 화제가 되고 있으니, 사실상 다 써도 된다고 보셔도 될 것 같습니다. 저도 거의 리눅스만 쓰는 업계 출신이라서 그런지 "리눅스 쓰는 게 뭐가 어때서?"라는 생각인데, 금융권 분들은 파격이라고 여기나 봅니다.

아무튼, 서버 운영체제로 리눅스를 쓰면 되는데, 이 리눅스에는 배포판이라는 게 여러 종류 있습니다. 다 리눅스인데, 단체별로 어떻게 소프트웨어 패키지를 묶어서 배포하느냐가 다르고 아주 조끔씩 다르기도 합니다. Ubuntu, Debian, CentOS 등이 많이 쓰이고, 요새는 잠시 후 설명할 도커(Docker) 환경 덕분에 아주 가벼운 Alpine Linux를 많이 쓰고 있습니다.

개인 랩탑에 리눅스를 깔아서 데스크탑 운영체제로 쓸 수도 있습니다만, 워낙 번거로운 작업들이 수반되기 때문에 그다지 권하고 싶지는 않습니다. 그냥 평소 본인에게 익숙한 윈도나 맥에서 버추얼 박스(Virtual Box) 같은 가상 머신을 설치해서 써보는 것을 권해드립니다. 컴퓨터를 쓰면서 대부분의 작업은 내가 익숙한 환경에서 하고, 서버 작업만을 위해서 버추얼 박스에 설치한 리눅스로 연습하고 테스트하는 정도가 좋다고 생각합니다.

선택한 리눅스 환경에 웹서버 띄우고, 내가 사용하는 파이썬이나 루비로 웹서비스를 실행해서 외부 네트워크 열어주고 80 포트나 443 포트 열어서 웹서비스를 제공하면 되는 거죠.

* Do: 리눅스 기초 서적 1권을 읽으며, 내 랩탑에 버추얼 박스로 우분투를 설치해서 연습합니다.
* Don't: 리눅스를 내 랩탑 기본 OS로 설치해서 쓸 필요는 없어요.

## 도커 (Docker)

리눅스를 또 한 단계 가상화로 나누어 아주 작은 단위로 격리된 환경에서 쓸 수 있게 해주는 도커가 있는데, 과장 조금 보태면 혁명이라고 봐도 됩니다. 기존에는 리눅스를 쓰더라도 도커보다는 더 큰 단위로 묶어서 하나의 큰 틀을 준비해서 운영했는데, 도커는 리눅스 시스템 안에서 또 리눅스 여럿으로 환경을 격리해서 더 작고 가볍고 효율적인 운용을 가능하게 해줍니다.

[도커이미지]

리눅스를 설치해서 웹서비스를 돌릴 환경을 갖추고 정기적으로 관리하는 일도, 말로 하는 것보다 훨씬 어려운 경우가 있습니다. 내가 원하는 애플리케이션이 필요로 하는 라이브러리가 빠져 있어서 추가로 설치해야 할 때도 있고, 사소하게는 버전이 안 맞아서 문제가 될 때도 있습니다. 내 로컬에 있는 리눅스에서는 잘됐는데, 정작 운영해야 할 서버에서는 뭔가 문제가 있어서 잘 실행되지 않아서, 그 문제를 해결하는 데에 많은 시간을 낭비하게 되기도 합니다.

도커는, 그 리눅스 안에 다른 가상 리눅스 환경을 여럿 만들고, 그 환경마다 각양각색의 원하는 설정을 미리 준비해서 쉽게 곧바로 실행할 수 있습니다. 필요한 오픈소스 애플리케이션이 있다면, 누군가 잘 만들어 놓은 컨테이너 이미지를 받아다가 내가 원하는 입맛으로 살짝 바꿔 실행할 수도 있고, 그대로 써도 되는 경우도 많습니다.

무엇보다 이 컨테이너를, 내 로컬 환경과 서버가 운영되는 실제 서비스 환경에서 차이 없이 그대로 쓸 수 있다는 점도 참 매력적입니다. 도커는 워낙 파격적이라 제가 설명드리는 내용이 전부이기는 어렵고요, 앞으로는, 아니 그리고 어쩌면 이미 도커로 판이 바뀌었다고 보셔도 되지 않을까 싶습니다.

어쩌면 어떤 분들은 서버용 운영체제로 리눅스가 아니라 윈도 서버를 쓰려하실 수도 있으나, 이 도커의 존재만으로도 리눅스를 써야 할 만한 충분한 이유가 되지 않을까 합니다.

* Do: 도커 기초 서적 1권을 골라 차근히 읽습니다. 당장 이해가 되지 않더라도, 일단 끝까지 읽습니다.

## AWS (아마존 웹 서비스, Amazon Web Services)

예전에는, 그리고 지금도 큰 기업들은, IDC라고 인터넷 데이터 센터에 입주해서 전용 공간에서 서버를 가져다 놓고 운영합니다. 그러려면 우선 데이터 센터에 서버가 들어갈 물리적 공간과 네트워크와 전력과 항온항습 등을 위한 계약을 하고, 적절한 장비를 사서 넣어서 운영하며 관리합니다.

하지만, 이제 클라우드 환경으로 가면서, 그럴 필요가 없어졌지요. 아마존 웹 서비스 같은 플랫폼에 가입해서, 원하는 사양의 가상 머신을 원하는 순간에 필요한 시간만큼 운영할 수 있습니다. 초기에 큰 액수의 계약을 한다거나, 내게 필요한 사양의 서버를 사서 갖다 넣는다거나 하는 일은 오래전 일이 돼버렸습니다.

이미 준비된 서버들을 필요에 따라 임대해서 쓰고, 더 이상 필요 없으면 반납하면 됩니다. 내 서버를 내 자가용이라고 비유한다면, 그 이후 있었던 서버 임대 서비스가 렌터카 서비스이고, 클라우드 환경은 쏘카 같은 시스템이라고 보면 되려나요? 그보다 더 편리한 격차가 크기는 한데, 개념적으로는 크게 다르지 않을 것 같습니다. 아무튼, 지금은 서버를 산다거나 데이터센터나 호스팅 업체에 계약을 할 필요는 없고, AWS 같은 클라우드 서비스를 필요에 맞게 쓰면 됩니다.

경쟁 서비스로는 구글 클라우드 플랫폼이나 마이크로 소프트 애저가 있습니다만, AWS가 워낙에 넘사벽으로 앞서 있어서 어떨지 모르겠네요. 나중에야 상향 평준화되겠지만, 지금은 그냥 고민 없이 AWS를 쓰면 됩니다.

이 연재에서 목표로 하는 동네 웹서비스 목적으로 아주 작은 장비를 할당받아서 24시간 운영한다면, 아마도 한 달에 1~2만원으로도 충분하지 않을까 합니다. 다른 호스팅 업체를 이용하면 훨씬 저렴하게 운용할 수 있다고 말하는 사람들이 있을 텐데요, 고맙다 말하고 무시합니다. 커피 한 두잔 값 차이에, 불필요한 시간을 낭비하지 않아도 되니, 우리의 가장 소중한 자원인 "시간과 노력"을 줄일 수 있다면, 충분히 지불할 만한 가격 차이입니다.

게다가, AWS의 RDS처럼 데이터베이스를 편리하게 운영해주고 백업과 복구도 대신해주는 시스템이 있어서 편리함을 넘어서서 무섭기까지 합니다. 이 정도라면 DBA 같은 직종이 덜 각광 받을 것 같고, 좀 더 지나면 저 같은 서버 개발자도 필요 없어질 것 같습니다.

다만, AWS는 워낙 방대한 서비스이기에 조금 시간을 들여 공부해야 할 필요가 있습니다. 우선 기초 서적 한 두권 골라서 여유롭게 차근히 보시고 접근하시면 좋지 않을까 합니다. 일단은 EC2, RDS, S3정도만 파악해서 쓰셔도 충분할 거예요.

* Do: AWS 기초 서적을 1권 다 읽으며 가볍게 실험해 봅니다.
* Don't: 직접 서버를 운영한다거나 호스팅 업체에 입주하는 일은 하지 않습니다.

## 연재 마무리

이상, 2017년에 새로 웹 개발을 시작하는 분들을 위한 하나의 이정표를 작성해 보았습니다. 시작부터 언급드렸듯이, 이게 하나의 완전한 가이드일 수는 없고요, 다만, 지나치게 흔들리거나 방황하지 말고, 시작점부터 끝점까지 하나 이어보자는 목표로 적어보았습니다. 하나하나의 주제를 학습하는 데에도 적지 않은 시간이 걸리겠지만, 다 걷고 난다면, 사실 동네 웹서비스뿐 아니라 제대로 된 개발자로 일하는 데에도 충분하지 않을까요?

이상 다섯 편의 긴 글 다 읽어주신 분들 감사드립니다. 아마 당분간은 다른 주제로 글을 쓰겠지만, 언젠가 이 연재의 시즌2를 다시 시작할지도 모르겠네요. 그럼 즐거운 웹 개발 시작하시길 바라겠습니다!
