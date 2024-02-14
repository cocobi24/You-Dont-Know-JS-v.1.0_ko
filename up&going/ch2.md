# You Don't Know JS: Up & Going
# Chapter 2: Into JavaScript
# 2장: 자바스크립트 시작하기

In the previous chapter, I introduced the basic building blocks of programming, such as variables, loops, conditionals, and functions. Of course, all the code shown has been in JavaScript. But in this chapter, we want to focus specifically on things you need to know about JavaScript to get up and going as a JS developer.
이전 장에서는 변수, 루프, 조건부, 함수 등 프로그래밍의 기본 구성 요소를 소개했습니다. 물론 보여드린 모든 코드는 자바스크립트로 작성되었습니다. 하지만 이번 장에서는 JS 개발자가 되기 위해 자바스크립트에 대해 알아야 할 사항들을 집중적으로 다루고자 합니다.

We will introduce quite a few concepts in this chapter that will not be fully explored until subsequent *YDKJS* books. You can think of this chapter as an overview of the topics covered in detail throughout the rest of this series.
이 장에서는 다음 *YDKJS* 책이 나올 때까지 완전히 다루지 않을 개념들을 꽤 많이 소개할 것입니다. 이 장은 이 시리즈의 나머지 부분에서 자세히 다룰 주제에 대한 개요라고 생각하시면 됩니다.

Especially if you're new to JavaScript, you should expect to spend quite a bit of time reviewing the concepts and code examples here multiple times. Any good foundation is laid brick by brick, so don't expect that you'll immediately understand it all the first pass through.
특히 자바스크립트를 처음 접한다면 여기서의 개념과 코드 예제를 여러 번 검토하는 데 상당한 시간이 소요될 것으로 예상해야 합니다. 좋은 기초는 벽돌 한 장 한 장 쌓아가는 것이므로 첫 번째 과정을 통해 모든 것을 바로 이해할 수 있을 거라고 기대하지 마세요.

Your journey to deeply learn JavaScript starts here.
자바스크립트를 깊이 있게 배우기 위한 여정은 여기서부터 시작됩니다.

**Note:** As I said in Chapter 1, you should definitely try all this code yourself as you read and work through this chapter. Be aware that some of the code here assumes capabilities introduced in the newest version of JavaScript at the time of this writing (commonly referred to as "ES6" for the 6th edition of ECMAScript -- the official name of the JS specification). If you happen to be using an older, pre-ES6 browser, the code may not work. A recent update of a modern browser (like Chrome, Firefox, or IE) should be used.
**참고: 1장에서 말했듯이, 이 챕터를 읽으면서 이 모든 코드를 직접 시도해보는 것이 좋습니다. 이 장의 일부 코드는 이 글을 작성할 당시 최신 버전의 자바스크립트(일반적으로 JS 사양의 공식 명칭인 ECMAScript 6판의 경우 "ES6"라고 함)에 도입된 기능을 가정하고 있다는 점에 유의하세요. ES6 이전의 구형 브라우저를 사용하는 경우 코드가 작동하지 않을 수 있습니다. 최신 브라우저(예: Chrome, Firefox, IE)의 최신 업데이트를 사용해야 합니다.

## Values & Types
## 값과 타입

As we asserted in Chapter 1, JavaScript has typed values, not typed variables. The following built-in types are available:
1장에서 살펴본 것처럼 자바스크립트에는 변수가 아닌 값 타입이 있습니다. 다음과 같은 내장 타입을 사용할 수 있습니다:

* `string`
* `number`
* `boolean`
* `null` and `undefined`
* `object`
* `symbol` (new to ES6)

JavaScript provides a `typeof` operator that can examine a value and tell you what type it is:
자바스크립트는 값을 검사하여 어떤 유형인지 알려주는 `typeof` 연산자를 제공합니다:

```js
var a;
typeof a;				// "undefined"

a = "hello world";
typeof a;				// "string"

a = 42;
typeof a;				// "number"

a = true;
typeof a;				// "boolean"

a = null;
typeof a;				// "object" -- weird, bug

a = undefined;
typeof a;				// "undefined"

a = { b: "c" };
typeof a;				// "object"
```

The return value from the `typeof` operator is always one of six (seven as of ES6! - the "symbol" type) string values. That is, `typeof "abc"` returns `"string"`, not `string`.
typeof` 연산자의 반환 값은 항상 6개의(ES6에서는 7개! "기호" 유형) 문자열 값 중 하나입니다. 즉, `typeof "abc"`는 `string`이 아닌 `"string"`을 반환합니다.

Notice how in this snippet the `a` variable holds every different type of value, and that despite appearances, `typeof a` is not asking for the "type of `a`", but rather for the "type of the value currently in `a`." Only values have types in JavaScript; variables are just simple containers for those values.
이 코드 조각에서 `a` 변수가 모든 다른 유형의 값을 보유하고 있으며, 겉보기와 달리 `typeof a`는 "`a`의 유형"을 묻는 것이 아니라 "현재 `a`에 있는 값의 유형"을 묻고 있다는 점에 주목하세요. 자바스크립트에서는 값에만 타입이 있고, 변수는 그 값을 담는 단순한 컨테이너일 뿐입니다.

`typeof null` is an interesting case, because it errantly returns `"object"`, when you'd expect it to return `"null"`.
타입 오브 널`은 흥미로운 경우인데, `"널"`을 반환할 것으로 예상되는 경우 `"객체"`를 잘못 반환하기 때문입니다.

**Warning:** This is a long-standing bug in JS, but one that is likely never going to be fixed. Too much code on the Web relies on the bug and thus fixing it would cause a lot more bugs!
**경고:** 이 문제는 JS의 오랜 버그이지만 앞으로도 고쳐지지 않을 가능성이 높습니다. 웹의 너무 많은 코드가 이 버그에 의존하고 있기 때문에 이 버그를 수정하면 더 많은 버그가 발생할 수 있습니다!

Also, note `a = undefined`. We're explicitly setting `a` to the `undefined` value, but that is behaviorally no different from a variable that has no value set yet, like with the `var a;` line at the top of the snippet. A variable can get to this "undefined" value state in several different ways, including functions that return no values and usage of the `void` operator.
또한 `a = undefined`에 주목하세요. 명시적으로 `a`를 `정의되지 않은` 값으로 설정하고 있지만, 이는 스니펫 상단의 `var a;` 줄과 같이 아직 값이 설정되지 않은 변수와 동작적으로 다르지 않습니다. 변수는 값을 반환하지 않는 함수, `void` 연산자 사용 등 여러 가지 방법으로 이 '정의되지 않은' 값 상태에 도달할 수 있습니다.

### Objects
### 객체

The `object` type refers to a compound value where you can set properties (named locations) that each hold their own values of any type. This is perhaps one of the most useful value types in all of JavaScript.
객체` 유형은 각각 고유한 유형의 값을 보유하는 속성(위치라는 이름의)을 설정할 수 있는 복합 값을 나타냅니다. 이는 아마도 자바스크립트 전체에서 가장 유용한 값 유형 중 하나일 것입니다.

```js
var obj = {
	a: "hello world",
	b: 42,
	c: true
};

obj.a;		// "hello world"
obj.b;		// 42
obj.c;		// true

obj["a"];	// "hello world"
obj["b"];	// 42
obj["c"];	// true
```

It may be helpful to think of this `obj` value visually:
이 `객체` 값을 시각적으로 생각하면 도움이 될 수 있습니다:

<img src="fig4.png">

Properties can either be accessed with *dot notation* (i.e., `obj.a`) or *bracket notation* (i.e., `obj["a"]`). Dot notation is shorter and generally easier to read, and is thus preferred when possible.
속성은 *점 표기법*(예: `obj.a`) 또는 *대괄호 표기법*(예: `obj["a"]`)으로 액세스할 수 있습니다. 점 표기법이 더 짧고 일반적으로 읽기 쉽기 때문에 가능하면 점 표기법을 선호합니다.

Bracket notation is useful if you have a property name that has special characters in it, like `obj["hello world!"]` -- such properties are often referred to as *keys* when accessed via bracket notation. The `[ ]` notation requires either a variable (explained next) or a `string` *literal* (which needs to be wrapped in `" .. "` or `' .. '`).
대괄호 표기법은 `obj["hello world!"]`와 같이 특수 문자가 포함된 속성 이름이 있는 경우 유용하며, 이러한 속성은 대괄호 표기법을 통해 액세스할 때 종종 *키*라고 합니다. '[ ]` 표기법에는 변수(다음에 설명) 또는 '" .. "` 또는 '' .. '`로 감싸야 하는 ` 문자열` *리터럴*이 필요합니다.

Of course, bracket notation is also useful if you want to access a property/key but the name is stored in another variable, such as:
물론 대괄호 표기법은 속성/키에 액세스하고 싶지만 이름이 다른 변수에 저장되어 있는 경우 등에도 유용합니다:

```js
var obj = {
	a: "hello world",
	b: 42
};

var b = "a";

obj[b];			// "hello world"
obj["b"];		// 42
```

**Note:** For more information on JavaScript `object`s, see the *this & Object Prototypes* title of this series, specifically Chapter 3.
**참고:** 자바스크립트 `객체`에 대한 자세한 내용은 이 시리즈의 *이것과 객체 프로토타입* 제목, 특히 3장을 참조하세요.

There are a couple of other value types that you will commonly interact with in JavaScript programs: *array* and *function*. But rather than being proper built-in types, these should be thought of more like subtypes -- specialized versions of the `object` type.
자바스크립트 프로그램에서 일반적으로 상호작용하는 몇 가지 다른 값 유형이 있습니다: *배열*과 *함수*. 하지만 이것들은 제대로 된 내장 타입이라기보다는 '객체' 타입의 특수 버전인 서브타입에 가깝다고 생각해야 합니다.

#### Arrays
#### 배열

An array is an `object` that holds values (of any type) not particularly in named properties/keys, but rather in numerically indexed positions. For example:
배열은 특별히 명명된 속성/키가 아닌 숫자 인덱싱된 위치에 값(모든 유형의 값)을 저장하는 '객체'입니다. 예를 들어

```js
var arr = [
	"hello world",
	42,
	true
];

arr[0];			// "hello world"
arr[1];			// 42
arr[2];			// true
arr.length;		// 3

typeof arr;		// "object"
```

**Note:** Languages that start counting at zero, like JS does, use `0` as the index of the first element in the array.
**참고: JS와 같이 0에서 카운트를 시작하는 언어는 배열의 첫 번째 요소의 인덱스로 `0`을 사용합니다.

It may be helpful to think of `arr` visually:
배열`을 시각적으로 생각하면 도움이 될 수 있습니다:

<img src="fig5.png">

Because arrays are special objects (as `typeof` implies), they can also have properties, including the automatically updated `length` property.
배열은 특수한 객체이기 때문에 (`typeof`에서 알 수 있듯이) 자동으로 업데이트되는 `length` 프로퍼티를 포함한 프로퍼티를 가질 수도 있습니다.

You theoretically could use an array as a normal object with your own named properties, or you could use an `object` but only give it numeric properties (`0`, `1`, etc.) similar to an array. However, this would generally be considered improper usage of the respective types.
이론적으로는 배열을 고유한 이름의 프로퍼티를 가진 일반 객체로 사용할 수도 있고, `객체`를 사용하되 배열과 유사한 숫자 프로퍼티(`0`, `1` 등)만 부여할 수도 있습니다. 그러나 이는 일반적으로 각 유형을 부적절하게 사용하는 것으로 간주됩니다.

The best and most natural approach is to use arrays for numerically positioned values and use `object`s for named properties.
가장 자연스럽고 가장 좋은 방법은 숫자 값에는 배열을 사용하고 명명된 프로퍼티에는 `객체`를 사용하는 것입니다.

#### Functions
#### 함수

The other `object` subtype you'll use all over your JS programs is a function:
JS 프로그램 전체에서 사용하게 될 또 다른 `object` 하위 유형은 함수입니다:

```js
function foo() {
	return 42;
}

foo.bar = "hello world";

typeof foo;			// "function"
typeof foo();		// "number"
typeof foo.bar;		// "string"
```

Again, functions are a subtype of `objects` -- `typeof` returns `"function"`, which implies that a `function` is a main type -- and can thus have properties, but you typically will only use function object properties (like `foo.bar`) in limited cases.
다시 말하지만, 함수는 `객체`의 하위 유형이며, `typeof`는 `함수`가 기본 유형임을 의미하는 `함수`를 반환하므로 프로퍼티를 가질 수 있지만 일반적으로 `foo.bar`와 같은 함수 객체 프로퍼티는 제한된 경우에만 사용할 수 있습니다.

**Note:** For more information on JS values and their types, see the first two chapters of the *Types & Grammar* title of this series.
**참고:** JS 값과 그 유형에 대한 자세한 내용은 이 시리즈의 *유형과 문법* 제목의 처음 두 장을 참조하세요.

### Built-In Type Methods
### 내장 타입 메서드

The built-in types and subtypes we've just discussed have behaviors exposed as properties and methods that are quite powerful and useful.
방금 살펴본 내장 타입과 서브타입은 매우 강력하고 유용한 프로퍼티와 메서드로 노출된 동작을 가지고 있습니다.

For example:
예를 들어

```js
var a = "hello world";
var b = 3.14159;

a.length;				// 11
a.toUpperCase();		// "HELLO WORLD"
b.toFixed(4);			// "3.1416"
```

The "how" behind being able to call `a.toUpperCase()` is more complicated than just that method existing on the value.
대문자 대문자()`를 호출할 수 있는 '방법'은 단순히 값에 존재하는 메서드보다 더 복잡합니다.

Briefly, there is a `String` (capital `S`) object wrapper form, typically called a "native," that pairs with the primitive `string` type; it's this object wrapper that defines the `toUpperCase()` method on its prototype.
간단히 설명하자면, 일반적으로 "네이티브"라고 불리는 `String`(대문자 `S`) 객체 래퍼 형식이 원시 `string` 유형과 짝을 이루며, 이 객체 래퍼가 프로토타입에서 `toUpperCase()` 메서드를 정의합니다.

When you use a primitive value like `"hello world"` as an `object` by referencing a property or method (e.g., `a.toUpperCase()` in the previous snippet), JS automatically "boxes" the value to its object wrapper counterpart (hidden under the covers).
속성이나 메서드(예: 이전 코드 조각의 `a.toUpperCase()`)를 참조하여 `hello world`와 같은 원시 값을 `객체`로 사용하면 JS는 자동으로 해당 값을 객체 래퍼에 해당하는 값으로 "박스 처리"합니다(덮개 아래에 숨겨져 있음).

A `string` value can be wrapped by a `String` object, a `number` can be wrapped by a `Number` object, and a `boolean` can be wrapped by a `Boolean` object. For the most part, you don't need to worry about or directly use these object wrapper forms of the values -- prefer the primitive value forms in practically all cases and JavaScript will take care of the rest for you.
문자열` 값은 `String` 객체로, `숫자`는 `숫자` 객체로, `부울`은 `부울` 객체로 래핑할 수 있습니다. 대부분의 경우 이러한 객체 래퍼 형태의 값에 대해 걱정하거나 직접 사용할 필요는 없습니다. 거의 모든 경우에 원시 값 형식을 선호하며 나머지는 자바스크립트가 알아서 처리합니다.

**Note:** For more information on JS natives and "boxing," see Chapter 3 of the *Types & Grammar* title of this series. To better understand the prototype of an object, see Chapter 5 of the *this & Object Prototypes* title of this series.
**참고:** JS 네이티브와 "복싱"에 대한 자세한 내용은 이 시리즈의 *타입과 문법* 제목의 3장을 참조하세요. 객체의 프로토타입을 더 잘 이해하려면 이 시리즈의 *이것과 객체 프로토타입* 제목의 5장을 참조하세요.

### Comparing Values
### 값 비교

There are two main types of value comparison that you will need to make in your JS programs: *equality* and *inequality*. The result of any comparison is a strictly `boolean` value (`true` or `false`), regardless of what value types are compared.
JS 프로그램에서 수행해야 하는 값 비교에는 크게 두 가지 유형이 있습니다: *동일성*과 *부등식*입니다. 모든 비교의 결과는 비교되는 값 유형에 관계없이 엄격하게 `부울` 값(`true` 또는 `false`)이 됩니다.

#### Coercion
#### 강압

We talked briefly about coercion in Chapter 1, but let's revisit it here.
1장에서 강제성에 대해 간략하게 설명했지만 여기서 다시 한 번 살펴보겠습니다.

Coercion comes in two forms in JavaScript: *explicit* and *implicit*. Explicit coercion is simply that you can see obviously from the code that a conversion from one type to another will occur, whereas implicit coercion is when the type conversion can happen as more of a non-obvious side effect of some other operation.
자바스크립트에서 강제는 두 가지 형태로 존재합니다: *명시적 강제와 암시적 강제입니다. 명시적 강제성은 단순히 코드에서 한 타입에서 다른 타입으로의 변환이 일어날 것이라는 것을 분명히 알 수 있는 반면, 암시적 강제성은 타입 변환이 다른 연산의 명백하지 않은 부작용으로 일어날 수 있는 경우입니다.

You've probably heard sentiments like "coercion is evil" drawn from the fact that there are clearly places where coercion can produce some surprising results. Perhaps nothing evokes frustration from developers more than when the language surprises them.
"강제는 악이다"라는 말을 들어본 적이 있을 것입니다. 강제로 인해 놀라운 결과를 초래할 수 있는 곳이 분명히 존재한다는 사실에서 비롯된 말입니다. 언어가 개발자를 놀라게 할 때만큼 개발자의 좌절감을 불러일으키는 것도 없을 것입니다.

Coercion is not evil, nor does it have to be surprising. In fact, the majority of cases you can construct with type coercion are quite sensible and understandable, and can even be used to *improve* the readability of your code. But we won't go much further into that debate -- Chapter 4 of the *Types & Grammar* title of this series covers all sides.
강압은 악이 아니며 놀라울 필요도 없습니다. 실제로 타입 강제로 구성할 수 있는 대부분의 경우는 상당히 합리적이고 이해하기 쉬우며 코드의 가독성을 *개선*하는 데에도 사용할 수 있습니다. 하지만 이 시리즈의 제목인 *타입과 문법*의 4장에서 모든 측면을 다루기 때문에 더 이상 이 논쟁을 다루지 않겠습니다.

Here's an example of *explicit* coercion:
다음은 *명시적* 강제의 예시입니다:

```js
var a = "42";

var b = Number( a );

a;				// "42"
b;				// 42 -- the number!
```

And here's an example of *implicit* coercion:
다음은 *암묵적인* 강압의 예입니다:

```js
var a = "42";

var b = a * 1;	// "42" implicitly coerced to 42 here

a;				// "42"
b;				// 42 -- the number!
```

#### Truthy & Falsy
#### 진실과 거짓

In Chapter 1, we briefly mentioned the "truthy" and "falsy" nature of values: when a non-`boolean` value is coerced to a `boolean`, does it become `true` or `false`, respectively?
1장에서 우리는 값의 '진실'과 '거짓'에 대해 간략하게 언급했는데, '부울'이 아닌 값을 '부울'로 강제할 때 각각 '참'과 '거짓'이 되는가?

The specific list of "falsy" values in JavaScript is as follows:
자바스크립트에서 "거짓" 값의 구체적인 목록은 다음과 같습니다:

* `""` (empty string)
* `0`, `-0`, `NaN` (invalid `number`)
* `null`, `undefined`
* `false`

Any value that's not on this "falsy" list is "truthy." Here are some examples of those:
이 "허위" 목록에 없는 값은 모두 "진실"입니다. 다음은 그 몇 가지 예입니다:

* `"hello"`
* `42`
* `true`
* `[ ]`, `[ 1, "2", 3 ]` (arrays)
* `{ }`, `{ a: 42 }` (objects)
* `function foo() { .. }` (functions)

It's important to remember that a non-`boolean` value only follows this "truthy"/"falsy" coercion if it's actually coerced to a `boolean`. It's not all that difficult to confuse yourself with a situation that seems like it's coercing a value to a `boolean` when it's not.
부울`이 아닌 값은 실제로 `부울`로 강제될 때만 이 "진실"/ "거짓" 강제를 따른다는 점을 기억하는 것이 중요합니다. 그렇지 않은데도 값을 `부울`로 강제하는 것처럼 보이는 상황을 혼동하는 것은 그리 어렵지 않습니다.

#### Equality
#### 평등

There are four equality operators: `==`, `===`, `!=`, and `!==`. The `!` forms are of course the symmetric "not equal" versions of their counterparts; *non-equality* should not be confused with *inequality*.
등호 연산자는 네 가지가 있습니다: ==`, `===`, `!=`, `!==`. 물론 '!` 형식은 해당 형식의 대칭적인 "같지 않은" 버전입니다; *비등호*를 *불등호*와 혼동해서는 안 됩니다.

The difference between `==` and `===` is usually characterized that `==` checks for value equality and `===` checks for both value and type equality. However, this is inaccurate. The proper way to characterize them is that `==` checks for value equality with coercion allowed, and `===` checks for value equality without allowing coercion; `===` is often called "strict equality" for this reason.
일반적으로 `==`와 `===`의 차이는 `==`는 값의 동일성을 검사하고 `===`는 값과 타입의 동일성을 모두 검사한다는 특징이 있습니다. 그러나 이는 정확하지 않습니다. 올바른 표현은 `==`는 강제가 허용된 상태에서 값의 동일성을 검사하고, `===`는 강제를 허용하지 않고 값의 동일성을 검사하는 것으로, `===`는 이러한 이유로 종종 "엄격한 동일성"이라고 불립니다.

Consider the implicit coercion that's allowed by the `==` loose-equality comparison and not allowed with the `===` strict-equality:
느슨한 평등 비교에서는 허용되고 엄격한 평등 비교에서는 허용되지 않는 암시적 강제를 생각해 보겠습니다:

```js
var a = "42";
var b = 42;

a == b;			// true
a === b;		// false
```

In the `a == b` comparison, JS notices that the types do not match, so it goes through an ordered series of steps to coerce one or both values to a different type until the types match, where then a simple value equality can be checked.
a == b` 비교에서 JS는 타입이 일치하지 않는다는 것을 알아차리고, 타입이 일치할 때까지 하나 또는 두 값을 다른 타입으로 강제하는 일련의 단계를 거쳐 간단한 값 동일성을 확인할 수 있습니다.

If you think about it, there's two possible ways `a == b` could give `true` via coercion. Either the comparison could end up as `42 == 42` or it could be `"42" == "42"`. So which is it?
생각해 보면, `a == b`가 강제를 통해 `참`을 반환할 수 있는 방법은 두 가지가 있습니다. 비교 결과가 `42 == 42`가 될 수도 있고, `"42" == "42"`가 될 수도 있습니다. 그렇다면 어느 쪽일까요?

The answer: `"42"` becomes `42`, to make the comparison `42 == 42`. In such a simple example, it doesn't really seem to matter which way that process goes, as the end result is the same. There are more complex cases where it matters not just what the end result of the comparison is, but *how* you get there.
정답입니다: "42"`는 `42`가 되어 `42 == 42` 비교가 됩니다. 이러한 간단한 예에서는 최종 결과가 동일하기 때문에 어떤 방식으로 처리하는지는 중요하지 않은 것 같습니다. 비교의 최종 결과가 무엇인지는 중요하지 않고, 어떻게 비교에 도달했는지가 더 복잡한 경우가 있습니다.

The `a === b` produces `false`, because the coercion is not allowed, so the simple value comparison obviously fails. Many developers feel that `===` is more predictable, so they advocate always using that form and staying away from `==`. I think this view is very shortsighted. I believe `==` is a powerful tool that helps your program, *if you take the time to learn how it works.*
'a === b'는 강제가 허용되지 않기 때문에 '거짓'을 생성하므로 단순한 값 비교는 분명히 실패합니다. 많은 개발자들은 `===`가 더 예측 가능하다고 생각하기 때문에 항상 이 형식을 사용하고 `==`를 멀리해야 한다고 주장합니다. 저는 이런 관점이 매우 근시안적이라고 생각합니다. 저는 `==`가 *시간을 들여서 어떻게 작동하는지 배운다면 *프로그램에 도움이 되는 강력한 도구라고 생각합니다.

We're not going to cover all the nitty-gritty details of how the coercion in `==` comparisons works here. Much of it is pretty sensible, but there are some important corner cases to be careful of. You can read section 11.9.3 of the ES5 specification (http://www.ecma-international.org/ecma-262/5.1/) to see the exact rules, and you'll be surprised at just how straightforward this mechanism is, compared to all the negative hype surrounding it.
여기서는 `==` 비교의 강제가 어떻게 작동하는지에 대한 핵심적인 내용을 모두 다루지는 않겠습니다. 대부분의 내용은 매우 합리적이지만 주의해야 할 몇 가지 중요한 코너 케이스가 있습니다. ES5 사양의 11.9.3 섹션(http://www.ecma-international.org/ecma-262/5.1/)을 읽어보면 정확한 규칙을 확인할 수 있으며, 이 메커니즘을 둘러싼 모든 부정적인 과대 광고에 비해 이 메커니즘이 얼마나 간단한지 알게 되면 놀랄 것입니다.

To boil down a whole lot of details to a few simple takeaways, and help you know whether to use `==` or `===` in various situations, here are my simple rules:
많은 세부 사항을 몇 가지 간단한 핵심 사항으로 요약하고 다양한 상황에서 `==` 또는 `===`를 사용할지 여부를 파악하는 데 도움이 되는 간단한 규칙은 다음과 같습니다:

* If either value (aka side) in a comparison could be the `true` or `false` value, avoid `==` and use `===`.
* If either value in a comparison could be one of these specific values (`0`, `""`, or `[]` -- empty array), avoid `==` and use `===`.
* In *all* other cases, you're safe to use `==`. Not only is it safe, but in many cases it simplifies your code in a way that improves readability.
* 비교에서 두 값(일명 양쪽)이 모두 `참` 또는 `거짓` 값일 수 있는 경우 `==`를 사용하지 말고 `===`를 사용합니다.
* 비교의 두 값 중 하나가 이러한 특정 값(`0`, `""` 또는 `[]` - 빈 배열)일 수 있는 경우, `==`를 피하고 `===`를 사용합니다.
* 다른 *모든* 경우에는 `==`를 사용해도 안전합니다. 안전할 뿐만 아니라 많은 경우 가독성을 향상시키는 방식으로 코드를 단순화합니다.

What these rules boil down to is requiring you to think critically about your code and about what kinds of values can come through variables that get compared for equality. If you can be certain about the values, and `==` is safe, use it! If you can't be certain about the values, use `===`. It's that simple.
이 규칙의 핵심은 코드에 대해 비판적으로 생각하고 동일성을 비교하는 변수를 통해 어떤 종류의 값이 나올 수 있는지 생각해야 한다는 것입니다. 값에 대해 확신할 수 있고 `==`가 안전하다면 사용하세요! 값을 확신할 수 없다면 `===`를 사용하세요. 그렇게 간단합니다.

The `!=` non-equality form pairs with `==`, and the `!==` form pairs with `===`. All the rules and observations we just discussed hold symmetrically for these non-equality comparisons.
!=` 비등호 형식은 `==`와 짝을 이루고, `!==` 형식은 `===`와 짝을 이룹니다. 방금 설명한 모든 규칙과 관찰 사항은 이러한 비동등 비교에 대칭적으로 적용됩니다.

You should take special note of the `==` and `===` comparison rules if you're comparing two non-primitive values, like `object`s (including `function` and `array`). Because those values are actually held by reference, both `==` and `===` comparisons will simply check whether the references match, not anything about the underlying values.
객체(`함수`와 `배열` 포함)와 같이 원시값이 아닌 두 값을 비교하는 경우 `==`와 `===` 비교 규칙에 특히 유의해야 합니다. 이러한 값은 실제로 참조로 유지되기 때문에 `==`와 `===` 비교는 단순히 참조가 일치하는지 여부만 확인하며, 기본 값에 대해서는 아무 것도 확인하지 않습니다.

For example, `array`s are by default coerced to `string`s by simply joining all the values with commas (`,`) in between. You might think that two `array`s with the same contents would be `==` equal, but they're not:
예를 들어, `array`는 기본적으로 모든 값을 쉼표(`,`)로 연결하여 `string`으로 강제로 변환됩니다. 동일한 내용을 가진 두 개의 `array`가 `==` 같을 것이라고 생각할 수 있지만 그렇지 않습니다:

```js
var a = [1,2,3];
var b = [1,2,3];
var c = "1,2,3";

a == c;		// true
b == c;		// true
a == b;		// false
```

**Note:** For more information about the `==` equality comparison rules, see the ES5 specification (section 11.9.3) and also consult Chapter 4 of the *Types & Grammar* title of this series; see Chapter 2 for more information about values versus references.
**참고: `==` 등호 비교 규칙에 대한 자세한 내용은 ES5 사양(섹션 11.9.3)을 참조하고 이 시리즈의 *유형 및 문법* 제목의 4장을 참조하세요. 값과 참조에 대한 자세한 내용은 2장을 참조하세요.

#### Inequality
#### 부등식

The `<`, `>`, `<=`, and `>=` operators are used for inequality, referred to in the specification as "relational comparison." Typically they will be used with ordinally comparable values like `number`s. It's easy to understand that `3 < 4`.
부등식에는 `<`, `>`, `<=`, `>=` 연산자가 사용되며, 사양에서는 "관계형 비교"라고 부릅니다. 일반적으로 '숫자'와 같이 일반적으로 비교 가능한 값과 함께 사용됩니다. 3 < 4`는 쉽게 이해할 수 있습니다.

But JavaScript `string` values can also be compared for inequality, using typical alphabetic rules (`"bar" < "foo"`).
하지만 자바스크립트 ` 문자열` 값은 일반적인 알파벳 규칙(`"bar" < "foo"`)을 사용하여 부등식 비교도 가능합니다.

What about coercion? Similar rules as `==` comparison (though not exactly identical!) apply to the inequality operators. Notably, there are no "strict inequality" operators that would disallow coercion the same way `===` "strict equality" does.
강제는 어떨까요? 부등식 연산자에도 `==` 비교와 비슷한 규칙(정확히 동일하지는 않지만!)이 적용됩니다. 특히, `===` "엄격 부등식"과 같은 방식으로 강제를 허용하지 않는 "엄격 부등식" 연산자는 없습니다.

Consider:
생각해 봅시다:

```js
var a = 41;
var b = "42";
var c = "43";

a < b;		// true
b < c;		// true
```

What happens here? In section 11.8.5 of the ES5 specification, it says that if both values in the `<` comparison are `string`s, as it is with `b < c`, the comparison is made lexicographically (aka alphabetically like a dictionary). But if one or both is not a `string`, as it is with `a < b`, then both values are coerced to be `number`s, and a typical numeric comparison occurs.
여기서 무슨 일이 일어날까요? ES5 사양의 섹션 11.8.5에 따르면 `<` 비교의 두 값이 모두 `` 문자열``인 경우 `b <c`와 마찬가지로 사전적으로(사전처럼 알파벳순으로) 비교가 이루어집니다. 그러나 'a < b'와 같이 둘 중 하나 또는 둘 다 '문자열'이 아닌 경우 두 값이 모두 '숫자'가 되어야 하며, 일반적인 숫자 비교가 이루어집니다.

The biggest gotcha you may run into here with comparisons between potentially different value types -- remember, there are no "strict inequality" forms to use -- is when one of the values cannot be made into a valid number, such as:
잠재적으로 다른 값 유형 간의 비교에서 가장 큰 어려움은 다음과 같이 값 중 하나를 유효한 숫자로 만들 수 없는 경우입니다(사용할 "엄격한 부등식" 형식은 없다는 점을 기억하세요):

```js
var a = 42;
var b = "foo";

a < b;		// false
a > b;		// false
a == b;		// false
```

Wait, how can all three of those comparisons be `false`? Because the `b` value is being coerced to the "invalid number value" `NaN` in the `<` and `>` comparisons, and the specification says that `NaN` is neither greater-than nor less-than any other value.
잠깐만요, 어떻게 이 세 가지 비교가 모두 '거짓'일 수 있을까요? 왜냐하면 `<`와 `>` 비교에서 `b` 값이 "잘못된 숫자 값"인 `NaN`으로 강제되고 있고, 사양에 따르면 `NaN`은 다른 값보다 크지도 작지도 않다고 명시되어 있기 때문입니다.

The `==` comparison fails for a different reason. `a == b` could fail if it's interpreted either as `42 == NaN` or `"42" == "foo"` -- as we explained earlier, the former is the case.
다른 이유로 `==` 비교가 실패합니다. a == b`가 `42 == NaN` 또는 `"42" == "foo"`로 해석되는 경우 실패할 수 있는데, 앞서 설명한 것처럼 전자의 경우입니다.

**Note:** For more information about the inequality comparison rules, see section 11.8.5 of the ES5 specification and also consult Chapter 4 of the *Types & Grammar* title of this series.
**참고: 부등식 비교 규칙에 대한 자세한 내용은 ES5 사양의 11.8.5 절을 참조하고, 이 시리즈의 *타입과 문법* 4장을 참고하세요.

## Variables
## 변수

In JavaScript, variable names (including function names) must be valid *identifiers*. The strict and complete rules for valid characters in identifiers are a little complex when you consider nontraditional characters such as Unicode. If you only consider typical ASCII alphanumeric characters though, the rules are simple.
자바스크립트에서 변수 이름(함수 이름 포함)은 유효한 *식별자*여야 합니다. 식별자의 유효한 문자에 대한 엄격하고 완전한 규칙은 유니코드와 같은 비표준 문자를 고려할 때 약간 복잡합니다. 하지만 일반적인 ASCII 영숫자 문자만 고려한다면 규칙은 간단합니다.

An identifier must start with `a`-`z`, `A`-`Z`, `$`, or `_`. It can then contain any of those characters plus the numerals `0`-`9`.
식별자는 `a`-`z`, `A`-`Z`, `$` 또는 `_`로 시작해야 합니다. 그런 다음 이러한 문자와 숫자 `0`-`9`를 포함할 수 있습니다.

Generally, the same rules apply to a property name as to a variable identifier. However, certain words cannot be used as variables, but are OK as property names. These words are called "reserved words," and include the JS keywords (`for`, `in`, `if`, etc.) as well as `null`, `true`, and `false`.
일반적으로 변수 식별자와 동일한 규칙이 속성 이름에도 적용됩니다. 그러나 특정 단어는 변수로 사용할 수 없지만 속성 이름으로는 사용할 수 있습니다. 이러한 단어를 "예약어"라고 하며, JS 키워드(`for`, `in`, `if` 등)와 `null`, `true`, `false`가 여기에 포함됩니다.

**Note:** For more information about reserved words, see Appendix A of the *Types & Grammar* title of this series.
**참고: **예약어에 대한 자세한 내용은 이 시리즈의 *유형 및 문법* 제목의 부록 A를 참조하세요.

### Function Scopes
### 함수 범위

You use the `var` keyword to declare a variable that will belong to the current function scope, or the global scope if at the top level outside of any function.
변수` 키워드를 사용하여 현재 함수 범위 또는 함수 외부의 최상위 레벨에 있는 경우 전역 범위에 속할 변수를 선언합니다.

#### Hoisting
#### 호이스팅

Wherever a `var` appears inside a scope, that declaration is taken to belong to the entire scope and accessible everywhere throughout.
스코프 내에 `var`가 나타날 때마다 해당 선언은 전체 스코프에 속하는 것으로 간주되어 전체 범위에서 어디서나 액세스할 수 있습니다.

Metaphorically, this behavior is called *hoisting*, when a `var` declaration is conceptually "moved" to the top of its enclosing scope. Technically, this process is more accurately explained by how code is compiled, but we can skip over those details for now.
은유적으로 이 동작을 *호이스팅*이라고 하는데, `var` 선언을 개념적으로 둘러싸고 있는 범위의 맨 위로 "이동"시키는 것입니다. 기술적으로 이 프로세스는 코드가 컴파일되는 방식으로 더 정확하게 설명할 수 있지만 지금은 자세한 설명은 생략하겠습니다.

Consider:
생각해 봅시다:

```js
var a = 2;

foo();					// works because `foo()`
						// declaration is "hoisted"

function foo() {
	a = 3;

	console.log( a );	// 3

	var a;				// declaration is "hoisted"
						// to the top of `foo()`
}

console.log( a );	// 2
```

**Warning:** It's not common or a good idea to rely on variable *hoisting* to use a variable earlier in its scope than its `var` declaration appears; it can be quite confusing. It's much more common and accepted to use *hoisted* function declarations, as we do with the `foo()` call appearing before its formal declaration.
**경고:** `var` 선언이 나타나기 전 범위에서 변수를 사용하기 위해 *호이스트* 변수에 의존하는 것은 일반적이지도 않고 좋은 생각도 아니며, 상당히 혼란스러울 수 있습니다. 공식 선언 앞에 `foo()` 호출이 나타나는 것처럼 *호이스트* 함수 선언을 사용하는 것이 훨씬 더 일반적이고 허용됩니다.

#### Nested Scopes
#### 중첩 범위

When you declare a variable, it is available anywhere in that scope, as well as any lower/inner scopes. For example:
변수를 선언하면 해당 변수는 하위/내부 범위뿐만 아니라 해당 범위의 모든 곳에서 사용할 수 있습니다. 예를 들어

```js
function foo() {
	var a = 1;

	function bar() {
		var b = 2;

		function baz() {
			var c = 3;

			console.log( a, b, c );	// 1 2 3
		}

		baz();
		console.log( a, b );		// 1 2
	}

	bar();
	console.log( a );				// 1
}

foo();
```

Notice that `c` is not available inside of `bar()`, because it's declared only inside the inner `baz()` scope, and that `b` is not available to `foo()` for the same reason.
c`는 내부 `baz()` 범위 내에서만 선언되기 때문에 `bar()` 내부에서 사용할 수 없으며, `b`도 같은 이유로 `foo()`에서 사용할 수 없다는 점에 유의하세요.

If you try to access a variable's value in a scope where it's not available, you'll get a `ReferenceError` thrown. If you try to set a variable that hasn't been declared, you'll either end up creating a variable in the top-level global scope (bad!) or getting an error, depending on "strict mode" (see "Strict Mode"). Let's take a look:
사용할 수 없는 범위에서 변수 값에 액세스하려고 하면 `ReferenceError`가 발생합니다. 선언되지 않은 변수를 설정하려고 하면 최상위 전역 범위에서 변수를 만들거나('나쁜'!), '엄격한 모드'에 따라 오류가 발생합니다('엄격한 모드' 참조). 한 번 살펴보겠습니다:

```js
function foo() {
	a = 1;	// `a` not formally declared
}

foo();
a;			// 1 -- oops, auto global variable :(
```

This is a very bad practice. Don't do it! Always formally declare your variables.
이는 매우 나쁜 습관입니다. 하지 마세요! 항상 변수를 공식적으로 선언하세요.

In addition to creating declarations for variables at the function level, ES6 *lets* you declare variables to belong to individual blocks (pairs of `{ .. }`), using the `let` keyword. Besides some nuanced details, the scoping rules will behave roughly the same as we just saw with functions:
함수 수준에서 변수에 대한 선언을 생성하는 것 외에도, ES6에서는 `let` 키워드를 사용하여 변수를 개별 블록(`{ .. }` 쌍)에 속하도록 선언할 수 있습니다. 약간의 미묘한 차이를 제외하면 범위 지정 규칙은 방금 살펴본 함수에서와 거의 동일하게 작동합니다:

```js
function foo() {
	var a = 1;

	if (a >= 1) {
		let b = 2;

		while (b < 5) {
			let c = b * 2;
			b++;

			console.log( a + c );
		}
	}
}

foo();
// 5 7 9
```

Because of using `let` instead of `var`, `b` will belong only to the `if` statement and thus not to the whole `foo()` function's scope. Similarly, `c` belongs only to the `while` loop. Block scoping is very useful for managing your variable scopes in a more fine-grained fashion, which can make your code much easier to maintain over time.
var` 대신 `let`을 사용했기 때문에 `b`는 `if` 문에만 속하며 전체 `foo()` 함수의 범위에는 속하지 않습니다. 마찬가지로 `c`는 `while` 루프에만 속합니다. 블록 범위 지정은 변수 범위를 보다 세밀하게 관리할 때 매우 유용하며, 시간이 지남에 따라 코드를 훨씬 쉽게 유지 관리할 수 있습니다.

**Note:** For more information about scope, see the *Scope & Closures* title of this series. See the *ES6 & Beyond* title of this series for more information about `let` block scoping.
**참고: 범위와 관련된 자세한 내용은 이 시리즈의 *범위 및 클로저* 제목을 참조하세요. 'let' 블록 범위 지정에 대한 자세한 내용은 이 시리즈의 *ES6 및 그 이후* 제목을 참조하세요.

## Conditionals
## 조건문

In addition to the `if` statement we introduced briefly in Chapter 1, JavaScript provides a few other conditionals mechanisms that we should take a look at.
1장에서 간략하게 소개한 `if` 문 외에도 자바스크립트에는 살펴봐야 할 몇 가지 다른 조건문 메커니즘이 있습니다.

Sometimes you may find yourself writing a series of `if..else..if` statements like this:
때때로 다음과 같은 일련의 `if..else..if` 문을 작성하게 될 수도 있습니다:

```js
if (a == 2) {
	// do something
}
else if (a == 10) {
	// do another thing
}
else if (a == 42) {
	// do yet another thing
}
else {
	// fallback to here
}
```

This structure works, but it's a little verbose because you need to specify the `a` test for each case. Here's another option, the `switch` statement:
이 구조는 작동하지만 각 경우에 대해 `a` 테스트를 지정해야 하므로 약간 장황합니다. 또 다른 옵션인 `switch` 문이 있습니다:

```js
switch (a) {
	case 2:
		// do something
		break;
	case 10:
		// do another thing
		break;
	case 42:
		// do yet another thing
		break;
	default:
		// fallback to here
}
```

The `break` is important if you want only the statement(s) in one `case` to run. If you omit `break` from a `case`, and that `case` matches or runs, execution will continue with the next `case`'s statements regardless of that `case` matching. This so called "fall through" is sometimes useful/desired:
하나의 `case`에 있는 문만 실행하려면 `break`가 중요합니다. 만약 `case`에서 `break`를 생략했는데 그 `case`가 일치하거나 실행되면, 그 `case`의 일치 여부와 상관없이 다음 `case`의 문이 계속 실행됩니다. 소위 "폴 스루"라고 불리는 이 기능은 때때로 유용하거나 바람직합니다:

```js
switch (a) {
	case 2:
	case 10:
		// some cool stuff
		break;
	case 42:
		// other stuff
		break;
	default:
		// fallback
}
```

Here, if `a` is either `2` or `10`, it will execute the "some cool stuff" code statements.
여기서 `a`가 `2` 또는 `10`이면 "some cool stuff" 코드문이 실행됩니다.

Another form of conditional in JavaScript is the "conditional operator," often called the "ternary operator." It's like a more concise form of a single `if..else` statement, such as:
자바스크립트에서 조건의 또 다른 형태는 흔히 "삼항 연산자"라고 불리는 "조건 연산자"입니다. 이는 단일 `if..else` 문을 좀 더 간결하게 표현한 형태입니다:

```js
var a = 42;

var b = (a > 41) ? "hello" : "world";

// similar to:

// if (a > 41) {
//    b = "hello";
// }
// else {
//    b = "world";
// }
```

If the test expression (`a > 41` here) evaluates as `true`, the first clause (`"hello"`) results, otherwise the second clause (`"world"`) results, and whatever the result is then gets assigned to `b`.
테스트 표현식(여기서는 `a > 41`)이 `true`로 평가되면 첫 번째 절("hello"`)의 결과가 나오고, 그렇지 않으면 두 번째 절("world"`)의 결과가 나오며, 어떤 결과가 나오든 `b`에 할당됩니다.

The conditional operator doesn't have to be used in an assignment, but that's definitely the most common usage.
조건부 연산자를 할당에 사용할 필요는 없지만, 가장 일반적으로 사용되는 방법입니다.

**Note:** For more information about testing conditions and other patterns for `switch` and `? :`, see the *Types & Grammar* title of this series.
**참고: `switch` 및 `? :`에 대한 테스트 조건 및 기타 패턴에 대한 자세한 내용은 이 시리즈의 *유형 및 문법* 제목을 참조하세요.

## Strict Mode
## 엄격 모드

ES5 added a "strict mode" to the language, which tightens the rules for certain behaviors. Generally, these restrictions are seen as keeping the code to a safer and more appropriate set of guidelines. Also, adhering to strict mode makes your code generally more optimizable by the engine. Strict mode is a big win for code, and you should use it for all your programs.
ES5는 특정 동작에 대한 규칙을 강화하는 '엄격한 모드'를 언어에 추가했습니다. 일반적으로 이러한 제한은 코드를 보다 안전하고 적절한 지침에 따라 유지하는 것으로 간주됩니다. 또한 엄격 모드를 준수하면 일반적으로 엔진에서 코드를 더 잘 최적화할 수 있습니다. 엄격 모드는 코드에 큰 도움이 되므로 모든 프로그램에 엄격 모드를 사용해야 합니다.

You can opt in to strict mode for an individual function, or an entire file, depending on where you put the strict mode pragma:
엄격 모드 원칙을 어디에 두느냐에 따라 개별 함수 또는 전체 파일에 대해 엄격 모드를 선택할 수 있습니다:

```js
function foo() {
	"use strict";

	// this code is strict mode

	function bar() {
		// this code is strict mode
	}
}

// this code is not strict mode
```

Compare that to:
다음과 비교해보세요:

```js
"use strict";

function foo() {
	// this code is strict mode

	function bar() {
		// this code is strict mode
	}
}

// this code is strict mode
```

One key difference (improvement!) with strict mode is disallowing the implicit auto-global variable declaration from omitting the `var`:
엄격 모드와의 주요 차이점(개선 사항!) 중 하나는 암시적 자동 전역 변수 선언에서 `var` 생략을 허용하지 않는다는 점입니다:

```js
function foo() {
	"use strict";	// turn on strict mode
	a = 1;			// `var` missing, ReferenceError
}

foo();
```

If you turn on strict mode in your code, and you get errors, or code starts behaving buggy, your temptation might be to avoid strict mode. But that instinct would be a bad idea to indulge. If strict mode causes issues in your program, almost certainly it's a sign that you have things in your program you should fix.
코드에서 엄격 모드를 켰는데 오류가 발생하거나 코드가 버그가 발생하기 시작하면 엄격 모드를 피하고 싶은 유혹에 빠질 수 있습니다. 하지만 그런 본능에 빠지는 것은 좋지 않습니다. 엄격 모드로 인해 프로그램에서 문제가 발생한다면 프로그램에 수정해야 할 사항이 있다는 신호일 가능성이 높습니다.

Not only will strict mode keep your code to a safer path, and not only will it make your code more optimizable, but it also represents the future direction of the language. It'd be easier on you to get used to strict mode now than to keep putting it off -- it'll only get harder to convert later!
엄격 모드는 코드를 더 안전한 경로로 유지하고 코드를 더 최적화할 수 있을 뿐만 아니라 언어의 미래 방향을 제시하기도 합니다. 엄격 모드를 계속 미루는 것보다 지금 바로 엄격 모드에 익숙해지는 것이 나중에 변환하기가 더 쉬울 것입니다!

**Note:** For more information about strict mode, see the Chapter 5 of the *Types & Grammar* title of this series.
**참고: 엄격 모드에 대한 자세한 내용은 이 시리즈의 *유형 및 문법* 5장을 참조하세요.

## Functions As Values
## 값으로서의 함수

So far, we've discussed functions as the primary mechanism of *scope* in JavaScript. You recall typical `function` declaration syntax as follows:
지금까지 자바스크립트에서 *범위*의 주요 메커니즘으로서 함수에 대해 알아보았습니다. 일반적인 `함수` 선언 구문은 다음과 같습니다:

```js
function foo() {
	// ..
}
```

Though it may not seem obvious from that syntax, `foo` is basically just a variable in the outer enclosing scope that's given a reference to the `function` being declared. That is, the `function` itself is a value, just like `42` or `[1,2,3]` would be.
이 구문에서는 명확하게 보이지 않을 수 있지만, `foo`는 기본적으로 선언되는 `함수`에 대한 참조가 주어진 바깥쪽 범위의 변수일 뿐입니다. 즉, `42`나 `[1,2,3]`처럼 `함수` 자체가 값인 것입니다.

This may sound like a strange concept at first, so take a moment to ponder it. Not only can you pass a value (argument) *to* a function, but *a function itself can be a value* that's assigned to variables, or passed to or returned from other functions.
처음에는 생소한 개념처럼 들릴 수 있으니 잠시 시간을 두고 생각해 보세요. 값(인수)을 함수에 *전달할 수 있을 뿐만 아니라, *함수 자체가 변수에 할당되거나 다른 함수에 전달되거나 다른 함수에서 반환되는 값*이 될 수 있습니다.

As such, a function value should be thought of as an expression, much like any other value or expression.
따라서 함수 값은 다른 값이나 표현식과 마찬가지로 표현식으로 생각해야 합니다.

Consider:
생각해 보세요:

```js
var foo = function() {
	// ..
};

var x = function bar(){
	// ..
};
```

The first function expression assigned to the `foo` variable is called *anonymous* because it has no `name`.
foo` 변수에 할당된 첫 번째 함수 표현식은 `이름`이 없으므로 *anonymous*라고 합니다.

The second function expression is *named* (`bar`), even as a reference to it is also assigned to the `x` variable. *Named function expressions* are generally more preferable, though *anonymous function expressions* are still extremely common.
두 번째 함수 표현식은 참조가 `x` 변수에 할당되어 있더라도 *명명된*(`bar`) 함수 표현식입니다. 일반적으로 *명명된 함수 표현식*이 더 선호되지만 *익명 함수 표현식*도 여전히 매우 일반적입니다.

For more information, see the *Scope & Closures* title of this series.
자세한 내용은 이 시리즈의 *범위 및 클로저* 제목을 참조하세요.

### Immediately Invoked Function Expressions (IIFEs)
### 즉시 호출 함수 표현식(IIFE)

In the previous snippet, neither of the function expressions are executed -- we could if we had included `foo()` or `x()`, for instance.
앞의 코드 조각에서는 두 함수 표현식 중 어느 것도 실행되지 않았습니다. 예를 들어 `foo()` 또는 `x()`를 포함했다면 실행할 수 있었을 것입니다.

There's another way to execute a function expression, which is typically referred to as an *immediately invoked function expression* (IIFE):
함수 표현식을 실행하는 또 다른 방법이 있는데, 이를 일반적으로 *즉시 호출된 함수 표현식*(IIFE)이라고 합니다:

```js
(function IIFE(){
	console.log( "Hello!" );
})();
// "Hello!"
```

The outer `( .. )` that surrounds the `(function IIFE(){ .. })` function expression is just a nuance of JS grammar needed to prevent it from being treated as a normal function declaration.
함수 표현식을 둘러싸고 있는 바깥쪽 `( .. )`은 `(함수 IIFE(){ .. })` 함수 표현식은 일반적인 함수 선언으로 취급되지 않도록 하기 위해 필요한 JS 문법의 뉘앙스일 뿐입니다.

The final `()` on the end of the expression -- the `})();` line -- is what actually executes the function expression referenced immediately before it.
표현식 끝에 있는 마지막 `()`, 즉 `})();` 줄은 바로 앞에 참조된 함수 표현식을 실제로 실행하는 것입니다.

That may seem strange, but it's not as foreign as first glance. Consider the similarities between `foo` and `IIFE` here:
이상하게 보일 수 있지만 언뜻 보기에는 그렇게 낯설지 않습니다. 여기서 `foo`와 `IIFE`의 유사점을 생각해 보세요:

```js
function foo() { .. }

// `foo` function reference expression,
// then `()` executes it
foo();

// `IIFE` function expression,
// then `()` executes it
(function IIFE(){ .. })();
```

As you can see, listing the `(function IIFE(){ .. })` before its executing `()` is essentially the same as including `foo` before its executing `()`; in both cases, the function reference is executed with `()` immediately after it.
보시다시피, 실행하는 `()` 앞에 `(함수 IIFE(){ .. })`를 실행하는 '()` 앞에 나열하는 것은 '()`를 실행하는 '()` 앞에 `foo`를 포함하는 것과 본질적으로 동일하며, 두 경우 모두 함수 참조는 바로 뒤에 '()`와 함께 실행됩니다.

Because an IIFE is just a function, and functions create variable *scope*, using an IIFE in this fashion is often used to declare variables that won't affect the surrounding code outside the IIFE:
IIFE는 단지 함수일 뿐이고 함수는 *범위* 변수를 생성하기 때문에, 이러한 방식으로 IIFE를 사용하는 것은 종종 IIFE 외부의 주변 코드에 영향을 주지 않는 변수를 선언하는 데 사용됩니다:

```js
var a = 42;

(function IIFE(){
	var a = 10;
	console.log( a );	// 10
})();

console.log( a );		// 42
```

IIFEs can also have return values:

```js
var x = (function IIFE(){
	return 42;
})();

x;	// 42
```

The `42` value gets `return`ed from the `IIFE`-named function being executed, and is then assigned to `x`.
42` 값은 실행 중인 `IIFE`라는 이름의 함수에서 `리턴`된 후 `x`에 할당됩니다.

### Closure
### 클로저

*Closure* is one of the most important, and often least understood, concepts in JavaScript. I won't cover it in deep detail here, and instead refer you to the *Scope & Closures* title of this series. But I want to say a few things about it so you understand the general concept. It will be one of the most important techniques in your JS skillset.
*클로저*는 자바스크립트에서 가장 중요하지만 가장 잘 이해되지 않는 개념 중 하나입니다. 여기서는 자세히 다루지 않고 대신 이 시리즈의 제목인 *범위와 클로저*를 참고하시기 바랍니다. 하지만 일반적인 개념을 이해할 수 있도록 몇 가지 말씀드리고 싶습니다. 이것은 JS 스킬셋에서 가장 중요한 기술 중 하나가 될 것입니다.

You can think of closure as a way to "remember" and continue to access a function's scope (its variables) even once the function has finished running.
클로저는 함수의 실행이 끝난 후에도 함수의 범위(변수)를 "기억"하고 계속 액세스하는 방법이라고 생각할 수 있습니다.

Consider:
생각해 보세요:

```js
function makeAdder(x) {
	// parameter `x` is an inner variable

	// inner function `add()` uses `x`, so
	// it has a "closure" over it
	function add(y) {
		return y + x;
	};

	return add;
}
```

The reference to the inner `add(..)` function that gets returned with each call to the outer `makeAdder(..)` is able to remember whatever `x` value was passed in to `makeAdder(..)`. Now, let's use `makeAdder(..)`:
외부 `makeAdder(..)`를 호출할 때마다 반환되는 내부 `add(..)` 함수에 대한 참조는 `makeAdder(..)`에 전달된 `x` 값이 무엇이든 기억할 수 있습니다. 이제 `makeAdder(..)`를 사용해 봅시다:

```js
// `plusOne` gets a reference to the inner `add(..)`
// function with closure over the `x` parameter of
// the outer `makeAdder(..)`
var plusOne = makeAdder( 1 );

// `plusTen` gets a reference to the inner `add(..)`
// function with closure over the `x` parameter of
// the outer `makeAdder(..)`
var plusTen = makeAdder( 10 );

plusOne( 3 );		// 4  <-- 1 + 3
plusOne( 41 );		// 42 <-- 1 + 41

plusTen( 13 );		// 23 <-- 10 + 13
```

More on how this code works:
이 코드의 작동 방식에 대해 자세히 알아보세요:

1. When we call `makeAdder(1)`, we get back a reference to its inner `add(..)` that remembers `x` as `1`. We call this function reference `plusOne(..)`.
2. When we call `makeAdder(10)`, we get back another reference to its inner `add(..)` that remembers `x` as `10`. We call this function reference `plusTen(..)`.
3. When we call `plusOne(3)`, it adds `3` (its inner `y`) to the `1` (remembered by `x`), and we get `4` as the result.
4. When we call `plusTen(13)`, it adds `13` (its inner `y`) to the `10` (remembered by `x`), and we get `23` as the result.
1. makeAdder(1)`를 호출하면 `x`를 `1`로 기억하는 내부 `add(..)`에 대한 참조를 다시 가져옵니다. 이 함수 참조를 `plusOne(..)`이라고 부릅니다.
2. makeAdder(10)`를 호출하면 `x`를 `10`으로 기억하는 내부 `add(..)`에 대한 또 다른 참조를 다시 가져옵니다. 이 함수 참조를 `plusTen(..)`이라고 부릅니다.
3. 플러스원(3)`을 호출하면 `x`가 기억하는 `1`에 `3`(내부 `y`)을 더하고, 그 결과로 `4`를 얻습니다.
4. 플러스텐(13)`을 호출하면 `10`(`x`가 기억)에 `13`(내부 `y`)을 더하고, 그 결과로 `23`을 얻습니다.

Don't worry if this seems strange and confusing at first -- it can be! It'll take lots of practice to understand it fully.
처음에는 이상하고 혼란스러워 보이더라도 걱정하지 마세요! 완전히 이해하려면 많은 연습이 필요합니다.

But trust me, once you do, it's one of the most powerful and useful techniques in all of programming. It's definitely worth the effort to let your brain simmer on closures for a bit. In the next section, we'll get a little more practice with closure.
하지만 일단 이해하게 되면 모든 프로그래밍에서 가장 강력하고 유용한 기법 중 하나라고 믿으세요. 클로저에 대해 잠시 머릿속을 끓여보는 것도 충분히 가치가 있습니다. 다음 섹션에서는 클로저에 대해 조금 더 연습해 보겠습니다.

#### Modules
#### 모듈

The most common usage of closure in JavaScript is the module pattern. Modules let you define private implementation details (variables, functions) that are hidden from the outside world, as well as a public API that *is* accessible from the outside.
자바스크립트에서 클로저의 가장 일반적인 사용법은 모듈 패턴입니다. 모듈을 사용하면 외부에서 볼 수 없는 비공개 구현 세부 사항(변수, 함수)을 정의할 수 있을 뿐만 아니라 외부에서 액세스할 수 있는 공개 API도 정의할 수 있습니다.

Consider:
생각해 보세요:

```js
function User(){
	var username, password;

	function doLogin(user,pw) {
		username = user;
		password = pw;

		// do the rest of the login work
	}

	var publicAPI = {
		login: doLogin
	};

	return publicAPI;
}

// create a `User` module instance
var fred = User();

fred.login( "fred", "12Battery34!" );
```

The `User()` function serves as an outer scope that holds the variables `username` and `password`, as well as the inner `doLogin()` function; these are all private inner details of this `User` module that cannot be accessed from the outside world.
User()` 함수는 `username`과 `password` 변수를 보관하는 외부 스코프와 내부 `doLogin()` 함수의 역할을 하며, 이들은 모두 외부에서 접근할 수 없는 이 `User` 모듈의 비공개 내부 세부 정보입니다.

**Warning:** We are not calling `new User()` here, on purpose, despite the fact that probably seems more common to most readers. `User()` is just a function, not a class to be instantiated, so it's just called normally. Using `new` would be inappropriate and actually waste resources.
**경고:** 대부분의 독자에게는 더 일반적인 것처럼 보이지만 여기서는 일부러 `new User()`를 호출하지 않습니다. User()`는 인스턴스화할 클래스가 아닌 함수일 뿐이므로 그냥 정상적으로 호출됩니다. new`를 사용하는 것은 부적절하며 실제로 리소스를 낭비할 수 있습니다.

Executing `User()` creates an *instance* of the `User` module -- a whole new scope is created, and thus a whole new copy of each of these inner variables/functions. We assign this instance to `fred`. If we run `User()` again, we'd get a new instance entirely separate from `fred`.
User()`를 실행하면 `User` 모듈의 *인스턴스*가 생성되며, 완전히 새로운 범위가 생성되고 따라서 각 내부 변수/함수의 복사본도 완전히 새로 만들어집니다. 이 인스턴스를 `fred`에 할당합니다. User()`를 다시 실행하면 `fred`와는 완전히 분리된 새로운 인스턴스를 얻게 됩니다.

The inner `doLogin()` function has a closure over `username` and `password`, meaning it will retain its access to them even after the `User()` function finishes running.
내부 `doLogin()` 함수는 `사용자 이름`과 `비밀번호`에 대한 클로저를 가지고 있으므로 `사용자()` 함수의 실행이 완료된 후에도 이들에 대한 접근 권한을 유지합니다.

`publicAPI` is an object with one property/method on it, `login`, which is a reference to the inner `doLogin()` function. When we return `publicAPI` from `User()`, it becomes the instance we call `fred`.
publicAPI`는 하나의 속성/메서드가 있는 객체로, 내부 `doLogin()` 함수에 대한 참조인 `login`이 있습니다. User()`에서 `publicAPI`를 반환하면 `fred`라고 부르는 인스턴스가 됩니다.

At this point, the outer `User()` function has finished executing. Normally, you'd think the inner variables like `username` and `password` have gone away. But here they have not, because there's a closure in the `login()` function keeping them alive.
이 시점에서 외부 `User()` 함수의 실행이 완료되었습니다. 일반적으로 `username`과 `password` 같은 내부 변수가 사라졌다고 생각할 수 있습니다. 하지만 여기서는 그렇지 않습니다. 왜냐하면 `login()` 함수에 클로저가 있기 때문입니다.

That's why we can call `fred.login(..)` -- the same as calling the inner `doLogin(..)` -- and it can still access `username` and `password` inner variables.
그렇기 때문에 `fred.login(..)`을 호출해도 내부 `doLogin(..)`을 호출하는 것과 동일하게 `username` 및 `password` 내부 변수에 액세스할 수 있습니다.

There's a good chance that with just this brief glimpse at closure and the module pattern, some of it is still a bit confusing. That's OK! It takes some work to wrap your brain around it.
이렇게 클로저와 모듈 패턴을 간략하게 살펴본 것만으로는 여전히 약간 혼란스러울 수 있습니다. 괜찮습니다! 머릿속을 정리하는 데 약간의 노력이 필요합니다.

From here, go read the *Scope & Closures* title of this series for a much more in-depth exploration.
여기에서 이 시리즈의 제목인 *범위 및 클로저*를 읽고 훨씬 더 깊이 있게 살펴보세요.

## `this` Identifier
## 이` 식별자

Another very commonly misunderstood concept in JavaScript is the `this` identifier. Again, there's a couple of chapters on it in the *this & Object Prototypes* title of this series, so here we'll just briefly introduce the concept.
자바스크립트에서 흔히 오해하는 또 다른 개념은 `this` 식별자입니다. 이 개념은 이 시리즈의 제목인 *이것과 객체 프로토타입*에 몇 개의 챕터가 있으므로 여기서는 간략하게 소개하겠습니다.

While it may often seem that `this` is related to "object-oriented patterns," in JS `this` is a different mechanism.
흔히 `this`가 "객체 지향 패턴"과 관련이 있는 것처럼 보일 수 있지만, JS에서 `this`는 다른 메커니즘입니다.

If a function has a `this` reference inside it, that `this` reference usually points to an `object`. But which `object` it points to depends on how the function was called.
함수 내부에 `this` 참조가 있는 경우, 그 `this` 참조는 일반적으로 `객체`를 가리킵니다. 그러나 어떤 `객체`를 가리키는지는 함수가 호출된 방식에 따라 다릅니다.

It's important to realize that `this` *does not* refer to the function itself, as is the most common misconception.
가장 흔한 오해처럼 `이것`은 함수 자체를 가리키는 것이 아니라는 점을 알아두는 것이 중요합니다.

Here's a quick illustration:
다음은 간단한 예시입니다:

```js
function foo() {
	console.log( this.bar );
}

var bar = "global";

var obj1 = {
	bar: "obj1",
	foo: foo
};

var obj2 = {
	bar: "obj2"
};

// --------

foo();				// "global"
obj1.foo();			// "obj1"
foo.call( obj2 );		// "obj2"
new foo();			// undefined
```

There are four rules for how `this` gets set, and they're shown in those last four lines of that snippet.
'this'가 설정되는 방식에는 네 가지 규칙이 있으며, 해당 스니펫의 마지막 네 줄에 이 규칙이 나와 있습니다.

1. `foo()` ends up setting `this` to the global object in non-strict mode -- in strict mode, `this` would be `undefined` and you'd get an error in accessing the `bar` property -- so `"global"` is the value found for `this.bar`.
2. `obj1.foo()` sets `this` to the `obj1` object.
3. `foo.call(obj2)` sets `this` to the `obj2` object.
4. `new foo()` sets `this` to a brand new empty object.
1. foo()`는 비엄격 모드에서 `this`를 전역 객체로 설정합니다. 엄격 모드에서는 `this`가 `정의되지 않음`이 되고 `bar` 속성에 액세스하는 데 오류가 발생하므로 `"global"`은 `this.bar`에 대해 찾은 값입니다.
2. obj1.foo()`는 `this`를 `obj1` 객체로 설정합니다.
3. foo.call(obj2)`는 `this`를 `obj2` 객체로 설정합니다.
4. new foo()`는 `this`를 새로운 빈 객체로 설정합니다.

Bottom line: to understand what `this` points to, you have to examine how the function in question was called. It will be one of those four ways just shown, and that will then answer what `this` is.
결론: `this`가 무엇을 가리키는지 이해하려면 해당 함수가 어떻게 호출되었는지 살펴봐야 합니다. 방금 설명한 네 가지 방법 중 하나이며, 이를 통해 `this`가 무엇인지 알 수 있습니다.

**Note:** For more information about `this`, see Chapters 1 and 2 of the *this & Object Prototypes* title of this series.
**참고: `this`에 대한 자세한 내용은 이 시리즈의 제목인 *이것과 객체 프로토타입*의 1장과 2장을 참조하세요.

## Prototypes
## 프로토타입

The prototype mechanism in JavaScript is quite complicated. We will only glance at it here. You will want to spend plenty of time reviewing Chapters 4-6 of the *this & Object Prototypes* title of this series for all the details.
자바스크립트의 프로토타입 메커니즘은 상당히 복잡합니다. 여기서는 간략하게만 살펴보겠습니다. 자세한 내용은 이 시리즈의 제목인 *이것과 객체 프로토타입*의 4장부터 6장까지를 충분히 검토하는 것이 좋습니다.

When you reference a property on an object, if that property doesn't exist, JavaScript will automatically use that object's internal prototype reference to find another object to look for the property on. You could think of this almost as a fallback if the property is missing.
객체에서 프로퍼티를 참조할 때 해당 프로퍼티가 존재하지 않으면 자바스크립트는 자동으로 해당 객체의 내부 프로토타입 참조를 사용해 해당 프로퍼티를 찾을 다른 객체를 찾습니다. 이는 프로퍼티가 누락되었을 때를 대비한 대체 수단이라고 생각하면 됩니다.

The internal prototype reference linkage from one object to its fallback happens at the time the object is created. The simplest way to illustrate it is with a built-in utility called `Object.create(..)`.
한 객체에서 폴백으로의 내부 프로토타입 참조 연결은 객체가 생성될 때 발생합니다. 이를 설명하는 가장 간단한 방법은 `Object.create(..)`라는 내장 유틸리티를 사용하는 것입니다.

Consider:
생각해 봅시다:

```js
var foo = {
	a: 42
};

// create `bar` and link it to `foo`
var bar = Object.create( foo );

bar.b = "hello world";

bar.b;		// "hello world"
bar.a;		// 42 <-- delegated to `foo`
```

It may help to visualize the `foo` and `bar` objects and their relationship:
foo`와 `bar` 객체와 그 관계를 시각화하면 도움이 될 수 있습니다:

<img src="fig6.png">

The `a` property doesn't actually exist on the `bar` object, but because `bar` is prototype-linked to `foo`, JavaScript automatically falls back to looking for `a` on the `foo` object, where it's found.
a` 속성은 실제로 `bar` 객체에 존재하지 않지만, `bar`는 `foo`에 프로토타입으로 연결되어 있기 때문에 자바스크립트는 자동으로 `foo` 객체에서 `a`를 찾아서 찾게 됩니다.

This linkage may seem like a strange feature of the language. The most common way this feature is used -- and I would argue, abused -- is to try to emulate/fake a "class" mechanism with "inheritance."
이 연결은 언어의 이상한 기능처럼 보일 수 있습니다. 이 기능이 사용되는 가장 일반적인 방법은 "상속"을 통해 "클래스" 메커니즘을 모방/가짜로 만드는 것입니다.

But a more natural way of applying prototypes is a pattern called "behavior delegation," where you intentionally design your linked objects to be able to *delegate* from one to the other for parts of the needed behavior.
그러나 프로토타입을 적용하는 더 자연스러운 방법은 "동작 위임"이라는 패턴으로, 연결된 객체가 필요한 동작의 일부를 다른 객체에 *위임*할 수 있도록 의도적으로 설계하는 것입니다.

**Note:** For more information about prototypes and behavior delegation, see Chapters 4-6 of the *this & Object Prototypes* title of this series.
참고: **주:** 프로토타입과 동작 위임에 대한 자세한 내용은 이 시리즈의 *이것과 객체 프로토타입* 제목의 4~6장을 참조하세요.

## Old & New
## 이전 버전과 새 버전

Some of the JS features we've already covered, and certainly many of the features covered in the rest of this series, are newer additions and will not necessarily be available in older browsers. In fact, some of the newest features in the specification aren't even implemented in any stable browsers yet.
이미 다룬 JS 기능 중 일부와 이 시리즈의 나머지 부분에서 다루는 기능 중 상당수는 최근에 추가된 기능으로, 구형 브라우저에서 반드시 사용할 수 있는 것은 아닙니다. 실제로 이 사양의 최신 기능 중 일부는 아직 안정적인 브라우저에서 구현되지 않은 것도 있습니다.

So, what do you do with the new stuff? Do you just have to wait around for years or decades for all the old browsers to fade into obscurity?
그렇다면 새로운 기능을 어떻게 사용해야 할까요? 오래된 브라우저들이 모두 사라질 때까지 몇 년, 몇 십 년을 기다려야 할까요?

That's how many people think about the situation, but it's really not a healthy approach to JS.
많은 사람들이 그렇게 생각하지만, 이는 JS에 대한 건전한 접근 방식이 아닙니다.

There are two main techniques you can use to "bring" the newer JavaScript stuff to the older browsers: polyfilling and transpiling.
최신 자바스크립트를 구형 브라우저에 '가져오는' 데 사용할 수 있는 두 가지 주요 기술은 폴리필링과 트랜스파일링입니다.

### Polyfilling
### 폴리필

The word "polyfill" is an invented term (by Remy Sharp) (https://remysharp.com/2010/10/08/what-is-a-polyfill) used to refer to taking the definition of a newer feature and producing a piece of code that's equivalent to the behavior, but is able to run in older JS environments.
"폴리필"이라는 단어는 새로운 기능의 정의를 가져와서 그 동작과 동일하지만 이전 JS 환경에서도 실행할 수 있는 코드를 생성하는 것을 가리키는 데 사용되는 (Remy Sharp가 만든) 용어(https://remysharp.com/2010/10/08/what-is-a-polyfill)입니다.

For example, ES6 defines a utility called `Number.isNaN(..)` to provide an accurate non-buggy check for `NaN` values, deprecating the original `isNaN(..)` utility. But it's easy to polyfill that utility so that you can start using it in your code regardless of whether the end user is in an ES6 browser or not.
예를 들어, ES6에서는 `NaN` 값에 대해 버그가 발생하지 않는 정확한 검사를 제공하기 위해 `Number.isNaN(..)`이라는 유틸리티를 정의하여 기존의 `isNaN(..)` 유틸리티를 더 이상 사용하지 않습니다. 하지만 이 유틸리티를 폴리필링하면 최종 사용자가 ES6 브라우저를 사용하는지 여부에 관계없이 코드에서 이 유틸리티를 사용할 수 있습니다.

Consider:
생각해 봅시다:

```js
if (!Number.isNaN) {
	Number.isNaN = function isNaN(x) {
		return x !== x;
	};
}
```

The `if` statement guards against applying the polyfill definition in ES6 browsers where it will already exist. If it's not already present, we define `Number.isNaN(..)`.
if` 문은 폴리필 정의가 이미 존재하는 ES6 브라우저에 적용되지 않도록 보호합니다. 아직 존재하지 않는다면 `Number.isNaN(..)`을 정의합니다.

**Note:** The check we do here takes advantage of a quirk with `NaN` values, which is that they're the only value in the whole language that is not equal to itself. So the `NaN` value is the only one that would make `x !== x` be `true`.
**참고:** 여기서 수행하는 검사는 전체 언어에서 자신과 같지 않은 유일한 값이라는 `NaN` 값의 특이한 점을 활용합니다. 따라서 `NaN` 값은 `x !== x`를 `참`으로 만들 수 있는 유일한 값입니다.

Not all new features are fully polyfillable. Sometimes most of the behavior can be polyfilled, but there are still small deviations. You should be really, really careful in implementing a polyfill yourself, to make sure you are adhering to the specification as strictly as possible.
모든 새로운 기능이 완전히 폴리필이 가능한 것은 아닙니다. 때로는 대부분의 동작이 폴리필링이 가능하지만 여전히 작은 편차가 있습니다. 폴리필을 직접 구현할 때는 최대한 엄격하게 사양을 준수할 수 있도록 정말 정말 주의해야 합니다.

Or better yet, use an already vetted set of polyfills that you can trust, such as those provided by ES5-Shim (https://github.com/es-shims/es5-shim) and ES6-Shim (https://github.com/es-shims/es6-shim).
또는 ES5-Shim(https://github.com/es-shims/es5-shim) 및 ES6-Shim(https://github.com/es-shims/es6-shim)에서 제공하는 것과 같이 신뢰할 수 있는 이미 검증된 폴리필 세트를 사용하는 것이 더 좋습니다.

### Transpiling
### 트랜스파일링

There's no way to polyfill new syntax that has been added to the language. The new syntax would throw an error in the old JS engine as unrecognized/invalid.
언어에 추가된 새 구문을 폴리필링할 수 있는 방법이 없습니다. 새 구문은 이전 JS 엔진에서 인식할 수 없거나 유효하지 않다는 오류를 발생시킵니다.

So the better option is to use a tool that converts your newer code into older code equivalents. This process is commonly called "transpiling," a term for transforming + compiling.
따라서 더 나은 방법은 최신 코드를 이전 코드와 동등한 코드로 변환하는 도구를 사용하는 것입니다. 이 프로세스를 일반적으로 '변환 + 컴파일'을 뜻하는 '트랜스파일링'이라고 합니다.

Essentially, your source code is authored in the new syntax form, but what you deploy to the browser is the transpiled code in old syntax form. You typically insert the transpiler into your build process, similar to your code linter or your minifier.
기본적으로 소스 코드는 새로운 구문 형식으로 작성되지만 브라우저에 배포하는 것은 이전 구문 형식으로 트랜스파일링된 코드입니다. 일반적으로 코드 린터나 미니파이어와 유사하게 빌드 프로세스에 트랜스파일러를 삽입합니다.

You might wonder why you'd go to the trouble to write new syntax only to have it transpiled away to older code -- why not just write the older code directly?
왜 굳이 새로운 구문을 작성하는 수고를 감수하고 이전 코드로 트랜스파일링해야 하는지, 왜 이전 코드를 직접 작성하지 않는지 궁금할 수 있습니다.

There are several important reasons you should care about transpiling:
트랜스파일링에 신경 써야 하는 몇 가지 중요한 이유가 있습니다:

* The new syntax added to the language is designed to make your code more readable and maintainable. The older equivalents are often much more convoluted. You should prefer writing newer and cleaner syntax, not only for yourself but for all other members of the development team.
* If you transpile only for older browsers, but serve the new syntax to the newest browsers, you get to take advantage of browser performance optimizations with the new syntax. This also lets browser makers have more real-world code to test their implementations and optimizations on.
* Using the new syntax earlier allows it to be tested more robustly in the real world, which provides earlier feedback to the JavaScript committee (TC39). If issues are found early enough, they can be changed/fixed before those language design mistakes become permanent.
* 언어에 추가된 새로운 구문은 코드의 가독성과 유지보수성을 높이기 위해 고안되었습니다. 이전 구문은 훨씬 더 복잡한 경우가 많습니다. 자신뿐만 아니라 개발팀의 다른 모든 구성원을 위해 더 새롭고 깔끔한 구문을 작성하는 것을 선호해야 합니다.
* 구형 브라우저에만 트랜스파일을 적용하고 최신 브라우저에는 새 구문을 제공하면 새 구문을 통해 브라우저 성능 최적화의 이점을 누릴 수 있습니다. 또한 브라우저 제조업체는 구현 및 최적화를 테스트할 수 있는 실제 코드를 더 많이 확보할 수 있습니다.
* 새 구문을 더 일찍 사용하면 실제 환경에서 더 강력하게 테스트할 수 있으므로 자바스크립트 위원회(TC39)에 더 일찍 피드백을 제공할 수 있습니다. 문제를 조기에 발견하면 언어 설계상의 실수가 영구화되기 전에 변경/수정할 수 있습니다.

Here's a quick example of transpiling. ES6 adds a feature called "default parameter values." It looks like this:
다음은 트랜스파일링의 간단한 예시입니다. ES6에는 "기본 매개변수 값"이라는 기능이 추가되었습니다. 다음과 같이 보입니다:

```js
function foo(a = 2) {
	console.log( a );
}

foo();		// 2
foo( 42 );	// 42
```

Simple, right? Helpful, too! But it's new syntax that's invalid in pre-ES6 engines. So what will a transpiler do with that code to make it run in older environments?
간단하죠? 유용하기도 하죠? 하지만 ES6 이전 엔진에서는 유효하지 않은 새로운 구문입니다. 그렇다면 트랜스파일러는 이 코드를 이전 환경에서 실행하기 위해 어떤 작업을 수행할까요?

```js
function foo() {
	var a = arguments[0] !== (void 0) ? arguments[0] : 2;
	console.log( a );
}
```

As you can see, it checks to see if the `arguments[0]` value is `void 0` (aka `undefined`), and if so provides the `2` default value; otherwise, it assigns whatever was passed.
보시다시피, `arguments[0]` 값이 `void 0`(일명 `undefined`)인지 확인하고, 그렇다면 기본값인 `2`를 제공하고, 그렇지 않으면 전달된 값을 할당합니다.

In addition to being able to now use the nicer syntax even in older browsers, looking at the transpiled code actually explains the intended behavior more clearly.
이제 구형 브라우저에서도 더 멋진 구문을 사용할 수 있을 뿐 아니라, 트랜스파일된 코드를 보면 의도한 동작이 더 명확하게 설명됩니다.

You may not have realized just from looking at the ES6 version that `undefined` is the only value that can't get explicitly passed in for a default-value parameter, but the transpiled code makes that much more clear.
ES6 버전만 보면 기본값 매개변수에 명시적으로 전달할 수 없는 값은 '정의되지 않음'뿐이라는 사실을 깨닫지 못했을 수도 있지만, 트랜스파일링된 코드를 보면 훨씬 더 명확해집니다.

The last important detail to emphasize about transpilers is that they should now be thought of as a standard part of the JS development ecosystem and process. JS is going to continue to evolve, much more quickly than before, so every few months new syntax and new features will be added.
마지막으로 트랜스파일러에 대해 강조하고 싶은 중요한 사항은 이제 트랜스파일러를 JS 개발 에코시스템과 프로세스의 표준 부분으로 생각해야 한다는 것입니다. JS는 이전보다 훨씬 더 빠르게 계속 발전할 것이므로 몇 달마다 새로운 구문과 새로운 기능이 추가될 것입니다.

If you use a transpiler by default, you'll always be able to make that switch to newer syntax whenever you find it useful, rather than always waiting for years for today's browsers to phase out.
기본적으로 트랜스파일러를 사용하는 경우, 오늘날의 브라우저가 단계적으로 사라질 때까지 몇 년을 기다릴 필요 없이 유용하다고 판단될 때마다 언제든지 최신 구문으로 전환할 수 있습니다.

There are quite a few great transpilers for you to choose from. Here are some good options at the time of this writing:
선택할 수 있는 훌륭한 트랜스파일러가 꽤 많이 있습니다. 이 글을 쓰는 시점에서 몇 가지 좋은 옵션은 다음과 같습니다:

* Babel (https://babeljs.io) (formerly 6to5): Transpiles ES6+ into ES5
* Traceur (https://github.com/google/traceur-compiler): Transpiles ES6, ES7, and beyond into ES5
* 바벨(https://babeljs.io)(이전의 6to5): ES6+를 ES5로 트랜스파일링
* 트레이스어(https://github.com/google/traceur-compiler): ES6, ES7 및 그 이상을 ES5로 변환합니다.

## Non-JavaScript
## 비 자바스크립트

So far, the only things we've covered are in the JS language itself. The reality is that most JS is written to run in and interact with environments like browsers. A good chunk of the stuff that you write in your code is, strictly speaking, not directly controlled by JavaScript. That probably sounds a little strange.
지금까지 다룬 내용은 JS 언어 자체에 관한 것입니다. 사실 대부분의 JS는 브라우저와 같은 환경에서 실행되고 상호 작용하도록 작성되었습니다. 엄밀히 말하면 코드에서 작성하는 내용 중 상당 부분은 자바스크립트로 직접 제어되지 않습니다. 조금 이상하게 들릴 수도 있습니다.

The most common non-JavaScript JavaScript you'll encounter is the DOM API. For example:
자바스크립트가 아닌 가장 일반적인 자바스크립트는 DOM API입니다. 예를 들어

```js
var el = document.getElementById( "foo" );
```

The `document` variable exists as a global variable when your code is running in a browser. It's not provided by the JS engine, nor is it particularly controlled by the JavaScript specification. It takes the form of something that looks an awful lot like a normal JS `object`, but it's not really exactly that. It's a special `object,` often called a "host object."
문서` 변수는 코드가 브라우저에서 실행될 때 전역 변수로 존재합니다. 이 변수는 JS 엔진에서 제공하지 않으며, 자바스크립트 사양에 의해 특별히 제어되지도 않습니다. 일반적인 JS `객체`와 매우 흡사한 형태를 취하지만 실제로는 그렇지 않습니다. 이는 흔히 "호스트 객체"라고 불리는 특수한 `객체`입니다.

Moreover, the `getElementById(..)` method on `document` looks like a normal JS function, but it's just a thinly exposed interface to a built-in method provided by the DOM from your browser. In some (newer-generation) browsers, this layer may also be in JS, but traditionally the DOM and its behavior is implemented in something more like C/C++.
또한 `document`의 `getElementById(..)` 메서드는 일반 JS 함수처럼 보이지만 브라우저에서 DOM이 제공하는 내장 메서드에 대한 인터페이스가 얇게 노출된 것일 뿐입니다. 일부 (최신 세대) 브라우저에서는 이 계층이 JS에도 있을 수 있지만, 전통적으로 DOM과 그 동작은 C/C++과 같은 방식으로 구현됩니다.

Another example is with input/output (I/O).
또 다른 예는 입력/출력(I/O)입니다.

Everyone's favorite `alert(..)` pops up a message box in the user's browser window. `alert(..)` is provided to your JS program by the browser, not by the JS engine itself. The call you make sends the message to the browser internals and it handles drawing and displaying the message box.
모두가 좋아하는 `alert(..)`는 사용자의 브라우저 창에 메시지 상자를 띄웁니다. alert(..)`는 JS 엔진 자체가 아니라 브라우저에 의해 JS 프로그램에 제공됩니다. 호출하면 브라우저 내부로 메시지가 전송되고 브라우저는 메시지 상자를 그리고 표시하는 작업을 처리합니다.

The same goes with `console.log(..)`; your browser provides such mechanisms and hooks them up to the developer tools.
콘솔 로그(..)`도 마찬가지입니다. 브라우저는 이러한 메커니즘을 제공하고 이를 개발자 도구에 연결합니다.

This book, and this whole series, focuses on JavaScript the language. That's why you don't see any substantial coverage of these non-JavaScript JavaScript mechanisms. Nevertheless, you need to be aware of them, as they'll be in every JS program you write!
이 책과 이 시리즈 전체는 자바스크립트라는 언어에 초점을 맞춥니다. 그렇기 때문에 자바스크립트가 아닌 자바스크립트 메커니즘에 대해서는 크게 다루지 않았습니다. 그럼에도 불구하고 이러한 메커니즘은 여러분이 작성하는 모든 JS 프로그램에 포함될 것이므로 반드시 알고 있어야 합니다!

## Review
## 검토

The first step to learning JavaScript's flavor of programming is to get a basic understanding of its core mechanisms like values, types, function closures, `this`, and prototypes.
자바스크립트 프로그래밍을 배우기 위한 첫 번째 단계는 값, 타입, 함수 클로저, `이것`, 프로토타입과 같은 핵심 메커니즘에 대한 기본적인 이해를 얻는 것입니다.

Of course, each of these topics deserves much greater coverage than you've seen here, but that's why they have chapters and books dedicated to them throughout the rest of this series. After you feel pretty comfortable with the concepts and code samples in this chapter, the rest of the series awaits you to really dig in and get to know the language deeply.
물론 이러한 각 주제는 여기서 살펴본 것보다 훨씬 더 많은 내용을 다룰 필요가 있지만, 이 시리즈의 나머지 장과 책에 해당 주제에 대한 챕터와 책이 있는 이유도 여기에 있습니다. 이 장의 개념과 코드 샘플에 어느 정도 익숙해졌다면, 나머지 시리즈에서는 이 언어를 더 깊이 파고들어 깊이 있게 알아볼 수 있습니다.

The final chapter of this book will briefly summarize each of the other titles in the series and the other concepts they cover besides what we've already explored.
이 책의 마지막 장에서는 시리즈의 다른 책과 이미 살펴본 내용 외에 다른 개념에 대해 간략하게 요약해 보겠습니다.