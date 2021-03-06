개발을 알지 못하는 당신이 웹 개발을 시작한다면, 어떤 것들을 차례로 공부하면 되는지 알려드린다는 주제로 연재 글을 적고 있습니다. 분야를 나눠서 첫째 글은 프론트엔드와 백엔드에서 공부할 만한 주제를 적었고, 두 번째 글은 데이터베이스와 네트워크에 대한 얘기, 세 번째는 기본적인 개발 도구들에 대해 간략히 살펴보았지요. 이번 글은, 웹 개발뿐만 아니라 모든 개발 분야에 다 쓰이는 자료 구조에 대해 설명드리려 해요. 프론트엔드 개발을 하든, 백엔드 개발을 하든, 아이폰 앱 개발을 하든, 안드로이드 앱 개발을 하든 어디에나 유용한 주제이지요.

1편: 프론트엔드와 백엔드 - https://goo.gl/7GLeQN
2편: 데이터베이스와 네트워크 - https://goo.gl/d16511
3편: 기본 개발 도구 - https://goo.gl/wWgqyw

틈틈이 네 번째 글을 쓰는 중, 이 연재 글이 꽤 많은 분들께 공유되어 조회수가 꽤 올라갔네요. 몇몇 지인들께만 보이려는 의도였는데, 이렇게 되니 사뭇 부담도 되고 한편으로는 기대도 됩니다. 원래는 제 평소 알고 있는 내용들을 머릿속에서 끄집어내어 가볍게 적어 낼 생각이었는데, 생각보다 머릿속에 있는 내용이 부실하더군요. 그래서 조금씩 자료를 찾아보며 저도 공부하며 남기고 있습니다. 공유의 의미가 그런 거죠. 나도 정리하는 과정에서 배우고, 보는 분들도 정리한 내용에서 배우고, 그리고 더 나아가 피드백으로부터 서로 배우고 말이죠. 이 연재가 마음에 드신다면, 주변에 공유도 해주시고, 댓글로 의견도 달아주시고 하면 서로 참 좋을 것 같습니다. 혹시 지적해주실 내용이나 질문이 있으시다면, 댓글로 남겨주셔도 좋을 것 같아요. 그러면 설명이 부족한 부분에 대해 부가 설명을 할 수도 있을 테고요.

그럼, 오늘은 연재 4편으로, 자료 구조에 대해 말씀드려 보겠습니다.

## 자료 구조 (data structures)

자료 구조는 자료를 효과적으로 잘 쓸 수 있도록 잘 정리하는 방법을 부르는 말입니다. 자료가 많지 않을 때야 아무렇게나 보관해도 찾을 수 있겠지만, 분량이 많아지면 나름의 정리 방법이 필요한 상황을 생각해보면 될 것 같아요. 자료를 장 정리해 둔다는 면에서 2편에 말씀드린 "데이터베이스"와 비슷한 영역이라고 볼 수도 있는데, 꼭 그런 건 아니지만, 보통 데이터베이스는 디스크에 저장하는 반영구적(persistent) 데이터를 다루고, 자료구조는 주로 프로그램이 실행되는 동안 메모리에 있는 데이터를 다룬다고 생각하면 이해가 쉬울 것 같습니다. 실상은, 데이터베이스도 내부적으로 갖가지 자료 구조를 활용하고, 디스크에 저장하는 목적의 자료 구조도 많으니 자료 구조가 더 포괄적인 개념이겠지만요.

아무튼, 자료 구조는 데이터를 잘 정리하는 나름의 방법을 말합니다. 예를 들어, 내 방 책장에 책을 꽂을 때야 아무렇게나 대충 꽂아 놓아도, 필요할 때 원하는 책을 찾아서 볼 수 있겠지만, 도서관이나 서점에서는 상황이 달라지잖아요? 크게는 도서 분류별로 구분된 영역에 위치하고 있을 테고, 같은 소분류 내에서도 도서명의 가나다 순으로 정렬되어 있겠지요. 그것만으로도 충분하지 않으니, 곳곳에 도서 검색용 PC가 있어서 원하는 책의 제목이나 저자 이름이나, ISBN 기준 등으로 다양하게 검색하는 방법이 준비돼 있지요.

우리가 작성하는 프로그램으로 다루는 데이터를 잘 보관하는 방법도 그렇습니다. 단순이 아무렇게나 늘어놔 놓고, 필요할 때 일일이 찾아보는 방법도 있고, 아니면 어떤 분류법을 써서 자주 사용하는 패턴에 맞게 효과적으로 찾을 수 있는 형태로 잘 보관하기도 합니다. 어떤 자료 구조로 저장하느냐에 따라 어떤 활용에는 효율적이고, 다른 활용에는 비효율적일 수도 있습니다. 전문 용어로 계산 복잡도(computational complexity)가 다르다고 말합니다. 예를 들어, 명함을 가나다 순으로 정리해 두었다면, 특정 성명으로 전화번호를 찾기에는 좋지만, 어떤 모르는 발신 번호가 떴을 때 그 번호가 누구의 것인지를 찾는 데 쓰기는 어려운 것처럼요.

자료 구조는 데이터를 잘 정돈하고, 또 효과적으로 운용하는 방법과 관련이 커서 흔히 알고리즘과 뗄 수 없는 단어이기도 합니다. 우선은 기본 자료 구조와 그걸 다룰 때의 특성 정도만 알고 있으면 좋겠습니다. 기초 자료 구조는 보통의 프로그래밍 언어에 기본으로 포함돼 있고, 그걸 다루는 알고리즘을 잘 구현해낸 코드도 함께 준비돼 있어서, 우리가 직접 자료 구조를 구현하거나 알고리즘을 코드로 표현할 일은 별로 없습니다. 설령 기초 수준을 넘어서는 고급 자료 구조가 필요하더라도, 누군가 남이 잘 만들어 놓은 것을 가져다 쓰면 됩니다. 하지만, 그 특성과 상황별 효율은 알고 있어야 상황에 맞게 적절한 자료 구조를 골라서 쓸 수 있습니다. 또, 공부하다가 관심이 생긴다면 깊게 파고들어서 직접 만들어 보는 것도 좋은 공부가 되는 것 같습니다. 만약 관심이 있다면 말이죠.

사실 우리가 만들려는 2층 목조 주택 같은 아담한 나만의 웹 서비스를 만드는 경우에는 별다른 자료 구조를 의식하지 않고도 대부분의 일을 처리할 수 있을 텐데요, 그럼에도 이 연재에 한 꼭지 틀고 앉히는 이유를 굳이 꼽아본다면, 우선, 대강이라도 알아두면 어디 가서 개발할 때 쫄리지 않습니다. 혹시나 개발을 본격적으로 시작하신다면 반드시 알아야 할 주제이기도 하고요. 그리고, 은근 어려워 보이지만, 꽤나 재밌는 분야이기도 합니다. 무엇보다, 모든 프로그래밍 언어마다 기본적인 자료 구조를 다루는 내용들이 들어있고 그걸 기반으로 코딩하게 되는데, 그게 당최 뭔 소리인지 알 수 있게 해주기도 하기 때문입니다.

프로그래밍 언어마다, 그 언어 기본으로 제공하는 자료 구조는 조금씩 다르지만, 대개는 아래 나열한 정도가 기본입니다.

* 배열(array) - 데이터들을 차례로 인덱스를 부여하며 순차적으로 나열
* 리스트(list) - 데이터들을 서로 줄기로 엮어서 다음 데이터들을 연결
* 해쉬(Hash, Dictionary) - 데이터의 기준값을 나름의 방법으로 분류해 정리
* 트리(tree) - 데이터들을 몇 단계로 분류를 거치며 계층적으로 정돈.

## 배열(Array)과 리스트(List)

배열과 리스트는 비슷한 데이터들을 나름의 순서로 나열해 놓는다는 점에서 비슷합니다. 정해진 순서로 늘어놓아도 되고, 꼭 순서가 없어도 무방합니다. 그저 차례로 줄지어 늘어놓은 구조일 뿐입니다. 체육 시간에 운동장에서 뛰노는 학생들을 선생님이 불러서 그냥 아무렇게나 한 줄로 서라고 해서 줄지어 세울 수도 있고, 때에 따라서는 키순으로 서라고 할 때도 있는 것처럼요. 키 순으로 서라고 하면, 제일 작은 학생을 찾기도 편하고, 제일 큰 학생도 찾기 편하고, 중간 키인 학생을 찾기도 편하지요.

배열은 인덱스라고 부르는 숫자를 기준으로 접근하기 쉬운 구조로 되어있습니다. 학교 다닐 때 수학 시간에 배우는 수열과 비슷합니다. 수열을 이루는 구성원을 수열의 항이나 원소라고 하는데, 그 구성원 하나하나를 몇 번째 원소인지 지칭하기 좋잖아요? 그 수열의 길이(length)라는 것도 있고요. 무한수열을 표현할 수도 있습니다만, 보통의 경우 유한 수열로 씁니다. 배열에 정해진 길이 `n`이 있고, 그 안에 여러 원소(데이터)들을 보관하지요.

예를 들어, `10 이하 양의 짝수`를 표현하는 수열 e가 있다면,

    e[i] = (2, 4, 6, 8, 10)

이때, 첫 번째 원소는 `2`이고 마지막 원소는 `10`이며, 이 배열의 길이(length)는 5입니다. 이걸 프로그램으로 표현한다면, 다섯 개 요소를 보관할 수 있는 정수 배열을 만들고 차례로 짝수들을 보관해 두었다가, 필요할 때 쓸 수 있지요.

수열로 예를 들었지만, 배열 안에 들어가는 것이 반드시 숫자일 필요는 없고요, 우리가 원하는 아무 데이터나 넣으면 됩니다. 필요에 따라 차례로 접근해서 어떤 작업을 하기도 하고, 아니면 임의의 위치를 인덱스로 콕 집어서 찾아 쓰기도 합니다. 배열의 인덱스와 수열의 몇째 항인가 하는 표현이 거의 같은데, 다만 보통 프로그래밍 언어에서는 첨자가 0에서 시작합니다. 첫째 항이 0번 항이고, 둘째 항의 인덱스는 1입니다. 단지 시작 값이 다른 것뿐이에요.

    e[0] = 2, e[1] = 4, ... e[4] = 10

한편 (연결) 리스트는 배열과 비슷합니다만, 자료를 보관하는 내부 구조에 인덱스가 있는 것이 아니라, 단지 임의의 순서만 있습니다. 각 값에 그 다음 값이 무언지 연결하는 고리(링크, link)가 있어요. 그래서 리스트의 첫 번째 요소로부터, 그다음 요소를 차례로 따라가면서 원하는 일을 할 수 있어요. 리스트의 첫번째 요소만 잘 갖고 있으면서, 필요할 때 거기서부터 찾아들어갑니다.

리스트도 모든 요소를 차례로 접근하는 것은 똑같이 할 수 있지만, 임의의 몇 번째 요소를 콕 집어서 찾아오는 데에는 배열에 비해 불리합니다. 대신, 리스트는 그 길이를 미리 정할 필요가 없이, 계속 크기를 늘리기 좋습니다. 그리고 중간에 어떤 요소를 끼워넣기도 편리합니다. 반면 배열의 경우 그 배열 중간에 어떤 값을 끼워 넣으려면, 그 뒤 요소들을 다 밀어내야 하는 불편함이 있습니다. 그래서 똑같이 차례로 늘어놓는 비슷한 데이터에 대해서도 어떨 때는 배열이 편리하고, 어떨 때는 리스트가 유리합니다. 효율의 차 이이지, 둘 다 할 수 있다는 점에서는 차이가 없어요. 예를 들어, 리스트라고 해서 몇 번째 요소가 뭔지 찾을 수 없다는 뜻이 아닙니다. 필요할 때, 처음부터 차례로 이동해가면서 몇번 째 요소를 찾아내면 됩니다. 그 길이도 끝까지 한번 가보면 알 수 있지요. 배열도, 배열의 길이를 늘리려면, 더 큰 크기의 배열을 만들어서, 원래 배열의 내용을 복사하면 됩니다.

보통, 원소들의 개수를 미리 알 수 없는 경우에는 리스트를 쓰고, 원소들의 개수가 정해져 있거나 임의의 위치를 콕 집어서 접근할 일이 많을 때는 배열을 씁니다. 또, 언어에 따라서 기본 문법에 배열이 편리한 경우가 많아서, 대부분의 경우 배열을 우선시하기도 합니다.

## 해시(Hash, aka. Dictionary)

해시는, 데이터의 순서는 상관없이 어떤 특정 데이터를 빠르게 찾기 좋은 자료 구조입니다. 아마 우리 두뇌 속에 사람 얼굴을 판단하는 구조가 해시와 비슷하지 않을까 합니다. 어떤 사람의 인상착의를 보면, '아 저게 누구다'라는 머릿속 데이터를 뿅 하고 순간적으로 아는 상황과 비슷합니다. 인상착의라는 해시 함수가 있는 거고, 거기에 엮인 그 사람에 대한 정보들이 줄기로 엮여 나오지요. 만약 우리 머릿속에 있는 사람에 얼굴에 대한 데이터가 리스트나 배열로 되어있다면, 길을 가다 아는 사람을 만났을 때조차, 매번 일일이 그 인상착의 데이터를 순차적으로 뒤져봐야 한다면 너무 오래 걸려서, 결국 그 사람이 누구였는지는, 그 사람과 헤어지고 나서야 알까 말까 할 정도로 느리겠지요.

해시 구조를 쓰면 인상착의로부터 순간적으로 빨리 원하는 데이터를 찾기는 아주 유용하지만, 대신 이게 순서를 기준으로 찾기는 어렵습니다. 예를 들어, A라는 사람과 아주 비슷하게 생겼는데, 그보다는 조금 눈이 큰 사람이 누구인가? 이런 건 따로 찾을 수 없지요. 그저, 누군가의 얼굴을 딱 봤을 때, "아 내가 아는 사람이다 or 아니다", "아는 사람인데 그 인간이 어떤 인간이다" 이런 데이터를 찾기(lookup) 좋은 구조입니다. 우리가 알고 있는 얼굴을 모두 찾아내는 것도 어렵습니다. `내가 인상착의를 알고 있는 사람이 총 몇 명인가?`  이런 정보 쉽게 생각해 내시는 분 있으면 제보 바랍니다.

해시에는 그 데이터를 대표하는 키 값이라는 것이 있고, 그 키 값으로부터 특정 인덱스를 뽑는 해시 함수(Hash Function)가 있습니다. 키 값에 따라 골고루 이 인덱스를 흩어 놓아서 데이터 공간을 효과적으로 사용할 수 있는 함수가 해시함수에 유용합니다. 조금 전 예를 든 상황에는 인상착의라는 것이 그 사람에 관련한 데이터의 키값인 거고, 그 얼굴로부터 모종의 특징을 추려서 머리속에 보관하는 해시 함수가 우리 본능에 프로그래밍되어 있는 거지요.

가장 이해하기 쉬운 해시 함수는 아마도 영어사전을 찾을 때 쓰는, 알파벳 첫 글자가 아닐까 합니다. `programming`이라는 단어를 찾고자 한다면, `p`섹션으로 가서 알파벳 순으로 찾아보잖아요? 이 경우 `p`를 추출하는 함수가 해시 함수인 셈입니다. `p`섹션으로 빠르게 이동해서, 거기서 데이터를 찾아보고 있으면 그걸 돌려주면 되고, 없으면 사전에 없는 데이터인 겁니다. 이렇듯 역할이나 활용이 사전과 비슷해서 Dictionary라고도 부르나 봅니다. 사전의 경우, 정확하게 말하자면, 알파벳 순으로 정렬된 리스트/배열의 구조 위에 알파벳 첫 글자를 따는 해시로 인덱스를 부여해서 더 빠르게 찾을 수 있는 구조입니다. 이렇게, 몇몇 자료구조를 병용해서 원하는 활용에 조합해 쓰기도 합니다.

## 트리(Tree)

트리는 계층적인 구조를 다룰 때 쓰기 좋은 자료 구조입니다. 나무의 뿌리(root)로 시작해서 여러 가지가 갈라지며 마지막에 나뭇잎(leaf)이 달려있는 모양새를 연상해서 트리라고 이름 지었나 봅니다. 보통의 나무들이 가지가 갈라졌다가 다시 만나는 경우는 없을 텐데요, 트리 구조도 그렇습니다. 보통 그림으로 표현할 때는 거꾸로 루트(root) 노드를 제일 위에 그리고, 아래로 차례로 이어 그립니다. 그리는 표현으로 보자면, 회사나 단체의 조직도와 더 유사합니다. 조직도 제일 위에 회사 사장이 있고, 그 아래에 부문별 이사들이 있고, 이사들 아래에 부장들이 있는 식으로요. 다만 회사에는 겸직이라는 희한한 직책이 있지만, 트리에는 합쳐지는 가지가 없습니다. 암튼, 각각의 요소를 노드(node)라고 부르며, 각 노드는 해당하는 요소(값)와 여러 하위 노드를 가르키는 연결 고리가 있습니다. 리스트의 각 원소가 다음 요소를 가리키는 링크가 있는 것과 비슷한데, 트리의 경우 각 노드 별로 두 개 이상의 연결 고리가 있습니다. 각 노드마다 연결 고리가 최대 두 개까지만 있는 트리를 이진트리(Binary tree)라고 따로 부르기도 합니다.

다소 어렵게 느껴지는 트리를 알아야 하는 이유는, 트리로 무언가 계층적인 구조를 다루기에 편리하고, 계층적인 구조로 무언가를 다루는 일은 개발할 때 여러모로 유용해서, 트리의 쓰임새도 덩달아 많기 때문입니다. HTML을 이미 공부하셨다면, DOM 트리라는 표현도 들어보셨을 텐데요, HTML 문서도 트리로 표현합니다. `<ul>` 노드가 있고, 그 자식들로 `<li>` 노드들이 붙어 있는 상황이 딱 트리 구조인 셈이죠. 루트 노드가 `<html>`이고요. 우리가 루비, 파이썬, 자바스크립트 등의 언어로 프로그래밍할 때의 소스코드(텍스트)도 AST라는 트리 구조로 변환되는 과정이 들어있습니다. 자세히 알 필요는 아직 없지만, 뭐가 됐든 암튼 꽤 많이 쓰인다고 알고 넘어가 보기로 해요.

그리고, 트리 구조로 자료를 정렬해 두면, 대량의 데이터를 검색하는 데에도 매우 효과적으로 활용할 수 있습니다. 그래서 2편에 설명드린 데이터베이스도 내부적으로는 B-tree라는 트리 구조를 활용해서 데이터를 색인(index)해 둡니다. 덕분에 아주 많은 데이터 중에서도 순식간에 데이터를 찾아낼 수 있습니다.

트리는 그 쓰임새도 다양하고, 또 그만큼 종류도 다양합니다. 우선은 이 정도로만 알고, 기회가 되면 자세히 알아보기로 해요. (솔직히 말해 제가 잘 설명할 자신이 없네요)

## 계산 복잡도 (Computational Complexity)

어떤 자료 구조를 쓰면서 특정 연산을 하는데 얼마나 복잡한가를 평가하고 예측하는 것이 '계산 복잡도'입니다. 얼마나 복잡한지를 알 수 있으니, 덜 복잡한 구조로 되어 있다면, 반대로 말해 효율적이라는 얘기입니다. 앞서도 언급했듯, 그 자료구조를 활용하는 알고리즘과 직결된 내용이라서, 알고리즘 책에서 배울 수 있는 내용입니다.

원하는 작업을 하는데, 얼마만큼의 메모리나 디스크 공간을 필요로 하는지를 '공간 복잡도'(space complexity)라고 하고, 얼마나 빠르게 처리할 수 있는지를 '시간 복잡도'(time complexity)라고 말합니다. 어떤 자료 구조를 쓰는 어떤 알고리즘은 시간은 빠르지만 메모리를 많이 쓴다거나, 반대로 어떤 알고리즘은 원하는 일을 하는 시간은 매우 오래 걸리지만, 아주 적은 메모리로도 원하는 작업을 끝낼 수 있기도 해서 둘 다를 고려하기도 합니다. 하지만 별도로 굳이 언급하지 않는다면, 보통 '시간 복잡도'를 얘기하는 편입니다. 즉, '계산 복잡도'라고 하면, 어떤 데이터로 어떤 작업을 하는데 걸리는 시간의 정도라고 생각하시면 크게 어긋나지는 않을 것 같습니다.

이 복잡도를 평가하고 예측하는 기준으로, 빅 오 표기법(Big O notation)을 씁니다. 언뜻 보기엔 단순히 정해진 테스트 작업을 두고 몇 초에 다 처리할 수 있는가 같은 기준을 쓰면 될 것 같지만, 그러면 해당 자료구조나 알고리즘을 어떤 프로그래밍 언어로 어떤 하드웨어에서 구현해 실행하는가에 따라 수시로 달라지기 때문에 유용한 잣대가 되지 않습니다. 그래서 몇 가지 기준을 정해서 쓰는데, 그중 하나가 빅 오 표기법입니다. 알파벳 대문자에 이어 괄호를 열고 수식 같은 게 들어 있습니다.

    O(1), O(log n), O(n), O(n log n), O(n^2), O(2^n), O(n!)

이런 식으로요. 다른 개발자들과 말할 때는 오 원, 오 로그 엔, 오 엔, 오  엔 로그 엔, 오 엔 스퀘어, 오 엔 팩토리얼로 읽습니다. 2^n은 뭐라고 읽는지 모르겠습니다. 지수 시간이 걸린다고도 하고, exponential(기하급수적)이라고도 하는데, 정식으로는 뭐라고 부르는지 모르겠네요. 그리고, 우리말로 오 일, 오 엔 제곱 등으로 얘기해도 다른 사람이 알아는 듣겠습니다만, 꽤 생소해할 거예요.

이 표기법은, 데이터가 꽤 많이 있을 때, 자료의 건수에 비해 어느 정도로 오래 걸리는가를 의미하는데요, 예를 들어, O(n)의 경우는 데이터가 n건 있을 때 n만큼의 시간이 걸린다는 뜻으로, 데이터 분량에 비례해서 점점 오래 걸린다는 뜻입니다. O(1)의 경우는 데이터의 건수와 상관없이 늘 똑같은 시간이 걸린다는 뜻으로, 아주 효과적임을 뜻합니다. O(log n) 같은 경우 로그 n에 비례하는 시간이 걸린다는 뜻이라서, 데이터가 아주 많아도 꽤 효과적으로 일을 할 수 있습니다. 이진 검색처럼 log의 밑수가 2인 경우가 많아서 O(log n)이라고 하면 흔히 지수가 2인 로그를 뜻하기도 합니다. 뭐가 뭔지 어렵다면, 일단 O(1) = 아주 빠른 것에서부터 뒤로 갈수록 더 느려지는 거라고 생각하셔도 됩니다.

    O(1) < O(log n) < O(n) < O(n log n)

이 정도만이라도 기억하면 좋고요, 앞서 자료 구조에 대해서 몇 가지 주요 연산에 대해서만이라도 빅 오 표기법으로 대략 알면, 당장은 충분한 수준인 거죠.

배열(Array)에서 몇 번째 데이터를 가져오는 연산은, 배열은 이미 인덱스가 갖춰져 있기 때문에 O(1)에 빠르게 끝낼 수 있습니다.  그러나 배열의 중간, 예를 들어 두 번째, 자리에 어떤 데이터를 넣는 연산은, 그 원래 있던 두 번째 자리 데이터와 그 뒤의 데이터들을 차례로 다 밀어내야 해서 O(n)의 시간이 필요합니다. 데이터 건수에 비례하는 시간이 걸리는 거지요.

반대로 리스트의 경우, 특정 위치에 값을 추가하는 일은 아주 간단합니다. 그저 원하는 위치에 그 앞 데이터의 연결고리를 새 데이터에 연결하고, 새 데이터의 그다음 연결 고리를 원래 데이터로 지정하면 됩니다. O(1)에 끝낼 수 있지요. 하지만, 전체 데이터의 건수를 센다거나, 특정 몇 번째 요소를 찾고자 하는 일은 데이터를 일일이 순회해야 하기 때문에 O(n)의 시간이 걸립니다.

해시의 경우 어떤 자료구조로 구현하느냐에 따라 조금 달라지기도 합니다만, 보통은 해시함수를 한번 거쳐서 원하는 위치를 배열처럼 뿅 찾아가기에 O(1)의 아주 빠른 속도로 원하는 데이터가 있는지 없는지, 있다면 무엇인지 알 수 있습니다. 실상은 해시 충돌(collision)이라는 게 있어서 정확하지는 않지만 일단 O(1)이라고 보면 됩니다. 대신 순서상 몇 번째 데이터를 찾는다거나 전체 건수를 알기는 어렵습니다.

그리고 트리는, 만약 정렬해둔 이진트리라면 밑수가 2인 로그 n에 비례해서, 아주 데이터가 많더라도 아주 빠르게 데이터를 검색할 수 있는 구조입니다. 그리고 데이터를 추가하거나 삭제하는 시간도 매우 빨라서 대량의 데이터를 다루는 데에 유용합니다.

## 마무리

이제껏 설명드린 주제들 중에 어쩌면 가장 어려운 내용일지도 모르겠습니다. 아니면 단지 제가 쉽게 설명할 내공이 없어서 그럴지도 모르고요. 유독 틀린 내용이 많을 것 같기는 한데, 부담 없이 지적해주세요. 저도 공부하는 의미가 될 테니 감사한 일이죠.

마무리로, 이 연재의 하이라이트, 할 것과 하지 말 것을 정리하겠습니다.

Do: 배열, 리스트, 해시, 트리를 공부하고 주요 작업에 대해 시간 복잡도를 알아 두기
Don't: 알고리즘 컨테스트 공부, 코딩 인터뷰 준비 등

물론, 취업이나 이직을 목표로 하고 있다면, 알고리즘 컨테스트나 코닝 인터뷰 문제 풀이가 아주 큰 도움이 되겠습니다만, 만약 제 연재의 컨셉인 간단한 웹서비스 직접 만들기에는 전혀 도움이 되지 않으므로, 무시하고 넘어가도록 합시다.

긴 글 읽어주셔서 고맙습니다. 늘 그렇듯, 마음에 드셨다면, 주변에 공유해주시고, 심기 불편하시다면, 마음이 편해지는 글을 찾거나 직접 작성해서 공유해 주세요. 그럼 다음 편에 만나요.

* https://en.wikipedia.org/wiki/Array_data_structure
* https://en.wikipedia.org/wiki/Tree_(data_structure)
* https://en.wikipedia.org/wiki/B-tree
* https://en.wikipedia.org/wiki/Big_O_notation
