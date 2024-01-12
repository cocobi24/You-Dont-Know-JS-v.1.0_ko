# You Don't Know JS
# 서문

여러분도 알고있으리라 확신지만, 책 시리즈 제목의 "JS"는 자바스크립트를 욕하는데 사용하는 단어의 약어가 아닙니다. 하지만 자바스크립트의 특이한 점들에 대해 저주하는 것은 공감할 수 있을 것 입니다!

웹의 초창기부터 자바스크립트는 우리가 소비하는 콘텐츠를 중심으로 상호 작용하는 경험을 이끌어내는 근본적인 기능이었습니다. 깜빡이는 마우스의 흔적과 성가신 팝업 프롬프트가 자바스크립트의 시작점일지도 모릅니다. 하지만 자바스크립트가 시작된 지난 20년간 자바스크립트의 기술과 능력은 계속해서 성장했고, 오늘날 세계에서 가장 많이 사용되는 소프트웨어 플랫폼인 웹의 핵심에 자리잡게 되었습니다.

하지만 언어로서의 자바스크립트는 지속적으로 많은 비판의 대상이 되어 왔는데, 그러한 이유는 자바스크립트의 전통과 철학 때문입니다. 심지어 자바스크립트라는 이름조차도 브렌단 아이크(Brendan Eich)가 말했듯이, 성숙한 형 "자바" 옆에 "멍청한 동생"이라는 이미지를 떠오르게 합니다. 하지만 이 이름은 단지 정치와 마케팅의 산물일 뿐입니다. 두 언어는 많은 점에서 크게 다릅니다. " *Java* "와 " *Java* script"는 " *Car* "와  " *Car* nival"의 관계와 같이 관련이 없습니다.

자바스크립트는 C 언어 스타일의 절차 지향 뿐만 아니라 미묘하고 명백하지 않은 Scheme/Lisp 스타일의 함수형과 같이 여러 언어의 개념과 문법을 차용했기 때문에, 프로그래밍 경험이 없거나 적은 개발자들도 쉽게 접근할 수 있습니다. 또한, 자바스크립트의 "Hello World"는 매우 간단하여 편안함을 느낄 수 있습니다.

자바스크립트는 아마도 가장 쉽게 시작하고 실행할 수 있는 언어 중 하나이지만, 언어의 별난점으로 인해 다른 언어들에 비해 완전히 마스터하는 일이 훨씬 더 드물다는 결과를 가져옵니다. C나 C++와 같은 언어로 full-scale 프로그램을 작성하기 위해서는 깊은 지식이 필요하지만, 자바스크립트로 프로그램을 작성하는 데에는 표먼적인 지식만 있어도 가능할 수 있습니다.

언어에 깊게 뿌리를 둔 정교한 개념들은 *단순해 보이는* 방식으로 표면화 되는 경향이 있습니다. 함수를 콜백으로 전달하는 것과 같이, 자바스크립트 개발자에게 언어를 있는 그대로 사용하고 내부 동작에 대해 걱정하지 않도록 장려합니다.

이는 동시에 널리 사용되는 간단하고 사용하기 쉬운 언어이면서, 복잡하고 미묘한 언어 메커니즘의 집합이기도 합니다. 주의깊은 공부 없이는 경험이 풍부한 자바스크립트 개발자조차도 *진정한 이해*를 얻기 어려울 수 있습니다.

바로 여기에 자바스크립트의 역설, 아킬레스건, 현재 우리에게 주어진 과제가 있습니다. 자바스크립트는 이해하지 않은 채 *사용할 수* 있기 때문에 언어를 이해하지 못하는 경우가 많습니다.


## Mission

If at every point that you encounter a surprise or frustration in JavaScript, your response is to add it to the blacklist, as some are accustomed to doing, you soon will be relegated to a hollow shell of the richness of JavaScript.

While this subset has been famously dubbed "The Good Parts", I would implore you, dear reader, to instead consider it the "The Easy Parts", "The Safe Parts", or even "The Incomplete Parts".

This *You Don't Know JavaScript* book series offers a contrary challenge: learn and deeply understand *all* of JavaScript, even and especially "The Tough Parts".

Here, we address head on the tendency of JS developers to learn "just enough" to get by, without ever forcing themselves to learn exactly how and why the language behaves the way it does. Furthermore, we eschew the common advice to *retreat* when the road gets rough.

I am not content, nor should you be, at stopping once something *just works*, and not really knowing *why*. I gently challenge you to journey down that bumpy "road less traveled" and embrace all that JavaScript is and can do. With that knowledge, no technique, no framework, no popular buzzword acronym of the week, will be beyond your understanding.

These books each take on specific core parts of the language which are most commonly misunderstood or under-understood, and dive very deep and exhaustively into them. You should come away from reading with a firm confidence in your understanding, not just of the theoretical, but the practical "what you need to know" bits.

The JavaScript you know *right now* is probably *parts* handed down to you by others who've been burned by incomplete understanding. *That* JavaScript is but a shadow of the true language. You don't *really* know JavaScript, *yet*, but if you dig into this series, you *will*. Read on, my friends. JavaScript awaits you.

## Summary

JavaScript is awesome. It's easy to learn partially, and much harder to learn completely (or even *sufficiently*). When developers encounter confusion, they usually blame the language instead of their lack of understanding. These books aim to fix that, inspiring a strong appreciation for the language you can now, and *should*, deeply *know*.

Note: Many of the examples in this book assume modern (and future-reaching) JavaScript engine environments, such as ES6. Some code may not work as described if run in older (pre-ES6) engines.