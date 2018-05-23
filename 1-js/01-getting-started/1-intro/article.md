# JavaScript 소개

자바스크립트에서 우리가 이것과 다른 기술을 접목하여 이룰 수 있는것에 대해 특별한 점을 살펴보겠습니다.

## JavaScript 란 무엇인가요?

*JavaScript* 는 *"동적인 웹페이지"* 를 위해 만들어졌습니다.

이 언어의 프로그램을 *scripts* 라고 합니다. 그것들은 HTML에 바로 쓰여지고 페이지가 로드 될 때 자동으로 실행될 수 있습니다.

스크립트는 일반 텍스트로 제공되고 실행됩니다. 그들은 특별한 준비 작업이나 편집 작업이 필요하지 않습니다.

이 측면에서 JavaScript는 [Java](http://en.wikipedia.org/wiki/Java)라고 불리는 언어와 매우 다릅니다.

```smart header="왜 <u>Java</u>Script 인가요?"
JavaScript 가 만들어졌을때, 처음엔 "LiveScript" 라는 다른 이름이였습니다. 그러나 당시에 Java 프로그래밍 언어가 매우 유명했기에 자바의 "동생" 으로써 위치하는 것이 도움이 될것이라 결정됬습니다.

그러나 진화함에 따라 JavaScript는 [ECMAScript] (http://en.wikipedia.org/wiki/ECMAScript)라는 자체 사양을 사용하여 완전히 독립된 언어가되었으며 이제는 Java와 전혀 관련이 없습니다.
```

현재 자바 스크립트는 브라우저뿐만 아니라 서버 또는 실제로는 [the JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine) 라고하는 특별한 프로그램이있는 모든 장치에서도 실행할 수 있습니다.

브라우저는 내장되어 있으며 때로는 "JavaScript 가상머신" 이라고 불립니다.

"코드명" 에 따라 엔진에 차이가 있습니다. 예로 들면:

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- Chrome 과 Opera.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- Firefox.
- ...다른 코드명으로는 각각의 IE에서  다른 버전인 "Trident", "Chakra,  Microsoft Edge 의 "ChakraCore", 여러 Safari의 "Nitro" 와 "SquirrelFish" .

위의 용어는 인터넷의 개발자 관련 기사에 나오거나 직접 사용되기 때문에 기억해두면 좋습니다. 예를 들어 "기능 X가 V8에서 지원되는 경우" Chrome 및 Opera에서 작동하는걸 알 수 있습니다.

```smart header="어떻게 엔진이 작동하나요?"

엔진은 매우 복잡하지만 기본적인 것은 매우 간단합니다.

1. 엔진 (브라우저인 경우 포함) 이 스크립트를 읽습니다 ("파싱").
2. 그런 다음 스크립트를 기계어로 변환 ("컴파일")합니다.
3. 그리고 기계어는 꽤 빠르게 실행됩니다.

엔진은 프로세스의 모든 단계에서 최적화를 적용합니다. 심지어 실행중인 컴파일 된 스크립트를 감시하고 이를 통해 흐르는 데이터를 분석하며 해당 정보를 기반으로 컴퓨터 코드에 최적화를 적용합니다. 결과적으로 스크립트는 매우 빨라집니다.
```

## 브라우저 내 JavaScript는 무엇을 할 수 있나요?

최신 자바 스크립트는 "안전한" 프로그래밍 언어입니다. 처음에는 메모리와 CPU에 저수준 접근이 필요하지 않은 브라우저를 만들어 졌기에 이를 제공하지 않습니다.

기능은 JavaScript를 실행하는 환경에 크게 의존합니다. 예를 들어, [Node.JS](https://wikipedia.org/wiki/Node.js) 는 JavaScript 가 임의의 파일을 읽고 쓸 수있는 기능, 네트워크 요청 수행 기능을 지원합니다.

브라우저 안에서 JavaScript 는 웹 페이지 조작, 사용자 및 웹 서버와의 상호 작용과 관련된 모든 것을 할 수 있습니다.

예를 들어, 브라우저 안에서 JavaScript 는 다음과 같은게 가능합니다:

- 페이지에 새 HTML을 추가하고 기존 내용을 변경하고 스타일을 수정합니다.
- 사용자 동작(마우스 클릭, 포인터 이동, 키 누름 같은 상황) 에 반응하여 실행됩니다.
- 네트워크를 통해 원격 서버로 요청 보내기, 파일 다운로드 및 업로드. ([AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) 와 [COMET](https://en.wikipedia.org/wiki/Comet_(programming)) 로 불리는 기술).
- 쿠키 가져 오기 및 설정, 방문자에게 질문하기, 메시지 표시하기.
- 클라이언트 측의 데이터 기억하기 ("local storage").

## 브라우저 내 JavaScript가 할수 없는 것은 뭔가요?

브라우저의 JavaScript 기능은 사용자의 안전을 위해 제한됩니다. 악의적인 웹 페이지가 개인 정보에 액세스하거나 사용자 데이터를 손상시키는 것을 방지하기 위해서 입니다.

이러한 제한의 예는 다음과 같습니다:

- 웹 페이지의 JavaScript 는 하드 디스크의 임의 파일을 읽고 쓰거나 복사하거나 프로그램을 실행할 수 없으며 OS 시스템 기능에 직접 액세스 할 수 없습니다.

    최신 브라우저는 파일을 처리 할 수 있지만 액세스가 제한되며 사용자가 특정 작업 (파일을 브라우저 창에 "드랍"또는 `<input>`태그를 통해 선택하는 것)을 수행하는 경우에만 제공됩니다.

    카메라 / 마이크 및 기타 장치와 상호 작용하는 방법이 있지만 사용자의 명시적인 허가가 필요합니다. 따라서 JavaScript 가 활성화 된 페이지는 웹 카메라를 몰래 사용하여 주변을 관찰할 수 없으며 [NSA] (https://en.wikipedia.org/wiki/National_Security_Agency)로 정보를 보냅니다.
- 다른 탭 / 창은 일반적으로 서로에 대해 알지 못합니다. 때로는 기존 창에서 JavaScript를 사용하여 다른 창을 여는 경우가 있습니다. 그러나 이 경우에도 한 페이지의 JavaScript는 다른 사이트 (다른 도메인, 프로토콜 또는 포트)에서 온 경우 다른 페이지에 액세스하지 못할 수 있습니다.

    이를 "동일 출처 정책(Same Origin Policy)"이라고합니다. 이 문제를 해결하려면 *두 페이지* 모두에 데이터 교환을 처리하는 특수 JavaScript 코드가 있어야합니다.

    이 제한은 다시 사용자의 안전을위한 것입니다. 사용자가 열어 본 `http://anysite.com`의 페이지는 `http://gmail.com`이라는 URL로 다른 브라우저 탭에 액세스 할 수 없어서 정보를 훔칠 수 없습니다.
- JavaScript 는 인터넷을 통해 현재 페이지가있는 서버와 쉽게 통신 할 수 있습니다. 그러나 다른 사이트 / 도메인에서 데이터를 수신하는 능력은 무력합니다. 가능하면 원격 측에서 명시적으로 동의(HTTP 헤더로 표현)해야 합니다.

![](limitations.png)

자바 스크립트가 서버에서 처럼 브라우저 외부에서 사용되는 경우 이러한 제한은 존재하지 않습니다. 최신 브라우저는 플러그인 / 확장 기능을 설치하는 것을 허용하며 그를 통해 확장된 권한을 가질 수 있습니다.

## 무엇이 JavaScript 를 특별하게 만드나요?

자바 스크립트에는 적어도 *세 가지* 훌륭한 것들이 있습니다.:

```compare
+ HTML / CSS와의 완벽한 통합.
+ 간단하게 끝낼 수 있는 쉬운 일.
+ 모든 주요 브라우저에서 지원되며 기본적으로 사용하도록 설정.
```

결합된 이 세 가지는 JavaScript 및 다른 브라우저 기술에만 존재합니다.

이것이 바로 JavaScript를 독창적으로 만드는 이유이며 브라우저 인터페이스를 생성하는 가장 보편적인 도구입니다.

While planning to learn a new technology, it's beneficial to check its perspectives. So let's move on to the modern trends that include new languages and browser abilities.


## Languages "over" JavaScript

The syntax of JavaScript does not suit everyone's needs. Different people want different features.

That's to be expected, because projects and requirements are different for everyone.

So recently a plethora of new languages appeared, which are *transpiled* (converted) to JavaScript before they run in the browser.

Modern tools make the transpilation very fast and transparent, actually allowing developers to code in another language and autoconverting it "under the hood".

Examples of such languages:

- [CoffeeScript](http://coffeescript.org/) is a "syntactic sugar" for JavaScript, it introduces shorter syntax, allowing to write more precise and clear code. Usually Ruby devs like it.
- [TypeScript](http://www.typescriptlang.org/) is concentrated on adding "strict data typing", to simplify development and support of complex systems. It is developed by Microsoft.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps). It was initially offered by Google as a replacement for JavaScript, but as of now, browsers require it to be transpiled to JavaScript just like the ones above.

There are more. Of course even if we use one of those languages, we should also know JavaScript, to really understand what we're doing.

## Summary

- JavaScript was initially created as a browser-only language, but now it is used in many other environments as well.
- At this moment, JavaScript has a unique position as the most widely-adopted browser language with full integration with HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
