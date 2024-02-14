# You Don't Know JS: Up & Going
# 3장: YDKJS 속으로

이 시리즈의 목적은 무엇일까요? 간단히 말해서, 누군가가 "좋은 부분"이라고 부르는 언어의 일부분도 아니고, 직장에서 업무를 수행하는 데 필요한 최소한의 양을 배우는 것도 아니며, 자바스크립트의 *모든 부분*을 배우는 작업을 진지하게 받아들이는 것입니다.

다른 언어를 사용하는 개발자는 자신이 주로 사용하는 언어의 대부분 또는 전부를 배우기 위해 노력하지만, JS 개발자는 일반적으로 언어를 많이 배우지 않는 것처럼 보입니다. 이는 결코 좋은 일이 아니며, 이러한 현상을 계속 방치해서는 안 됩니다.

*You Don't Know JS* *(*YDKJS*) 시리즈는 JS 학습에 대한 일반적인 접근 방식과는 극명한 대조를 이룹니다. 또한, 여러분이 읽게 될 다른 JS 책과 다릅니다. 이 책은 여러분의 안전지대를 넘어서서 여러분이 접하는 모든 동작 하나하나에 대해 더 깊은 "왜?"라는 질문을 던지도록 도전합니다. 그 도전에 응할 준비가 되셨나요?

이 마지막 장에서는 YDKJS 시리즈의 나머지 책에서 무엇을 기대할 수 있는지, 그리고 *YDKJS*를 기반으로 JS 학습의 기초를 가장 효과적으로 구축하는 방법을 간략하게 요약해 보겠습니다.


## Scope & Closures

여러분이 이해해야 할 기본적인 사항 중 하나는 자바스크립트에서 변수의 스코프 지정이 어떻게 이루어지는가 입니다. 변수 스코프에 대해 단편적이고 모호한 *믿음*을 갖는 것만으로는 충분하지 않습니다.

'스코프와 클로저'라는 제목은 JS가 '인터프리터 언어'이기 때문에 컴파일되지 않는다는 오해를 반박하는 것으로 시작됩니다.

JS 엔진은 실행 직전(때로는 실행 중!)에 코드를 컴파일합니다. 따라서 코드에 대한 컴파일러의 접근 방식에 대한 더 깊은 이해를 통해 변수 및 함수 선언을 찾고 처리하는 방법을 이해할 것입니다. 그 과정에서 JS 변수 범위 관리에 대한 일반적인 비유인 "호이스팅"을 볼 수 있습니다.

"렉시컬 스코프"에 대한 이해는 이 책의 마지막 장에서 클로저(클로저는 아마도 JS에서 가장 중요한 개념일 것입니다.)에 대한 탐구의 기반이 됩니다. 따라서 스코프가 어떻게 작동하는지 제대로 이해하지 못한다면 클로저는 여전히 이해할 수 없는 상태로 남아 있을 것입니다.

이 책의 2장에서 간략하게 소개한 모듈 패턴은 클로저의 중요한 응용 사례 중 하나입니다. 모듈 패턴은 자바스크립트에서 가장 널리 사용되는 코드 구성 패턴이므로 모듈 패턴에 대한 깊은 이해가 최우선 순위 중 하나가 되어야 합니다.


## this & Object Prototypes

아마도 자바스크립트에 대해 가장 널리 퍼져 있고 지속적인 오해 중 하나는 `this` 키워드가 해당 키워드가 나타나는 함수를 참조한다는 것입니다. 이것은 심각한  착각입니다.

`this` 키워드는 해당 함수가 실행되는 방식에 따라 동적으로 바인딩되며, `this` 바인딩을 이해하고 완전히 결정하기 위한 네 가지 간단한 규칙이 있습니다.

`this` 키워드와 밀접한 관련이 있는 것은 렉시컬 스코프 변수를 찾는 방법과 유사한 속성에 대한 조회 체인인 객체 프로토타입 메커니즘입니다. 
그러나 프로토타입에는 또 다른 큰 오해가 있는데, (가짜) 클래스와 (소위 "프로토타입") 상속을 에뮬레이트한다는 생각입니다.

안타깝게도 자바스크립트에 클래스 및 상속 디자인 패턴을 도입하려는 시도는 여러분이 시도할 수 있는 최악의 선택입니다. 구문(syntax)상으로는 클래스와 같은 것이 존재한다고 착각할 수 있지만, 실제로는 프로토타입 메커니즘은 근본적으로 정반대이기 때문입니다.

문제는 이러한 불일치를 무시하고 구현하는 것이 '상속'인 것처럼 가장하는 것이 더 나은지, 아니면 객체 프로토타입 시스템이 실제로 작동하는 방식을 배우고 수용하는 것이 더 적절한지 여부입니다. 후자는 "행동 위임(behavior delegation)"이라는 이름이 더 적절합니다.

이는 구문적 선호 이상의 것입니다. 위임은 디자인의 필요성을 클래스와 상속으로 대체하는 완전히 다르고 더 강력한 디자인 패턴입니다. 하지만 이러한 주장은 자바스크립트 역사상 이 주제에 관한 거의 모든 블로그 포스트, 책, 컨퍼런스 강연을 정면으로 반박하는 것입니다.

위임과 상속에 관해 제가 주장하는 것은 자바스크립트와 그 구문을 싫어해서가 아니라, 자바스크립트의 진정한 기능이 제대로 활용되고 끝없는 혼란과 좌절이 사라지길 바라는 마음에서 나온 것입니다.

하지만 프로토타입과 위임에 관한 사례는 여기서 소개하는 것보다 훨씬 더 복잡한 문제입니다. 자바스크립트 "클래스"와 "상속"에 대해 알고 있다고 생각하는 모든 것을 재고할 준비가 되셨다면, 이 시리즈의 제목인 *this & Object Prototypes*의 4~6장을 통해 "빨간 약"(*매트릭스* 1999)을 복용할 수 있는 기회를 제공하고자 합니다.


## Types & Grammar

The third title in this series primarily focuses on tackling yet another highly controversial topic: type coercion. Perhaps no topic causes more frustration with JS developers than when you talk about the confusions surrounding implicit coercion.
이 시리즈의 세 번째 주제는 주로 논란이 많은 또 다른 주제인 타입 강제를 다루는 데 중점을 둡니다. 아마도 암시적 강제를 둘러싼 혼란에 대해 이야기할 때만큼 JS 개발자들을 좌절하게 만드는 주제는 없을 것입니다.

이 시리즈의 세 번째 제목은 주로 논란이 많은 또 다른 주제인 유형 강제를 다루는 데 중점을 둡니다. 아마도 암시적 강제를 둘러싼 혼란에 대해 이야기하는 것보다 JS 개발자에게 더 큰 좌절감을 주는 주제는 없을 것입니다.



By far, the conventional wisdom is that implicit coercion is a "bad part" of the language and should be avoided at all costs. In fact, some have gone so far as to call it a "flaw" in the design of the language. Indeed, there are tools whose entire job is to do nothing but scan your code and complain if you're doing anything even remotely like coercion.
지금까지 암시적 강제는 언어의 '나쁜 부분'이며 어떤 대가를 치르더라도 피해야 한다는 것이 일반적인 통념입니다. 실제로 일부에서는 이를 언어 설계의 '결함'이라고까지 부르기도 합니다. 실제로 코드를 스캔하고 사용자가 강압과 같은 행위를 할 경우 불만을 표시하는 것이 전부인 도구도 있습니다.

지금까지, 암묵적인 강제는 언어의 "나쁜 부분"이므로 어떤 대가를 치르더라도 피해야 한다는 것이 일반적인 통념입니다. 실제로 어떤 사람들은 이를 언어 설계의 "결함"이라고 부르기까지 했습니다. 실제로 코드를 스캔하고 강제와 같은 원격 작업을 수행하는 경우 불평하는 것 외에는 아무것도 수행하지 않는 도구가 있습니다.



But is coercion really so confusing, so bad, so treacherous, that your code is doomed from the start if you use it?
하지만 강제가 정말 그렇게 혼란스럽고, 나쁘고, 위험해서 이를 사용하면 코드가 처음부터 파멸할까요?

그러나 강제는 실제로 너무 혼란스럽고, 너무 나쁘고, 너무 위험해서 코드를 사용하면 처음부터 코드가 망가질 정도입니까?


I say no. After having built up an understanding of how types and values really work in Chapters 1-3, Chapter 4 takes on this debate and fully explains how coercion works, in all its nooks and crevices. We see just what parts of coercion really are surprising and what parts actually make complete sense if given the time to learn.
저는 아니라고 말합니다. 1~3장에서 유형과 값이 실제로 어떻게 작동하는지에 대한 이해를 쌓았다면, 4장에서는 이 논의를 이어받아 강제가 구석구석까지 어떻게 작동하는지에 대해 자세히 설명합니다. 강압의 어떤 부분이 정말 놀랍고, 어떤 부분이 학습할 시간이 주어진다면 실제로 완전히 이해가 되는지 살펴봅니다.

난 반대 야. 1~3장에서 유형과 값이 실제로 어떻게 작동하는지에 대한 이해를 쌓은 후 4장에서는 이 논쟁을 다루고 강압이 구석구석까지 작동하는 방식을 완전히 설명합니다. 우리는 강압의 어떤 부분이 실제로 놀라운지, 배울 시간이 주어진다면 어떤 부분이 실제로 완전히 이해되는지 알 수 있습니다.


But I'm not merely suggesting that coercion is sensible and learnable, I'm asserting that coercion is an incredibly useful and totally underestimated tool that *you should be using in your code.* I'm saying that coercion, when used properly, not only works, but makes your code better. All the naysayers and doubters will surely scoff at such a position, but I believe it's one of the main keys to upping your JS game.
하지만 저는 단순히 강제가 합리적이며 배울 수 있다고 제안하는 것이 아니라, 강제가 엄청나게 유용하지만 완전히 과소평가된 도구이며 *코드에서 사용해야 한다고 주장합니다. 즉, 강제는 제대로 사용하면 작동할 뿐만 아니라 코드를 개선할 수 있다는 것입니다. 모든 반대자들과 의심하는 사람들은 분명히 그런 입장을 비웃을 것이지만, 저는 그것이 JS 게임을 향상시키는 주요 열쇠 중 하나라고 믿습니다.

그러나 나는 단지 강제가 합리적이고 학습 가능하다고 제안하는 것이 아니라 강제가 코드에서 사용해야 하는 매우 유용하면서도 완전히 과소평가된 도구라고 주장하는 것입니다. 강제를 적절하게 사용하면 효과가 있을 뿐만 아니라 코드도 더 좋아진다는 뜻입니다. 모든 반대자들과 의심자들은 확실히 그러한 입장을 비웃을 것이지만 나는 이것이 JS 게임을 향상시키는 주요 열쇠 중 하나라고 믿습니다.


Do you want to just keep following what the crowd says, or are you willing to set all the assumptions aside and look at coercion with a fresh perspective? The *Types & Grammar* title of this series will coerce your thinking.
사람들이 말하는 것을 계속 따르고 싶으신가요, 아니면 모든 가정을 제쳐두고 새로운 시각으로 강제를 바라보고 싶으신가요? 이 시리즈의 *타입과 문법*이라는 제목이 여러분의 생각을 강요할 것입니다.

군중이 말하는 것을 계속 따르고 싶습니까, 아니면 모든 가정을 제쳐두고 새로운 관점으로 강제를 바라볼 의향이 있습니까? 이 시리즈의 유형 및 문법 제목은 당신의 생각을 강요할 것 입니다 .


## Async & Performance

The first three titles of this series focus on the core mechanics of the language, but the fourth title branches out slightly to cover patterns on top of the language mechanics for managing asynchronous programming. Asynchrony is not only critical to the performance of our applications, it's increasingly becoming *the* critical factor in writability and maintainability.
이 시리즈의 첫 세 편은 언어의 핵심 메커니즘에 초점을 맞췄지만, 네 번째 편에서는 비동기 프로그래밍을 관리하기 위한 언어 메커니즘 위에 있는 패턴을 다루기 위해 약간 더 확장했습니다. 비동기는 애플리케이션의 성능에 매우 중요할 뿐만 아니라 쓰기 가능성과 유지보수성에서 점점 더 중요한 요소가 되고 있습니다.

이 시리즈의 처음 세 제목은 언어의 핵심 메커니즘에 초점을 맞추고 있지만 네 번째 제목은 비동기 프로그래밍 관리를 위한 언어 메커니즘 외에 패턴을 다루기 위해 약간 분기됩니다. 비동기성은 애플리케이션 성능에 중요할 뿐만 아니라 쓰기 가능성과 유지 관리 가능성에서도 점점 더 중요한 요소 가 되고 있습니다.


The book starts first by clearing up a lot of terminology and concept confusion around things like "async," "parallel," and "concurrent," and explains in depth how such things do and do not apply to JS.
이 책은 먼저 '비동기', '병렬', '동시'와 같은 용어와 개념의 혼란을 정리하는 것으로 시작하여 이러한 것들이 JS에 어떻게 적용되고 적용되지 않는지에 대해 자세히 설명합니다.

이 책은 먼저 "비동기", "병렬" 및 "동시"와 같은 것들에 대한 많은 용어와 개념 혼란을 정리하고 이러한 것들이 JS에 어떻게 적용되고 적용되지 않는지 깊이 설명합니다.


Then we move into examining callbacks as the primary method of enabling asynchrony. But it's here that we quickly see that the callback alone is hopelessly insufficient for the modern demands of asynchronous programming. We identify two major deficiencies of callbacks-only coding: *Inversion of Control* (IoC) trust loss and lack of linear reason-ability.
그런 다음 비동기를 활성화하는 주요 방법인 콜백을 살펴봅니다. 하지만 여기서 우리는 콜백만으로는 비동기 프로그래밍의 최신 요구 사항을 충족하기에는 절망적으로 부족하다는 것을 금방 알 수 있습니다. 우리는 콜백 전용 코딩의 두 가지 주요 결함을 확인했습니다: *제어의 역전*(IoC) 신뢰 손실과 선형적 추론 능력의 부족입니다.

그런 다음 비동기를 활성화하는 기본 방법으로 콜백을 살펴보겠습니다. 그러나 여기서 우리는 콜백만으로는 현대적인 비동기 프로그래밍 요구 사항을 충족하기에는 절망적으로 불충분하다는 것을 금방 알 수 있습니다. 우리는 콜백 전용 코딩의 두 가지 주요 결함, 즉 IoC( Inversion of Control ) 신뢰 손실과 선형 합리성 부족을 식별합니다.


To address these two major deficiencies, ES6 introduces two new mechanisms (and indeed, patterns): promises and generators.
이 두 가지 주요 결함을 해결하기 위해 ES6는 약속과 제너레이터라는 두 가지 새로운 메커니즘(그리고 실제로는 패턴)을 도입했습니다.

이러한 두 가지 주요 결함을 해결하기 위해 ES6에서는 Promise와 Generator라는 두 가지 새로운 메커니즘(실제로 패턴)을 도입했습니다.


Promises are a time-independent wrapper around a "future value," which lets you reason about and compose them regardless of if the value is ready or not yet. Moreover, they effectively solve the IoC trust issues by routing callbacks through a trustable and composable promise mechanism.
약속은 '미래 가치'를 시간과 무관하게 감싸는 래퍼로, 가치가 아직 준비되었는지 여부에 관계없이 추론하고 구성할 수 있습니다. 또한, 신뢰할 수 있고 컴포저블한 프로미스 메커니즘을 통해 콜백을 라우팅함으로써 IoC 신뢰 문제를 효과적으로 해결합니다.

Promise는 "미래 가치"에 대한 시간 독립적인 래퍼로, 값이 아직 준비되었는지 여부에 관계없이 이를 추론하고 구성할 수 있습니다. 또한 신뢰할 수 있고 구성 가능한 약속 메커니즘을 통해 콜백을 라우팅하여 IoC 신뢰 문제를 효과적으로 해결합니다.


Generators introduce a new mode of execution for JS functions, whereby the generator can be paused at `yield` points and be resumed asynchronously later. The pause-and-resume capability enables synchronous, sequential looking code in the generator to be processed asynchronously behind the scenes. By doing so, we address the non-linear, non-local-jump confusions of callbacks and thereby make our asynchronous code sync-looking so as to be more reason-able.
제너레이터는 JS 함수에 대한 새로운 실행 모드를 도입하여 '산출' 지점에서 제너레이터를 일시 중지했다가 나중에 비동기적으로 다시 시작할 수 있습니다. 일시 중지 및 재개 기능을 사용하면 제너레이터의 동기식, 순차적으로 보이는 코드를 백그라운드에서 비동기적으로 처리할 수 있습니다. 이를 통해 콜백의 비선형적, 비로컬 점프 혼동을 해결하고 비동기식 코드를 동기식처럼 보이게 하여 보다 합리적으로 만들 수 있습니다.

생성기는 JS 함수에 대한 새로운 실행 모드를 도입하여 생성기를 yield특정 지점에서 일시 중지하고 나중에 비동기적으로 다시 시작할 수 있습니다. 일시 중지 및 재개 기능을 사용하면 생성기의 동기적이고 순차적인 코드를 백그라운드에서 비동기적으로 처리할 수 있습니다. 그렇게 함으로써 우리는 콜백의 비선형, 비로컬 점프 혼란을 해결하고 비동기 코드를 보다 합리적으로 동기화되도록 만듭니다.



But it's the combination of promises and generators that "yields" our most effective asynchronous coding pattern to date in JavaScript. In fact, much of the future sophistication of asynchrony coming in ES7 and later will certainly be built on this foundation. To be serious about programming effectively in an async world, you're going to need to get really comfortable with combining promises and generators.
하지만 지금까지 자바스크립트에서 가장 효과적인 비동기 코딩 패턴을 '산출'하는 것은 프로미스와 제너레이터의 조합입니다. 실제로 ES7 이후 버전에 도입될 비동기성의 정교함은 대부분 이 기반 위에 구축될 것입니다. 비동기 세계에서 효과적으로 프로그래밍하려면 프로미스와 제너레이터를 결합하는 데 익숙해져야 합니다.

그러나 JavaScript에서 현재까지 가장 효과적인 비동기 코딩 패턴을 "산출"하는 것은 Promise와 생성자의 조합입니다. 실제로 ES7 이후 버전에서 구현될 비동기식 정교함의 상당 부분은 확실히 이러한 기반 위에 구축될 것입니다. 비동기 세계에서 효과적으로 프로그래밍하려면 Promise와 Generator를 결합하는 데 익숙해져야 합니다.



If promises and generators are about expressing patterns that let our programs run more concurrently and thus get more processing accomplished in a shorter period, JS has many other facets of performance optimization worth exploring.
프로미스와 제너레이터가 프로그램을 더 많이 동시에 실행하여 더 짧은 시간에 더 많은 처리를 수행할 수 있는 패턴을 표현하는 것이라면, JS에는 성능 최적화와 관련해 살펴볼 만한 다른 많은 측면이 있습니다.

Promise와 Generator가 프로그램을 동시에 더 많이 실행하여 더 짧은 기간에 더 많은 처리를 수행할 수 있도록 하는 패턴을 표현하는 것이라면 JS에는 탐색할 가치가 있는 성능 최적화의 다른 많은 측면이 있습니다.



Chapter 5 delves into topics like program parallelism with Web Workers and data parallelism with SIMD, as well as low-level optimization techniques like ASM.js. Chapter 6 takes a look at performance optimization from the perspective of proper benchmarking techniques, including what kinds of performance to worry about and what to ignore.
5장에서는 웹 워커를 사용한 프로그램 병렬 처리와 SIMD를 사용한 데이터 병렬 처리와 같은 주제와 ASM.js와 같은 저수준 최적화 기법을 살펴봅니다. 6장에서는 걱정해야 할 성능과 무시해야 할 성능을 포함해 적절한 벤치마킹 기법의 관점에서 성능 최적화를 살펴봅니다.

5장에서는 Web Workers를 사용한 프로그램 병렬 처리, SIMD를 사용한 데이터 병렬 처리, ASM.js와 같은 하위 수준 최적화 기술과 같은 주제를 살펴봅니다. 6장에서는 어떤 종류의 성능을 걱정하고 무엇을 무시할지 등 적절한 벤치마킹 기법의 관점에서 성능 최적화를 살펴봅니다.



Writing JavaScript effectively means writing code that can break the constraint barriers of being run dynamically in a wide range of browsers and other environments. It requires a lot of intricate and detailed planning and effort on our parts to take a program from "it works" to "it works well."
자바스크립트를 효과적으로 작성한다는 것은 다양한 브라우저와 기타 환경에서 동적으로 실행되는 제약 조건을 극복할 수 있는 코드를 작성하는 것을 의미합니다. 프로그램을 "작동하는" 수준에서 "잘 작동하는" 수준으로 끌어올리기 위해서는 매우 복잡하고 세밀한 계획과 노력이 필요합니다.

JavaScript를 효과적으로 작성한다는 것은 광범위한 브라우저 및 기타 환경에서 동적으로 실행되는 제약 장벽을 깨뜨릴 수 있는 코드를 작성하는 것을 의미합니다. 프로그램을 "효과가 있다"에서 "잘 효과가 있다"로 발전시키려면 많은 복잡하고 세부적인 계획과 노력이 필요합니다.



The *Async & Performance* title is designed to give you all the tools and skills you need to write reasonable and performant JavaScript code.
비동기 및 성능* 타이틀은 합리적이고 성능이 뛰어난 자바스크립트 코드를 작성하는 데 필요한 모든 도구와 기술을 제공하도록 설계되었습니다.

비동기 및 성능 제목은 합리적이고 성능이 뛰어난 JavaScript 코드를 작성하는 데 필요한 모든 도구와 기술을 제공하도록 설계되었습니다.



## ES6 & Beyond

No matter how much you feel you've mastered JavaScript to this point, the truth is that JavaScript is never going to stop evolving, and moreover, the rate of evolution is increasing rapidly. This fact is almost a metaphor for the spirit of this series, to embrace that we'll never fully *know* every part of JS, because as soon as you master it all, there's going to be new stuff coming down the line that you'll need to learn.
지금까지 자바스크립트를 얼마나 마스터했다고 생각하든, 사실 자바스크립트는 진화를 멈추지 않을 것이며, 더욱이 그 진화 속도는 점점 빨라지고 있습니다. 이 사실은 이 시리즈의 정신을 은유적으로 표현한 것으로, JS의 모든 부분을 완전히 '알 수는 없다'는 사실을 받아들이라는 뜻입니다. 왜냐하면 여러분이 모든 것을 마스터하자마자 여러분이 배워야 할 새로운 내용이 등장할 것이기 때문입니다.

지금까지 JavaScript를 얼마나 마스터했다고 생각하더라도 JavaScript는 결코 진화를 멈추지 않을 것이며, 더욱이 진화의 속도가 빠르게 증가하고 있다는 것이 사실입니다. 이 사실은 우리가 JS의 모든 부분을 완전히 알 수는 없다는 점을 포용하는 이 시리즈의 정신에 대한 은유에 가깝습니다. 왜냐하면 JS를 모두 마스터하자마자 새로운 내용이 나올 것이기 때문입니다. 배워야합니다.



This title is dedicated to both the short- and mid-term visions of where the language is headed, not just the *known* stuff like ES6 but the *likely* stuff beyond.
이 책은 ES6와 같은 '알려진' 내용뿐만 아니라 그 이후의 '가능성이 있는' 내용까지, 언어가 나아갈 방향에 대한 단기 및 중기 비전을 모두 다루고 있습니다.

이 제목은 ES6와 같이 알려진 것뿐만 아니라 그 이상의 것 까지 언어가 향하는 단기 및 중기 비전에 전념합니다 .


While all the titles of this series embrace the state of JavaScript at the time of this writing, which is mid-way through ES6 adoption, the primary focus in the series has been more on ES5. Now, we want to turn our attention to ES6, ES7, and ...
이 시리즈의 모든 제목은 ES6 도입의 중간 단계인 이 글을 쓰는 시점의 자바스크립트 상태를 다루고 있지만, 이 시리즈의 주된 초점은 ES5에 더 맞춰져 있습니다. 이제 ES6, ES7으로 관심을 돌리고자 합니다.

이 시리즈의 모든 타이틀은 ES6 채택의 중간 단계인 이 글을 쓰는 시점의 JavaScript 상태를 포함하고 있지만 시리즈의 주요 초점은 ES5에 더 맞춰져 있습니다. 이제 우리는 ES6, ES7 등에 관심을 돌리고 싶습니다.



Since ES6 is nearly complete at the time of this writing, *ES6 & Beyond* starts by dividing up the concrete stuff from the ES6 landscape into several key categories, including new syntax, new data structures (collections), and new processing capabilities and APIs. We cover each of these new ES6 features, in varying levels of detail, including reviewing details that are touched on in other books of this series.
이 글을 쓰는 시점에서 ES6는 거의 완성 단계에 접어들었기 때문에 *ES6 & 그 이후*는 새로운 구문, 새로운 데이터 구조(컬렉션), 새로운 처리 기능 및 API를 포함한 몇 가지 주요 범주로 ES6 환경의 구체적인 내용을 나누는 것으로 시작합니다. 이 시리즈의 다른 책에서 다룬 세부 사항을 검토하는 것을 포함하여 이러한 새로운 ES6 기능 각각을 다양한 수준에서 자세히 다룹니다.

이 글을 쓰는 시점에서 ES6는 거의 완성되었기 때문에 ES6 및 Beyond는 ES6 환경의 구체적인 내용을 새로운 구문, 새로운 데이터 구조(컬렉션), 새로운 처리 기능 및 API를 포함한 여러 주요 범주로 나누는 것부터 시작합니다. 우리는 이 시리즈의 다른 책에서 다룬 세부 사항을 검토하는 것을 포함하여 다양한 수준의 세부 사항으로 이러한 새로운 ES6 기능 각각을 다룹니다.



Some exciting ES6 things to look forward to reading about: destructuring, default parameter values, symbols, concise methods, computed properties, arrow functions, block scoping, promises, generators, iterators, modules, proxies, weakmaps, and much, much more! Phew, ES6 packs quite a punch!
디스트럭스트링, 기본 매개변수 값, 심볼, 간결한 메서드, 계산된 프로퍼티, 화살표 함수, 블록 스코핑, 프로미스, 제너레이터, 이터레이터, 모듈, 프록시, 약지도 등 흥미로운 ES6의 기능에 대해 알아보세요! 휴, ES6는 꽤나 강력한 기능을 담고 있습니다!

읽을 수 있는 ES6의 흥미로운 내용: 구조 분해, 기본 매개변수 값, 기호, 간결한 메서드, 계산된 속성, 화살표 함수, 블록 범위 지정, Promise, 생성기, 반복자, 모듈, 프록시, Weakmap 등 훨씬 더 많은 내용입니다! 휴, ES6는 꽤 강력한 성능을 발휘합니다!



The first part of the book is a roadmap for all the stuff you need to learn to get ready for the new and improved JavaScript you'll be writing and exploring over the next couple of years.
이 책의 첫 번째 부분은 앞으로 몇 년 동안 여러분이 작성하고 탐구하게 될 새롭고 개선된 자바스크립트에 대비하기 위해 배워야 할 모든 내용을 로드맵으로 정리했습니다.

책의 첫 번째 부분은 앞으로 몇 년 동안 작성하고 탐색하게 될 새롭고 향상된 JavaScript에 대비하기 위해 배워야 할 모든 내용에 대한 로드맵입니다.



The latter part of the book turns attention to briefly glance at things that we can likely expect to see in the near future of JavaScript. The most important realization here is that post-ES6, JS is likely going to evolve feature by feature rather than version by version, which means we can expect to see these near-future things coming much sooner than you might imagine.
책의 후반부에서는 가까운 미래에 자바스크립트에서 볼 수 있을 것으로 예상되는 것들을 간략하게 살펴봅니다. 여기서 가장 중요한 점은 ES6 이후에는 JS가 버전별로 발전하기보다는 기능별로 발전할 가능성이 높다는 점이며, 이는 곧 여러분이 상상하는 것보다 훨씬 빨리 이러한 가까운 미래의 모습을 볼 수 있다는 것을 의미합니다.

책의 후반부에서는 JavaScript의 가까운 미래에 우리가 보게 될 것으로 예상되는 것들을 간략하게 살펴보는 데 관심을 돌립니다. 여기서 가장 중요한 깨달음은 ES6 이후 JS가 버전별이 아닌 기능별로 발전할 가능성이 높다는 것입니다. 즉, 이러한 가까운 미래의 일이 여러분이 상상하는 것보다 훨씬 빨리 나타날 것으로 예상할 수 있다는 의미입니다.



The future for JavaScript is bright. Isn't it time we start learning it!?
자바스크립트의 미래는 밝습니다. 이제 자바스크립트를 배울 때가 되지 않았나요?

자바스크립트의 미래는 밝습니다. 이제 본격적으로 배워볼 시간이 되지 않았나요!?




## Review

*YDKJS* 시리즈는 JS 개발자가 이 거대한 언어의 모든 부분을 배울 수 있고, 배워야 한다는 명제에 전념하고 있습니다. 어떤 사람의 의견이나 프레임워크의 가정, 프로젝트의 마감일도 여러분이 자바스크립트를 배우고 깊이 이해하지 못하는 이유에 대한 변명이 되어서는 안 됩니다.

이 책은 언어에서 중점을 두는 각각의 중요한 영역을 다루며, 여러분이 알고 있다고 생각하지만 완전히 알지 못했던 자바스크립트의 모든 부분을 완전히 탐구할 수 있도록 짧지만 밀도 있게 구성했습니다.

"You Don't Know JS(당신은 JS를 모릅니다)"는 비판이나 모욕이 아닙니다. 저를 포함한 우리 모두가 받아들여야 할 깨달음입니다. 자바스크립트를 배우는 것은 최종 목표가 아니라 과정입니다. 우리는 아직 자바스크립트를 모릅니다. 하지만 곧 알게 되겠죠!
