# You Don't Know JS: Up & Going
# 1장: 프로그래밍 시작하기

*You Don't Know JS* (*YDKJS*) 시리즈에 오신 것을 환영합니다.

*Up & Going*에서는 프로그래밍의 몇 가지 기본 개념 (물론 JavaScript(흔히 JS로 축약됨)를 중심으로 설명합니다) 과 이 시리즈의 나머지 타이틀에 대해 접근하고 이해하는 방법을 소개합니다. 특히 프로그래밍 및/또는 자바스크립트를 이제 막 시작하는 분이라면 이 책에서 '시작'하는 데 필요한 내용을 간략하게 살펴볼 수 있습니다.

이 책은 매우 높은 수준에서 프로그래밍의 기본 원리를 설명하는 것부터 시작합니다. 또한, 이 책은 주로 프로그래밍 경험이 거의 또는 전혀 없는 상태에서 *YDKJS*를 시작하고 자바스크립트의 렌즈를 통해 프로그래밍을 이해하는 데 도움이 되는 책을 찾고 있는 분들을 대상으로 합니다.

1장은 프로그래밍을 시작하기 위해 더 많이 배우고 연습해야 할 내용을 간략하게 살펴보는 정도로 접근해야 합니다. 또한, 이러한 주제를 더 깊이 파고드는 데 도움이 되는 다른 훌륭한 프로그래밍 입문 자료도 많이 있으므로 이 장 외에도 이러한 자료를 참고하여 학습하는 것이 좋습니다.

일반적인 프로그래밍 기초에 익숙해졌다면 2장에서 자바스크립트의 프로그래밍 방식에 익숙해지는 데 도움이 될 것입니다. 2장에서는 자바스크립트가 무엇인지 소개하지만, 이는 포괄적인 가이드는 아니며, 나머지 *YDKJS* 책에서 다룰 것 입니다!

이미 자바스크립트에 익숙하다면 먼저 3장의 *YDKJS* 에서 기대할 수 있는 내용을 간략하게 확인한 다음 바로 시작하세요!

## 코드

처음부터 시작하겠습니다.

흔히 *소스코드* 또는 *코드*라고도 하는 프로그램은 컴퓨터에게 어떤 작업을 수행할지 알려주는 특수 명령어 집합입니다. 일반적으로 코드는 텍스트 파일에 저장되지만 JavaScript를 사용하면 브라우저의 개발자 콘솔에 직접 코드를 입력할 수도 있습니다. 이에 대해서는 곧 다루겠습니다.

유효한 형식과 명령어 조합에 대한 규칙을 *컴퓨터 언어*라고 하며, 영어에서 단어의 철자법이나 단어와 구두점을 사용하여 유효한 문장을 만드는 방법을 알려주는 것과 마찬가지로 *구문*이라고도 합니다.

### Statements
문

In a computer language, a group of words, numbers, and operators that performs a specific task is a *statement*. In JavaScript, a statement might look as follows:
컴퓨터 언어에서 특정 작업을 수행하는 단어, 숫자 및 연산자 그룹을 *문*이라고 합니다. 자바스크립트에서 문은 다음과 같이 보일 수 있습니다:

```js
a = b * 2;
```

The characters `a` and `b` are called *variables* (see "Variables"), which are like simple boxes you can store any of your stuff in. In programs, variables hold values (like the number `42`) to be used by the program. Think of them as symbolic placeholders for the values themselves.
문자 `a`와 `b`를 *변수*라고 하는데("변수" 참조), 이는 무엇이든 저장할 수 있는 간단한 상자와 같습니다. 프로그램에서 변수는 프로그램에서 사용할 값(예: 숫자 `42`)을 저장합니다. 변수는 값 자체에 대한 상징적인 자리 표시자라고 생각하면 됩니다.

By contrast, the `2` is just a value itself, called a *literal value*, because it stands alone without being stored in a variable.
반면 `2`는 변수에 저장되지 않고 독립적으로 존재하기 때문에 *리터럴 값*이라고 하는 값 자체에 불과합니다.

The `=` and `*` characters are *operators* (see "Operators") -- they perform actions with the values and variables such as assignment and mathematic multiplication.
'=` 및 `*` 문자는 *연산자*("연산자" 참조)로, 값과 변수를 가지고 할당 및 수학 곱셈과 같은 연산을 수행합니다.

Most statements in JavaScript conclude with a semicolon (`;`) at the end.
자바스크립트의 대부분의 문은 마지막에 세미콜론(`;`)으로 마무리됩니다.

The statement `a = b * 2;` tells the computer, roughly, to get the current value stored in the variable `b`, multiply that value by `2`, then store the result back into another variable we call `a`.
a = b * 2;` 문은 대략적으로 컴퓨터에게 변수 `b`에 저장된 현재 값을 가져와서 그 값에 `2`를 곱한 다음 그 결과를 다시 `a`라고 부르는 다른 변수에 저장하라고 지시하는 것입니다.

Programs are just collections of many such statements, which together describe all the steps that it takes to perform your program's purpose.
프로그램은 이러한 많은 명령문의 집합으로, 프로그램의 목적을 수행하는 데 필요한 모든 단계를 설명합니다.

### Expressions
표현식

Statements are made up of one or more *expressions*. An expression is any reference to a variable or value, or a set of variable(s) and value(s) combined with operators.
문은 하나 이상의 *표현식*으로 구성됩니다. 표현식은 변수나 값에 대한 참조 또는 연산자와 결합된 변수 및 값의 집합을 말합니다.

For example:
예를 들어

```js
a = b * 2;
```

This statement has four expressions in it:
이 문에는 네 개의 표현식이 있습니다:

* `2` is a *literal value expression*
* `b` is a *variable expression*, which means to retrieve its current value
* `b * 2` is an *arithmetic expression*, which means to do the multiplication
* `a = b * 2` is an *assignment expression*, which means to assign the result of the `b * 2` expression to the variable `a` (more on assignments later)
* `2`는 *리터럴 값 표현식*입니다.
* `b`는 *변수 표현식*으로, 현재 값을 검색하는 것을 의미합니다.
* `b * 2`는 *산술 표현식*으로, 곱셈을 수행하는 것을 의미합니다.
* `a = b * 2`는 *할당 표현식*으로, `b * 2` 표현식의 결과를 변수 `a`에 할당하는 것을 의미합니다(나중에 할당에 대해 자세히 설명합니다).

A general expression that stands alone is also called an *expression statement*, such as the following:
다음과 같이 단독으로 존재하는 일반적인 표현식을 *표현식 문*이라고도 합니다:

```js
b * 2;
```

This flavor of expression statement is not very common or useful, as generally it wouldn't have any effect on the running of the program -- it would retrieve the value of `b` and multiply it by `2`, but then wouldn't do anything with that result.
이러한 표현식 문은 일반적으로 프로그램 실행에 아무런 영향을 미치지 않기 때문에 그다지 일반적이거나 유용하지 않습니다. `b`의 값을 검색하고 `2`를 곱하지만 그 결과로는 아무 작업도 하지 않습니다.

A more common expression statement is a *call expression* statement (see "Functions"), as the entire statement is the function call expression itself:
보다 일반적인 표현식 문은 전체 문이 함수 호출 표현식 자체인 *call 표현식* 문입니다("함수" 참조):

```js
alert( a );
```

### Executing a Program
### 프로그램 실행하기

How do those collections of programming statements tell the computer what to do? The program needs to be *executed*, also referred to as *running the program*.
이러한 프로그래밍 명령문 모음은 어떻게 컴퓨터에게 무엇을 하라고 지시할까요? 프로그램을 *실행*해야 하는데, 이를 *프로그램 실행*이라고도 합니다.

Statements like `a = b * 2` are helpful for developers when reading and writing, but are not actually in a form the computer can directly understand. So a special utility on the computer (either an *interpreter* or a *compiler*) is used to translate the code you write into commands a computer can understand.
'a = b * 2'와 같은 문은 개발자가 읽고 쓸 때 유용하지만 실제로 컴퓨터가 직접 이해할 수 있는 형태는 아닙니다. 따라서 컴퓨터의 특수 유틸리티(*인터프리터* 또는 *컴파일러*)를 사용하여 작성한 코드를 컴퓨터가 이해할 수 있는 명령으로 번역합니다.

For some computer languages, this translation of commands is typically done from top to bottom, line by line, every time the program is run, which is usually called *interpreting* the code.
일부 컴퓨터 언어의 경우, 이러한 명령어 번역은 일반적으로 프로그램이 실행될 때마다 위에서 아래로, 한 줄씩 수행되며, 이를 일반적으로 코드 *인터프리터*라고 합니다.

For other languages, the translation is done ahead of time, called *compiling* the code, so when the program *runs* later, what's running is actually the already compiled computer instructions ready to go.
다른 언어의 경우, 코드 *컴파일*이라고 하는 번역이 미리 수행되므로 나중에 프로그램이 *실행*될 때 실제로 실행되는 것은 이미 컴파일된 컴퓨터 명령어가 준비된 상태입니다.

It's typically asserted that JavaScript is *interpreted*, because your JavaScript source code is processed each time it's run. But that's not entirely accurate. The JavaScript engine actually *compiles* the program on the fly and then immediately runs the compiled code.
일반적으로 자바스크립트 소스 코드가 실행될 때마다 처리되기 때문에 자바스크립트가 *해석*된다고 주장합니다. 하지만 이는 완전히 정확하지 않습니다. 자바스크립트 엔진은 실제로 프로그램을 즉석에서 *컴파일*한 다음 컴파일된 코드를 즉시 실행합니다.

**Note:** For more information on JavaScript compiling, see the first two chapters of the *Scope & Closures* title of this series.
참고: **주:** JavaScript 컴파일에 대한 자세한 내용은 이 시리즈의 *범위와 클로저* 제목의 처음 두 장을 참조하세요.

## Try It Yourself
## 직접 해보기

This chapter is going to introduce each programming concept with simple snippets of code, all written in JavaScript (obviously!).
이 장에서는 각 프로그래밍 개념을 자바스크립트로 작성된 간단한 코드 스니펫으로 소개할 것입니다(물론!).

It cannot be emphasized enough: while you go through this chapter -- and you may need to spend the time to go over it several times -- you should practice each of these concepts by typing the code yourself. The easiest way to do that is to open up the developer tools console in your nearest browser (Firefox, Chrome, IE, etc.).
아무리 강조해도 지나치지 않습니다. 이 장을 살펴보는 동안 - 그리고 시간을 들여 여러 번 살펴봐야 할 수도 있습니다 - 코드를 직접 입력해 보면서 각 개념을 연습해야 합니다. 가장 쉬운 방법은 가까운 브라우저(Firefox, Chrome, IE 등)에서 개발자 도구 콘솔을 여는 것입니다.

**Tip:** Typically, you can launch the developer console with a keyboard shortcut or from a menu item. For more detailed information about launching and using the console in your favorite browser, see "Mastering The Developer Tools Console" (http://blog.teamtreehouse.com/mastering-developer-tools-console). To type multiple lines into the console at once, use `<shift> + <enter>` to move to the next new line. Once you hit `<enter>` by itself, the console will run everything you've just typed.
**팁: 일반적으로 키보드 단축키를 사용하거나 메뉴 항목을 통해 개발자 콘솔을 시작할 수 있습니다. 자주 사용하는 브라우저에서 콘솔을 실행하고 사용하는 방법에 대한 자세한 내용은 '개발자 도구 콘솔 마스터하기'(http://blog.teamtreehouse.com/mastering-developer-tools-console)를 참조하세요. 콘솔에 한 번에 여러 줄을 입력하려면 `<shift> + <enter>`를 사용하여 다음 새 줄로 이동합니다. 그냥 `<입력>`을 누르면 콘솔이 방금 입력한 내용을 모두 실행합니다.

Let's get familiar with the process of running code in the console. First, I suggest opening up an empty tab in your browser. I prefer to do this by typing `about:blank` into the address bar. Then, make sure your developer console is open, as we just mentioned.
콘솔에서 코드를 실행하는 프로세스에 대해 알아봅시다. 먼저 브라우저에서 빈 탭을 여는 것이 좋습니다. 주소창에 `about:blank`을 입력하는 것이 좋습니다. 그런 다음 방금 언급한 대로 개발자 콘솔이 열려 있는지 확인합니다.

Now, type this code and see how it runs:
이제 이 코드를 입력하고 어떻게 실행되는지 확인합니다:

```js
a = 21;

b = a * 2;

console.log( b );
```

Typing the preceding code into the console in Chrome should produce something like the following:
Chrome의 콘솔에 앞의 코드를 입력하면 다음과 같은 결과가 표시됩니다:

<img src="fig1.png" width="500">

Go on, try it. The best way to learn programming is to start coding!
어서 해보세요. 프로그래밍을 배우는 가장 좋은 방법은 코딩을 시작하는 것입니다!

### Output
### 출력

In the previous code snippet, we used `console.log(..)`. Briefly, let's look at what that line of code is all about.
이전 코드 스니펫에서는 `console.log(..)`를 사용했습니다. 이 코드가 어떤 내용인지 간단히 살펴봅시다.

You may have guessed, but that's exactly how we print text (aka *output* to the user) in the developer console. There are two characteristics of that statement that we should explain.
짐작하셨겠지만, 이것이 바로 개발자 콘솔에서 사용자에게 텍스트(일명 *출력*)를 출력하는 방식입니다. 이 문에는 두 가지 특징이 있습니다.

First, the `log( b )` part is referred to as a function call (see "Functions"). What's happening is we're handing the `b` variable to that function, which asks it to take the value of `b` and print it to the console.
첫째, `log( b )` 부분을 함수 호출이라고 합니다("함수" 참조). 무슨 일이 일어나고 있느냐 하면 `b` 변수를 해당 함수에 전달하고, 이 함수는 `b` 값을 가져와 콘솔에 출력하도록 요청하는 것입니다.

Second, the `console.` part is an object reference where the `log(..)` function is located. We cover objects and their properties in more detail in Chapter 2.
둘째, `console.` 부분은 `log(..)` 함수가 위치한 객체 참조입니다. 객체와 그 속성에 대해서는 2장에서 더 자세히 다루겠습니다.

Another way of creating output that you can see is to run an `alert(..)` statement. For example:
눈으로 확인할 수 있는 출력을 생성하는 또 다른 방법은 `alert(..)` 문을 실행하는 것입니다. 예를 들어

```js
alert( b );
```

If you run that, you'll notice that instead of printing the output to the console, it shows a popup "OK" box with the contents of the `b` variable. However, using `console.log(..)` is generally going to make learning about coding and running your programs in the console easier than using `alert(..)`, because you can output many values at once without interrupting the browser interface.
이를 실행하면 콘솔에 출력을 출력하는 대신 `b` 변수의 내용이 포함된 "확인" 팝업 상자가 표시되는 것을 볼 수 있습니다. 그러나 `console.log(..)`를 사용하면 브라우저 인터페이스를 중단하지 않고 한 번에 많은 값을 출력할 수 있기 때문에 일반적으로 `alert(..)`를 사용하는 것보다 콘솔에서 프로그램을 코딩하고 실행하는 방법을 더 쉽게 배울 수 있습니다.

For this book, we'll use `console.log(..)` for output.
이 책에서는 `console.log(..)`를 출력에 사용하겠습니다.

### Input
### 입력

While we're discussing output, you may also wonder about *input* (i.e., receiving information from the user).
출력에 대해 논의하는 동안 *입력*(즉, 사용자로부터 정보를 수신하는 것)에 대해서도 궁금할 수 있습니다.

The most common way that happens is for the HTML page to show form elements (like text boxes) to a user that they can type into, and then using JS to read those values into your program's variables.
가장 일반적인 방법은 HTML 페이지에서 사용자가 입력할 수 있는 양식 요소(예: 텍스트 상자)를 표시한 다음 JS를 사용하여 해당 값을 프로그램의 변수로 읽어들이는 것입니다.

But there's an easier way to get input for simple learning and demonstration purposes such as what you'll be doing throughout this book. Use the `prompt(..)` function:
하지만 이 책 전체에서 다루게 될 내용처럼 간단한 학습 및 데모 목적으로 입력을 받는 더 쉬운 방법이 있습니다. 프롬프트(..)` 함수를 사용하세요:

```js
age = prompt( "Please tell me your age:" );

console.log( age );
```

As you may have guessed, the message you pass to `prompt(..)` -- in this case, `"Please tell me your age:"` -- is printed into the popup.
짐작할 수 있듯이 `prompt(..)`에 전달한 메시지(이 경우 `"나이를 알려주세요:"`)가 팝업에 인쇄됩니다.

This should look similar to the following:
다음과 비슷하게 보일 것입니다:

<img src="fig2.png" width="500">

Once you submit the input text by clicking "OK," you'll observe that the value you typed is stored in the `age` variable, which we then *output* with `console.log(..)`:
"확인"을 클릭하여 입력 텍스트를 제출하면 입력한 값이 `age` 변수에 저장되는 것을 확인할 수 있으며, 이 변수는 `console.log(..)`로 *출력*됩니다:

<img src="fig3.png" width="500">

To keep things simple while we're learning basic programming concepts, the examples in this book will not require input. But now that you've seen how to use `prompt(..)`, if you want to challenge yourself you can try to use input in your explorations of the examples.
기본 프로그래밍 개념을 배우는 동안 작업을 단순하게 유지하기 위해 이 책의 예제에는 입력이 필요하지 않습니다. 하지만 이제 '프롬프트(..)`를 사용하는 방법을 살펴봤으니 도전해보고 싶다면 예제를 살펴볼 때 입력을 사용해 볼 수 있습니다.

## Operators
## 연산자

Operators are how we perform actions on variables and values. We've already seen two JavaScript operators, the `=` and the `*`.
연산자는 변수와 값에 대한 작업을 수행하는 방법입니다. 이미 두 가지 자바스크립트 연산자, `=`와 `*`를 살펴봤습니다.

The `*` operator performs mathematic multiplication. Simple enough, right?
연산자 `*`는 수학적 곱셈을 수행합니다. 충분히 간단하지 않나요?

The `=` equals operator is used for *assignment* -- we first calculate the value on the *right-hand side* (source value) of the `=` and then put it into the variable that we specify on the *left-hand side* (target variable).
등호 연산자는 *할당*에 사용되며, 먼저 `=`의 *오른쪽*(소스 값)에 있는 값을 계산한 다음 *왼쪽*(대상 변수)에 지정한 변수에 넣습니다.

**Warning:** This may seem like a strange reverse order to specify assignment. Instead of `a = 42`, some might prefer to flip the order so the source value is on the left and the target variable is on the right, like `42 -> a` (this is not valid JavaScript!). Unfortunately, the `a = 42` ordered form, and similar variations, is quite prevalent in modern programming languages. If it feels unnatural, just spend some time rehearsing that ordering in your mind to get accustomed to it.
**경고:** 대입을 지정하는 데 이상한 역순으로 보일 수 있습니다. a = 42` 대신 `42 -> a`와 같이 소스 값이 왼쪽에 있고 대상 변수가 오른쪽에 있도록 순서를 뒤집는 것을 선호할 수도 있습니다(이는 유효한 자바스크립트가 아닙니다!). 안타깝게도 `a = 42` 순서 형식과 이와 유사한 변형은 최신 프로그래밍 언어에서 상당히 널리 사용됩니다. 부자연스럽게 느껴진다면 머릿속으로 이 순서를 연습하면서 익숙해지도록 시간을 투자하세요.

Consider:
고려하세요:

```js
a = 2;
b = a + 1;
```

Here, we assign the `2` value to the `a` variable. Then, we get the value of the `a` variable (still `2`), add `1` to it resulting in the value `3`, then store that value in the `b` variable.
여기서는 `2` 값을 `a` 변수에 할당합니다. 그런 다음 `a` 변수의 값(여전히 `2`)을 가져와서 `1`을 더하면 `3`이 되고, 그 값을 `b` 변수에 저장합니다.

While not technically an operator, you'll need the keyword `var` in every program, as it's the primary way you *declare* (aka *create*) *var*iables (see "Variables").
엄밀히 말하면 연산자는 아니지만, 모든 프로그램에서 `var` 키워드는 *변수*를 *선언*(또는 *생성*)하는 주요 방법이기 때문에 필요합니다("변수" 참조).

You should always declare the variable by name before you use it. But you only need to declare a variable once for each *scope* (see "Scope"); it can be used as many times after that as needed. For example:
변수를 사용하기 전에 항상 변수를 이름으로 선언해야 합니다. 그러나 변수는 각 *범위*마다 한 번만 선언하면 되고("범위" 참조), 그 이후에는 필요한 만큼 여러 번 사용할 수 있습니다. 예를 들어

```js
var a = 20;

a = a + 1;
a = a * 2;

console.log( a );	// 42
```

Here are some of the most common operators in JavaScript:
다음은 자바스크립트에서 가장 일반적인 연산자 몇 가지입니다:

* Assignment: `=` as in `a = 2`.
* Math: `+` (addition), `-` (subtraction), `*` (multiplication), and `/` (division), as in `a * 3`.
* Compound Assignment: `+=`, `-=`, `*=`, and `/=` are compound operators that combine a math operation with assignment, as in `a += 2` (same as `a = a + 2`).
* Increment/Decrement: `++` (increment), `--` (decrement), as in `a++` (similar to `a = a + 1`).
* Object Property Access: `.` as in `console.log()`.

   Objects are values that hold other values at specific named locations called properties. `obj.a` means an object value called `obj` with a property of the name `a`. Properties can alternatively be accessed as `obj["a"]`. See Chapter 2.
* Equality: `==` (loose-equals), `===` (strict-equals), `!=` (loose not-equals), `!==` (strict not-equals), as in `a == b`.

   See "Values & Types" and Chapter 2.
* Comparison: `<` (less than), `>` (greater than), `<=` (less than or loose-equals), `>=` (greater than or loose-equals), as in `a <= b`.

   See "Values & Types" and Chapter 2.
* Logical: `&&` (and), `||` (or), as in `a || b` that selects either `a` *or* `b`.
* 대입: `a = 2`와 같이 `=`.
* 수학: a * 3`과 같이 `+`(덧셈), `-`(뺄셈), `*`(곱셈) 및 `/`(나눗셈).
* 복합 대입: `+=`, `-=`, `*=` 및 `/=`는 `a += 2`와 같이 수학 연산과 대입을 결합하는 복합 연산자입니다(`a = a + 2`와 동일).
* 증가/감소: `a++`와 같이 `++`(증가), `--`(감소)입니다(`a = a + 1`과 유사).
* 개체 속성 액세스: 콘솔 로그()`에서와 같이 `.`.

   객체는 프로퍼티라고 하는 특정 명명된 위치에 다른 값을 저장하는 값입니다. obj.a`는 이름이 `a`인 속성을 가진 `obj`라는 개체 값을 의미합니다. 프로퍼티는 `obj["a"]`로 액세스할 수도 있습니다. 2장을 참조하십시오.
* 같음: `==`(느슨한 같음), `===`(엄격한 같음), `!=`(느슨한 같지 않음), `!==`(엄격한 같지 않음), `a == b`에서와 같이.

   "값과 유형" 및 2장을 참조하십시오.
* 비교: `<`(보다 작음), `>`(보다 큼), `<=`(보다 작거나 느슨한 같음), `>=`(보다 크거나 느슨한 같음), `a <= b`에서와 같이 비교합니다.

   "값과 유형" 및 2장을 참조하십시오.
* 논리: `&&`(및), `||`(또는), `a || b`에서처럼 `a` *또는* `b` 중 하나를 선택합니다.

These operators are used to express compound conditionals (see "Conditionals"), like if either `a` *or* `b` is true.
이러한 연산자는 `a` *또는* `b` 중 하나가 참인 경우와 같이 복합 조건("조건" 참조)을 표현하는 데 사용됩니다.

**Note:** For much more detail, and coverage of operators not mentioned here, see the Mozilla Developer Network (MDN)'s "Expressions and Operators" (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators).
**참고: **여기에 언급되지 않은 연산자에 대한 자세한 내용 및 적용 범위는 Mozilla 개발자 네트워크(MDN)의 "표현식 및 연산자"(https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)를 참조하세요.

## Values & Types
## 값 및 유형

If you ask an employee at a phone store how much a certain phone costs, and they say "ninety-nine, ninety-nine" (i.e., $99.99), they're giving you an actual numeric dollar figure that represents what you'll need to pay (plus taxes) to buy it. If you want to buy two of those phones, you can easily do the mental math to double that value to get $199.98 for your base cost.
휴대폰 매장 직원에게 특정 휴대폰의 가격을 물었을 때 직원이 "99, 99"(즉, $99.99)라고 대답한다면, 그 휴대폰을 구입하기 위해 지불해야 하는 금액(세금 포함)을 실제 숫자로 알려주는 것입니다. 이러한 휴대전화를 두 대 구매하려는 경우, 이 값을 두 배로 계산하여 기본 비용으로 $199.98을 쉽게 계산할 수 있습니다.

If that same employee picks up another similar phone but says it's "free" (perhaps with air quotes), they're not giving you a number, but instead another kind of representation of your expected cost ($0.00) -- the word "free."
같은 직원이 다른 유사한 휴대폰을 집어 들면서 "무료"라고 말한다면(아마도 공기 따옴표가 붙어 있을 것입니다), 그 직원은 숫자를 알려주는 것이 아니라 예상 비용($0.00)을 "무료"라는 단어로 표현한 것입니다.

When you later ask if the phone includes a charger, that answer could only have been either "yes" or "no."
나중에 휴대폰에 충전기가 포함되어 있는지 물어보면 "예" 또는 "아니오" 중 하나만 대답할 수 있습니다.

In very similar ways, when you express values in a program, you choose different representations for those values based on what you plan to do with them.
이와 매우 유사한 방식으로 프로그램에서 값을 표현할 때 해당 값으로 무엇을 하려는지에 따라 해당 값에 대해 다른 표현을 선택합니다.

These different representations for values are called *types* in programming terminology. JavaScript has built-in types for each of these so called *primitive* values:
이러한 다양한 값 표현을 프로그래밍 용어로는 *유형*이라고 합니다. 자바스크립트에는 *원시적* 값이라고 불리는 각 값에 대한 기본 제공 유형이 있습니다:

* When you need to do math, you want a `number`.
* When you need to print a value on the screen, you need a `string` (one or more characters, words, sentences).
* When you need to make a decision in your program, you need a `boolean` (`true` or `false`).
* 수학을 해야 할 때는 '숫자'가 필요합니다.
* 화면에 값을 인쇄해야 할 때는 ` 문자열`(하나 이상의 문자, 단어, 문장)이 필요합니다.
* 프로그램에서 결정을 내려야 할 때는 `부울`(`참` 또는 `거짓`)이 필요합니다.

Values that are included directly in the source code are called *literals*. `string` literals are surrounded by double quotes `"..."` or single quotes (`'...'`) -- the only difference is stylistic preference. `number` and `boolean` literals are just presented as is (i.e., `42`, `true`, etc.).
소스 코드에 직접 포함된 값을 *리터럴*이라고 합니다. 문자열` 리터럴은 큰따옴표 `"..."` 또는 작은따옴표(`'...'`)로 둘러싸여 있으며, 유일한 차이점은 문체 선호도입니다. 숫자` 및 `부울` 리터럴은 있는 그대로 표시됩니다(예: `42`, `true` 등).

Consider:
생각해 봅시다:

```js
"I am a string";
'I am also a string';

42;

true;
false;
```

Beyond `string`/`number`/`boolean` value types, it's common for programming languages to provide *arrays*, *objects*, *functions*, and more. We'll cover much more about values and types throughout this chapter and the next.
문자열`/`숫자`/`부울` 값 유형 외에도 프로그래밍 언어에서는 *배열*, *객체*, *함수* 등을 제공하는 것이 일반적입니다. 이 장과 다음 장에서 값과 유형에 대해 더 자세히 다루겠습니다.

### Converting Between Types
### 유형 간 변환

If you have a `number` but need to print it on the screen, you need to convert the value to a `string`, and in JavaScript this conversion is called "coercion." Similarly, if someone enters a series of numeric characters into a form on an ecommerce page, that's a `string`, but if you need to then use that value to do math operations, you need to *coerce* it to a `number`.
'숫자'가 있지만 화면에 인쇄해야 하는 경우 값을 '문자열'로 변환해야 하며, 자바스크립트에서는 이러한 변환을 "강제"라고 합니다. 마찬가지로 누군가 전자상거래 페이지의 양식에 일련의 숫자 문자를 입력하면 이는 '문자열'이지만, 이 값을 사용하여 수학 연산을 수행해야 하는 경우 이를 '숫자'로 '강제'해야 합니다.

JavaScript provides several different facilities for forcibly coercing between *types*. For example:
자바스크립트에서는 *유형*을 강제로 변환하기 위한 여러 가지 기능을 제공합니다. 예를 들어

```js
var a = "42";
var b = Number( a );

console.log( a );	// "42"
console.log( b );	// 42
```

Using `Number(..)` (a built-in function) as shown is an *explicit* coercion from any other type to the `number` type. That should be pretty straightforward.
그림과 같이 `Number(..)`(내장 함수)를 사용하는 것은 다른 타입을 `number` 타입으로 *명시적으로* 강제하는 것입니다. 이는 매우 간단합니다.

But a controversial topic is what happens when you try to compare two values that are not already of the same type, which would require *implicit* coercion.
그러나 이미 같은 유형이 아닌 두 값을 비교하려고 할 때 *암시적* 강제가 필요한 경우 어떤 일이 발생하느냐가 논란의 여지가 있는 주제입니다.

When comparing the string `"99.99"` to the number `99.99`, most people would agree they are equivalent. But they're not exactly the same, are they? It's the same value in two different representations, two different *types*. You could say they're "loosely equal," couldn't you?
문자열 `"99.99"`와 숫자 `99.99`를 비교할 때 대부분의 사람들은 둘이 같다는 데 동의할 것입니다. 하지만 정확히 같지는 않죠? 두 개의 다른 표현, 두 개의 다른 *유형*에서 동일한 값입니다. '느슨하게 동일하다'고 말할 수 있지 않을까요?

To help you out in these common situations, JavaScript will sometimes kick in and *implicitly* coerce values to the matching types.
이러한 일반적인 상황에서 사용자를 돕기 위해 자바스크립트는 때때로 *암시적으로* 값을 일치하는 유형으로 강제합니다.

So if you use the `==` loose equals operator to make the comparison `"99.99" == 99.99`, JavaScript will convert the left-hand side `"99.99"` to its `number` equivalent `99.99`. The comparison then becomes `99.99 == 99.99`, which is of course `true`.
예를 들어 `==` 느슨한 등호 연산자를 사용하여 `"99.99" == 99.99`를 비교하면 JavaScript는 왼쪽 `"99.99"`를 `숫자`에 해당하는 `99.99`로 변환합니다. 그러면 비교는 `99.99 == 99.99`가 되며, 이는 당연히 `참`이 됩니다.

While designed to help you, implicit coercion can create confusion if you haven't taken the time to learn the rules that govern its behavior. Most JS developers never have, so the common feeling is that implicit coercion is confusing and harms programs with unexpected bugs, and should thus be avoided. It's even sometimes called a flaw in the design of the language.
암시적 강제는 사용자를 돕기 위해 설계되었지만, 그 동작을 지배하는 규칙을 학습하는 데 시간을 할애하지 않으면 혼란을 야기할 수 있습니다. 대부분의 JS 개발자는 그런 경험이 없기 때문에 암시적 강제는 혼란을 야기하고 예기치 않은 버그로 프로그램에 해를 끼치므로 피해야 한다는 것이 일반적인 생각입니다. 심지어 언어 설계의 결함이라고도 불립니다.

However, implicit coercion is a mechanism that *can be learned*, and moreover *should be learned* by anyone wishing to take JavaScript programming seriously. Not only is it not confusing once you learn the rules, it can actually make your programs better! The effort is well worth it.
하지만 암시적 강제는 자바스크립트 프로그래밍을 진지하게 배우고자 하는 사람이라면 누구나 '배울 수 있는' 메커니즘이며, 더 나아가 '배워야만 하는' 메커니즘입니다. 일단 규칙을 익히면 혼란스럽지 않을 뿐만 아니라 실제로 프로그램을 더 잘 만들 수 있습니다! 그만한 노력은 충분히 가치가 있습니다.

**Note:** For more information on coercion, see Chapter 2 of this title and Chapter 4 of the *Types & Grammar* title of this series.
**참고: **강제성에 대한 자세한 내용은 이 글의 2장과 이 시리즈의 *유형과 문법* 글의 4장을 참조하세요.

## Code Comments
## 코드 코멘트

The phone store employee might jot down some notes on the features of a newly released phone or on the new plans her company offers. These notes are only for the employee -- they're not for customers to read. Nevertheless, these notes help the employee do her job better by documenting the hows and whys of what she should tell customers.
휴대폰 매장 직원은 새로 출시된 휴대폰의 기능이나 회사에서 제공하는 새로운 요금제에 대해 몇 가지 메모를 적을 수 있습니다. 이 메모는 직원만 볼 수 있고 고객이 읽을 수 없습니다. 그럼에도 불구하고 이러한 메모는 고객에게 설명해야 할 내용과 그 이유를 문서화함으로써 직원이 업무를 더 잘 수행하는 데 도움이 됩니다.

One of the most important lessons you can learn about writing code is that it's not just for the computer. Code is every bit as much, if not more, for the developer as it is for the compiler.
코드 작성에 대해 배울 수 있는 가장 중요한 교훈 중 하나는 코드가 컴퓨터만을 위한 것이 아니라는 것입니다. 코드는 컴파일러만큼이나 개발자를 위한 것이기도 합니다.

Your computer only cares about machine code, a series of binary 0s and 1s, that comes from *compilation*. There's a nearly infinite number of programs you could write that yield the same series of 0s and 1s. The choices you make about how to write your program matter -- not only to you, but to your other team members and even to your future self.
컴퓨터는 *컴파일*을 통해 생성되는 일련의 이진 0과 1로 이루어진 기계어 코드에만 관심을 갖습니다. 동일한 0과 1의 연속을 생성하는 프로그램은 거의 무한대에 가깝게 작성할 수 있습니다. 프로그램을 작성하는 방법에 대한 선택은 본인뿐만 아니라 다른 팀원, 심지어 미래의 자신에게까지 중요한 영향을 미칩니다.

You should strive not just to write programs that work correctly, but programs that make sense when examined. You can go a long way in that effort by choosing good names for your variables (see "Variables") and functions (see "Functions").
올바르게 작동하는 프로그램뿐만 아니라 검사했을 때 의미가 있는 프로그램을 작성하기 위해 노력해야 합니다. 변수('변수' 참조)와 함수('함수' 참조)의 이름을 잘 선택하면 이러한 노력에 큰 도움이 될 수 있습니다.

But another important part is code comments. These are bits of text in your program that are inserted purely to explain things to a human. The interpreter/compiler will always ignore these comments.
하지만 또 다른 중요한 부분은 코드 주석입니다. 코드 코멘트는 순전히 사람에게 설명하기 위해 삽입된 프로그램 내 텍스트 조각입니다. 인터프리터/컴파일러는 항상 이러한 주석을 무시합니다.

There are lots of opinions on what makes well-commented code; we can't really define absolute universal rules. But some observations and guidelines are quite useful:
주석이 잘 달린 코드에 대한 의견은 다양하기 때문에 절대적인 보편적 규칙을 정의할 수는 없습니다. 하지만 몇 가지 관찰과 가이드라인은 꽤 유용합니다:

* Code without comments is suboptimal.
* Too many comments (one per line, for example) is probably a sign of poorly written code.
* Comments should explain *why*, not *what*. They can optionally explain *how* if that's particularly confusing.
* 주석이 없는 코드는 차선책입니다.
* 주석이 너무 많으면(예를 들어 한 줄에 하나씩) 코드가 잘못 작성되었다는 신호일 수 있습니다.
* 코멘트는 *왜*가 아니라 *무엇*을 설명해야 합니다. 특히 혼란스러운 경우 선택적으로 *방법*을 설명할 수 있습니다.

In JavaScript, there are two types of comments possible: a single-line comment and a multiline comment.
JavaScript에는 한 줄 주석과 여러 줄 주석의 두 가지 유형의 주석이 있습니다.

Consider:
생각해 보세요:

```js
// This is a single-line comment

/* But this is
       a multiline
             comment.
                      */
```

The `//` single-line comment is appropriate if you're going to put a comment right above a single statement, or even at the end of a line. Everything on the line after the `//` is treated as the comment (and thus ignored by the compiler), all the way to the end of the line. There's no restriction to what can appear inside a single-line comment.
한 줄 주석은 단일 문 바로 위나 한 줄 끝에 주석을 넣으려는 경우에 적합합니다. '//` 이후 줄에 있는 모든 내용은 주석으로 취급되어 컴파일러에서 줄 끝까지 무시됩니다. 한 줄 주석 안에 표시할 수 있는 내용에는 제한이 없습니다.

Consider:
생각해 보세요:

```js
var a = 42;		// 42 is the meaning of life
```

The `/* .. */` multiline comment is appropriate if you have several lines worth of explanation to make in your comment.
'/* .. */` 여러 줄 코멘트는 댓글에 여러 줄에 걸쳐 설명할 내용이 있는 경우에 적합합니다.

Here's a common usage of multiline comments:
다음은 여러 줄 코멘트의 일반적인 사용 예시입니다:

```js
/* The following value is used because
   it has been shown that it answers
   every question in the universe. */
var a = 42;
```

It can also appear anywhere on a line, even in the middle of a line, because the `*/` ends it. For example:
또한 `*/`로 끝내기 때문에 줄의 어느 곳에나 표시할 수 있으며, 심지어 줄의 중간에도 표시할 수 있습니다. 예를 들어

```js
var a = /* arbitrary value */ 42;

console.log( a );	// 42
```

The only thing that cannot appear inside a multiline comment is a `*/`, because that would be interpreted to end the comment.
여러 줄의 주석 안에 표시할 수 없는 유일한 것은 `*/`인데, 이는 주석을 끝내는 것으로 해석되기 때문입니다.

You will definitely want to begin your learning of programming by starting off with the habit of commenting code. Throughout the rest of this chapter, you'll see I use comments to explain things, so do the same in your own practice. Trust me, everyone who reads your code will thank you!
코드에 주석을 다는 습관을 들이는 것부터 프로그래밍 학습을 시작하고 싶을 것입니다. 이 장의 나머지 부분에서는 제가 주석을 사용해 설명하는 것을 볼 수 있으니 여러분도 실습할 때 똑같이 해보세요. 여러분의 코드를 읽는 모든 사람이 고마워할 것입니다!

## Variables
## 변수

Most useful programs need to track a value as it changes over the course of the program, undergoing different operations as called for by your program's intended tasks.
대부분의 유용한 프로그램은 프로그램이 진행되는 동안 프로그램의 의도된 작업에 따라 다양한 연산을 거치면서 값이 변하는 것을 추적해야 합니다.

The easiest way to go about that in your program is to assign a value to a symbolic container, called a *variable* -- so called because the value in this container can *vary* over time as needed.
프로그램에서 이를 수행하는 가장 쉬운 방법은 *변수*라고 하는 기호 컨테이너에 값을 할당하는 것입니다. 이 컨테이너의 값은 필요에 따라 시간이 지남에 따라 *변할 수 있으므로 *변수*라고 부릅니다.

In some programming languages, you declare a variable (container) to hold a specific type of value, such as `number` or `string`. *Static typing*, otherwise known as *type enforcement*, is typically cited as a benefit for program correctness by preventing unintended value conversions.
일부 프로그래밍 언어에서는 '숫자' 또는 '문자열'과 같은 특정 유형의 값을 저장하기 위해 변수(컨테이너)를 선언합니다. *유형 강제 적용*이라고도 하는 *정적 타이핑*은 일반적으로 의도하지 않은 값 변환을 방지하여 프로그램의 정확성을 높이는 이점으로 꼽힙니다.

Other languages emphasize types for values instead of variables. *Weak typing*, otherwise known as *dynamic typing*, allows a variable to hold any type of value at any time. It's typically cited as a benefit for program flexibility by allowing a single variable to represent a value no matter what type form that value may take at any given moment in the program's logic flow.
다른 언어에서는 변수 대신 값의 유형을 강조합니다. *동적 타이핑*이라고도 하는 *약형 타이핑*은 변수가 언제든지 모든 유형의 값을 보유할 수 있도록 허용합니다. 이는 일반적으로 프로그램의 논리 흐름에서 특정 시점에 값이 어떤 타입을 취하든 단일 변수가 값을 나타낼 수 있게 함으로써 프로그램의 유연성을 높이는 이점으로 꼽힙니다.

JavaScript uses the latter approach, *dynamic typing*, meaning variables can hold values of any *type* without any *type* enforcement.
자바스크립트는 후자의 접근 방식인 *동적 타이핑*을 사용하므로, 변수는 *유형* 강제 적용 없이 모든 *유형*의 값을 보유할 수 있습니다.

As mentioned earlier, we declare a variable using the `var` statement -- notice there's no other *type* information in the declaration. Consider this simple program:
앞서 언급했듯이 `var` 문을 사용하여 변수를 선언하는데, 이 선언에는 다른 *유형* 정보가 없습니다. 이 간단한 프로그램을 살펴봅시다:

```js
var amount = 99.99;

amount = amount * 2;

console.log( amount );		// 199.98

// convert `amount` to a string, and
// add "$" on the beginning
amount = "$" + String( amount );

console.log( amount );		// "$199.98"
```

The `amount` variable starts out holding the number `99.99`, and then holds the `number` result of `amount * 2`, which is `199.98`.
금액` 변수는 처음에 숫자 `99.99`를 담고 있다가 `금액 * 2`의 결과인 `199.98`을 담고 있습니다.

The first `console.log(..)` command has to *implicitly* coerce that `number` value to a `string` to print it out.
첫 번째 `console.log(..)` 명령은 이 `number` 값을 `string`으로 강제 변환하여 출력해야 합니다.

Then the statement `amount = "$" + String(amount)` *explicitly* coerces the `199.98` value to a `string` and adds a `"$"` character to the beginning. At this point, `amount` now holds the `string` value `"$199.98"`, so the second `console.log(..)` statement doesn't need to do any coercion to print it out.
그런 다음 `amount = "$" + String(amount)` 문은 `199.98` 값을 `string`으로 강제 변환하고 시작 부분에 `"$"` 문자를 추가합니다. 이 시점에서 `amount`는 이제 `string` 값 `"$199.98"`을 보유하므로 두 번째 `console.log(..)` 문에서 강제로 출력할 필요가 없습니다.

JavaScript developers will note the flexibility of using the `amount` variable for each of the `99.99`, `199.98`, and the `"$199.98"` values. Static-typing enthusiasts would prefer a separate variable like `amountStr` to hold the final `"$199.98"` representation of the value, because it's a different type.
자바스크립트 개발자는 `99.99`, `199.98` 및 `"$199.98"` 값 각각에 대해 `amount` 변수를 사용할 수 있는 유연성에 주목할 것입니다. 정적 타이핑에 익숙한 사용자라면 최종 `"$199.98"` 값은 다른 유형이기 때문에 `amountStr`과 같은 별도의 변수를 사용하는 것을 선호할 것입니다.

Either way, you'll note that `amount` holds a running value that changes over the course of the program, illustrating the primary purpose of variables: managing program *state*.
어느 쪽이든, `amount`는 프로그램이 실행되는 동안 변경되는 실행 값을 보유하며 변수의 주요 목적인 프로그램 *상태*를 관리한다는 것을 알 수 있습니다.

In other words, *state* is tracking the changes to values as your program runs.
다시 말해, *state*는 프로그램이 실행되는 동안 값의 변화를 추적합니다.

Another common usage of variables is for centralizing value setting. This is more typically called *constants*, when you declare a variable with a value and intend for that value to *not change* throughout the program.
변수의 또 다른 일반적인 용도는 값 설정을 중앙 집중화하는 것입니다. 이를 일반적으로 *상수*라고 하는데, 값을 가진 변수를 선언하고 프로그램 전체에서 해당 값이 *변하지 않도록* 하려는 경우입니다.

You declare these *constants*, often at the top of a program, so that it's convenient for you to have one place to go to alter a value if you need to. By convention, JavaScript variables as constants are usually capitalized, with underscores `_` between multiple words.
이러한 *상수*를 프로그램 맨 위에 선언하면 필요할 때 한 곳에서 값을 변경할 수 있어 편리합니다. 일반적으로 자바스크립트 변수는 대문자로 표기하며, 여러 단어 사이에는 밑줄 `_`을 사용합니다.

Here's a silly example:
다음은 간단한 예시입니다:

```js
var TAX_RATE = 0.08;	// 8% sales tax

var amount = 99.99;

amount = amount * 2;

amount = amount + (amount * TAX_RATE);

console.log( amount );				// 215.9784
console.log( amount.toFixed( 2 ) );	// "215.98"
```

**Note:** Similar to how `console.log(..)` is a function `log(..)` accessed as an object property on the `console` value, `toFixed(..)` here is a function that can be accessed on `number` values. JavaScript `number`s aren't automatically formatted for dollars -- the engine doesn't know what your intent is and there's no type for currency. `toFixed(..)` lets us specify how many decimal places we'd like the `number` rounded to, and it produces the `string` as necessary.
**참고: `console.log(..)`가 `console` 값에서 객체 속성으로 접근하는 함수 `log(..)`인 것과 유사하게, 여기서 `toFixed(..)`는 `number` 값에서 접근할 수 있는 함수입니다. 자바스크립트 `number`는 자동으로 달러로 포맷되지 않습니다. 엔진은 사용자의 의도를 알 수 없고 통화에 대한 유형이 없기 때문입니다. toFixed(..)`를 사용하면 `number`를 소수점 이하 몇 자리까지 반올림할지 지정할 수 있으며, 필요에 따라 `string`을 생성합니다.

The `TAX_RATE` variable is only *constant* by convention -- there's nothing special in this program that prevents it from being changed. But if the city raises the sales tax rate to 9%, we can still easily update our program by setting the `TAX_RATE` assigned value to `0.09` in one place, instead of finding many occurrences of the value `0.08` strewn throughout the program and updating all of them.
이 프로그램에서는 이 변수를 변경할 수 없는 특별한 이유가 없기 때문에 `TAX_RATE` 변수는 관례상 *상수*일 뿐입니다. 그러나 시에서 판매 세율을 9%로 인상하는 경우 프로그램 전체에 흩어져 있는 `0.08` 값을 찾아서 모두 업데이트하는 대신 `TAX_RATE` 할당 값을 `0.09`로 한 곳에 설정하면 프로그램을 쉽게 업데이트할 수 있습니다.

The newest version of JavaScript at the time of this writing (commonly called "ES6") includes a new way to declare *constants*, by using `const` instead of `var`:
이 글을 쓰는 시점의 최신 자바스크립트 버전(일반적으로 "ES6"라고 함)에는 `var` 대신 `const`를 사용하여 *상수*를 선언하는 새로운 방법이 포함되어 있습니다:

```js
// as of ES6:
const TAX_RATE = 0.08;

var amount = 99.99;

// ..
```

Constants are useful just like variables with unchanged values, except that constants also prevent accidentally changing value somewhere else after the initial setting. If you tried to assign any different value to `TAX_RATE` after that first declaration, your program would reject the change (and in strict mode, fail with an error -- see "Strict Mode" in Chapter 2).
상수는 값이 변경되지 않는 변수와 마찬가지로 유용하지만, 상수는 초기 설정 이후 다른 곳에서 실수로 값을 변경하는 것을 방지한다는 점이 다릅니다. 첫 번째 선언 이후에 `TAX_RATE`에 다른 값을 할당하려고 하면 프로그램이 변경을 거부합니다(엄격 모드에서는 오류와 함께 실패합니다 - 2장의 "엄격 모드" 참조).

By the way, that kind of "protection" against mistakes is similar to the static-typing type enforcement, so you can see why static types in other languages can be attractive!
그런데 실수에 대한 이러한 종류의 '보호'는 정적 타입의 타입 강제 적용과 유사하므로 다른 언어의 정적 타입이 왜 매력적인지 알 수 있습니다!

**Note:** For more information about how different values in variables can be used in your programs, see the *Types & Grammar* title of this series.
**참고: **주: 프로그램에서 변수의 다양한 값을 사용하는 방법에 대한 자세한 내용은 이 시리즈의 *타입과 문법* 제목을 참조하세요.

## Blocks
## 블록

The phone store employee must go through a series of steps to complete the checkout as you buy your new phone.
휴대폰 매장 직원은 사용자가 새 휴대폰을 구매할 때 결제를 완료하기 위해 일련의 단계를 거쳐야 합니다.

Similarly, in code we often need to group a series of statements together, which we often call a *block*. In JavaScript, a block is defined by wrapping one or more statements inside a curly-brace pair `{ .. }`. Consider:
마찬가지로 코드에서도 일련의 문을 함께 그룹화해야 하는 경우가 많은데, 이를 흔히 *블록*이라고 부릅니다. JavaScript에서 블록은 중괄호 쌍 `{ ... }`. 생각해 봅시다:

```js
var amount = 99.99;

// a general block
{
	amount = amount * 2;
	console.log( amount );	// 199.98
}
```

This kind of standalone `{ .. }` general block is valid, but isn't as commonly seen in JS programs. Typically, blocks are attached to some other control statement, such as an `if` statement (see "Conditionals") or a loop (see "Loops"). For example:
이런 종류의 독립형 `{ ... }` 일반 블록은 유효하지만 JS 프로그램에서 흔히 볼 수 있는 것은 아닙니다. 일반적으로 블록은 `if` 문("조건문" 참조) 또는 루프("루프" 참조)와 같은 다른 제어 문에 첨부됩니다. 예를 들어

```js
var amount = 99.99;

// is amount big enough?
if (amount > 10) {			// <-- block attached to `if`
	amount = amount * 2;
	console.log( amount );	// 199.98
}
```

We'll explain `if` statements in the next section, but as you can see, the `{ .. }` block with its two statements is attached to `if (amount > 10)`; the statements inside the block will only be processed if the conditional passes.
다음 섹션에서 `if` 문에 대해 설명하겠지만, 보시다시피 두 개의 문이 있는 `{ ... }` 블록이 붙어 있습니다. }` 블록은 두 개의 문이 `if (amount > 10)`에 붙어 있으며, 블록 안의 문은 조건이 통과할 때만 처리됩니다.

**Note:** Unlike most other statements like `console.log(amount);`, a block statement does not need a semicolon (`;`) to conclude it.
**참고: `console.log(amount);`와 같은 대부분의 다른 문과 달리, 블록 문은 세미콜론(`;`)으로 끝낼 필요가 없습니다.

## Conditionals
## 조건부

"Do you want to add on the extra screen protectors to your purchase, for $9.99?" The helpful phone store employee has asked you to make a decision. And you may need to first consult the current *state* of your wallet or bank account to answer that question. But obviously, this is just a simple "yes or no" question.
"구매 시 화면 보호기를 9.99달러에 추가하시겠습니까?" 친절한 휴대폰 매장 직원이 결정을 내려달라고 요청했습니다. 이 질문에 답하려면 먼저 지갑이나 은행 계좌의 현재 *상태*를 확인해야 할 수도 있습니다. 하지만 분명히 이것은 단순한 "예, 아니오" 질문일 뿐입니다.

There are quite a few ways we can express *conditionals* (aka decisions) in our programs.
프로그램에서 *조건*(일명 결정)을 표현할 수 있는 방법은 꽤 많이 있습니다.

The most common one is the `if` statement. Essentially, you're saying, "*If* this condition is true, do the following...". For example:
가장 일반적인 것은 `if` 문입니다. 기본적으로 "*이 조건이 참이면* 다음을 수행하십시오..."라고 말하는 것입니다. 예를 들어

```js
var bank_balance = 302.13;
var amount = 99.99;

if (amount < bank_balance) {
	console.log( "I want to buy this phone!" );
}
```

The `if` statement requires an expression in between the parentheses `( )` that can be treated as either `true` or `false`. In this program, we provided the expression `amount < bank_balance`, which indeed will either evaluate to `true` or `false` depending on the amount in the `bank_balance` variable.
if` 문은 괄호 '( )` 사이에 `참` 또는 `거짓`으로 취급될 수 있는 표현식을 넣어야 합니다. 이 프로그램에서는 `금액 <은행 잔액`이라는 표현식을 제공했는데, 이 표현식은 실제로 `은행 잔액` 변수의 금액에 따라 `참` 또는 `거짓`으로 평가됩니다.

You can even provide an alternative if the condition isn't true, called an `else` clause. Consider:
조건이 참이 아닌 경우 `else` 절이라는 대안을 제공할 수도 있습니다. 생각해 봅시다:

```js
const ACCESSORY_PRICE = 9.99;

var bank_balance = 302.13;
var amount = 99.99;

amount = amount * 2;

// can we afford the extra purchase?
if ( amount < bank_balance ) {
	console.log( "I'll take the accessory!" );
	amount = amount + ACCESSORY_PRICE;
}
// otherwise:
else {
	console.log( "No, thanks." );
}
```

Here, if `amount < bank_balance` is `true`, we'll print out `"I'll take the accessory!"` and add the `9.99` to our `amount` variable. Otherwise, the `else` clause says we'll just politely respond with `"No, thanks."` and leave `amount` unchanged.
여기서 `amount < bank_balance`가 `true`이면 `"액세서리를 가져가겠습니다!"`를 출력하고 `amount` 변수에 `9.99`를 추가합니다. 그렇지 않으면 `else` 절을 통해 `아니요, 감사합니다`로 정중하게 응답하고 `amount`를 변경하지 않습니다.

As we discussed in "Values & Types" earlier, values that aren't already of an expected type are often coerced to that type. The `if` statement expects a `boolean`, but if you pass it something that's not already `boolean`, coercion will occur.
앞서 '값과 타입'에서 설명한 것처럼, 예상되는 타입이 아닌 값은 종종 해당 타입으로 강제로 지정됩니다. 만약` 문은 `부울`을 기대하지만, 아직 `부울`이 아닌 것을 전달하면 강제성이 발생합니다.

JavaScript defines a list of specific values that are considered "falsy" because when coerced to a `boolean`, they become `false` -- these include values like `0` and `""`. Any other value not on the "falsy" list is automatically "truthy" -- when coerced to a `boolean` they become `true`. Truthy values include things like `99.99` and `"free"`. See "Truthy & Falsy" in Chapter 2 for more information.
자바스크립트는 `부울`로 강제 처리되면 `거짓`이 되기 때문에 `거짓`으로 간주되는 특정 값의 목록을 정의하며, 여기에는 `0` 및 `""`과 같은 값이 포함됩니다. "거짓" 목록에 없는 다른 값은 자동으로 "진실"로 간주되며, `부울`로 강제로 지정하면 `참`이 됩니다. 진실한 값에는 `99.99` 및 `"free"`와 같은 것이 포함됩니다. 자세한 내용은 2장의 "진실과 거짓"을 참조하십시오.

*Conditionals* exist in other forms besides the `if`. For example, the `switch` statement can be used as a shorthand for a series of `if..else` statements (see Chapter 2). Loops (see "Loops") use a *conditional* to determine if the loop should keep going or stop.
*조건문은 `if` 외에 다른 형태로도 존재합니다. 예를 들어, `switch` 문은 일련의 `if..else` 문에 대한 약어로 사용할 수 있습니다(2장 참조). 루프("루프" 참조)는 *조건부*를 사용하여 루프를 계속 진행할지 아니면 중지할지를 결정합니다.

**Note:** For deeper information about the coercions that can occur implicitly in the test expressions of *conditionals*, see Chapter 4 of the *Types & Grammar* title of this series.
**참고: *조건문*의 테스트 표현식에서 암시적으로 발생할 수 있는 강제에 대한 자세한 내용은 이 시리즈의 *유형 및 문법* 제목의 4장을 참조하세요.

## Loops
## 루프

During busy times, there's a waiting list for customers who need to speak to the phone store employee. While there's still people on that list, she just needs to keep serving the next customer.
바쁜 시간대에는 전화 매장 직원과 통화해야 하는 고객의 대기 명단이 있습니다. 대기자 명단에 고객이 남아 있는 동안 직원은 다음 고객에게 계속 서비스를 제공해야 합니다.

Repeating a set of actions until a certain condition fails -- in other words, repeating only while the condition holds -- is the job of programming loops; loops can take different forms, but they all satisfy this basic behavior.
특정 조건이 충족될 때까지 일련의 동작을 반복하는 것, 즉 조건이 유지되는 동안에만 반복하는 것이 루프를 프로그래밍하는 일이며, 루프는 다양한 형태를 취할 수 있지만 모두 이 기본 동작을 충족합니다.

A loop includes the test condition as well as a block (typically as `{ .. }`). Each time the loop block executes, that's called an *iteration*.
루프에는 테스트 조건과 블록(일반적으로 `{ .. }`)이 포함됩니다. 루프 블록이 실행될 때마다 이를 *이터레이션*이라고 합니다.

For example, the `while` loop and the `do..while` loop forms illustrate the concept of repeating a block of statements until a condition no longer evaluates to `true`:
예를 들어, `while` 루프와 `do..while` 루프 형식은 조건이 더 이상 `true`로 평가되지 않을 때까지 문 블록을 반복하는 개념을 설명합니다:

```js
while (numOfCustomers > 0) {
	console.log( "How may I help you?" );

	// help the customer...

	numOfCustomers = numOfCustomers - 1;
}

// versus:

do {
	console.log( "How may I help you?" );

	// help the customer...

	numOfCustomers = numOfCustomers - 1;
} while (numOfCustomers > 0);
```

The only practical difference between these loops is whether the conditional is tested before the first iteration (`while`) or after the first iteration (`do..while`).
이러한 루프 간의 유일한 실질적인 차이점은 조건이 첫 번째 반복 전에 테스트되는지(`while`), 첫 번째 반복 후에 테스트되는지(`do..while`) 여부입니다.

In either form, if the conditional tests as `false`, the next iteration will not run. That means if the condition is initially `false`, a `while` loop will never run, but a `do..while` loop will run just the first time.
어떤 형태든 조건이 `false`로 테스트되면 다음 반복은 실행되지 않습니다. 즉, 조건이 처음에 `false`인 경우 `while` 루프는 실행되지 않지만 `do..while` 루프는 처음 한 번만 실행됩니다.

Sometimes you are looping for the intended purpose of counting a certain set of numbers, like from `0` to `9` (ten numbers). You can do that by setting a loop iteration variable like `i` at value `0` and incrementing it by `1` each iteration.
때로는 `0`에서 `9`(숫자 10개)까지와 같이 특정 숫자 집합을 세는 의도된 목적으로 루프를 실행할 수 있습니다. 이 경우 `i`와 같은 루프 반복 변수를 값 `0`으로 설정하고 반복할 때마다 `1`씩 증가시키면 됩니다.

**Warning:** For a variety of historical reasons, programming languages almost always count things in a zero-based fashion, meaning starting with `0` instead of `1`. If you're not familiar with that mode of thinking, it can be quite confusing at first. Take some time to practice counting starting with `0` to become more comfortable with it!
**경고:** 역사적으로 다양한 이유로 인해 프로그래밍 언어는 거의 항상 `1`이 아닌 `0`으로 시작하는 0 기반 방식으로 숫자를 계산합니다. 이러한 사고 방식에 익숙하지 않다면 처음에는 상당히 혼란스러울 수 있습니다. 시간을 들여 `0`으로 시작하는 수 세기를 연습하여 익숙해지도록 하세요!

The conditional is tested on each iteration, much as if there is an implied `if` statement inside the loop.
조건문은 마치 루프 안에 암시적인 `if` 문이 있는 것처럼 각 반복마다 테스트됩니다.

We can use JavaScript's `break` statement to stop a loop. Also, we can observe that it's awfully easy to create a loop that would otherwise run forever without a `break`ing mechanism.
자바스크립트의 `break` 문을 사용하여 루프를 중지할 수 있습니다. 또한, `break` 메커니즘이 없으면 영원히 실행되는 루프를 만드는 것이 매우 쉽다는 것을 알 수 있습니다.

Let's illustrate:
예를 들어 보겠습니다:

```js
var i = 0;

// a `while..true` loop would run forever, right?
while (true) {
	// stop the loop?
	if ((i <= 9) === false) {
		break;
	}

	console.log( i );
	i = i + 1;
}
// 0 1 2 3 4 5 6 7 8 9
```

**Warning:** This is not necessarily a practical form you'd want to use for your loops. It's presented here for illustration purposes only.
**경고:** 이 형태가 반드시 루프에 사용해야 하는 실용적인 형태는 아닙니다. 여기서는 설명 목적으로만 제공됩니다.

While a `while` (or `do..while`) can accomplish the task manually, there's another syntactic form called a `for` loop for just that purpose:
동안`(또는 `do..while`)으로 수동으로 작업을 수행할 수 있지만, 이러한 용도로만 사용할 수 있는 `for` 루프라는 구문 형식이 또 있습니다:

```js
for (var i = 0; i <= 9; i = i + 1) {
	console.log( i );
}
// 0 1 2 3 4 5 6 7 8 9
```

As you can see, in both cases the conditional `i <= 9` is `true` for the first 10 iterations (`i` of values `0` through `9`) of either loop form, but becomes `false` once `i` is value `10`.
보시다시피, 두 경우 모두 조건부 `i <= 9`는 두 루프 형식의 처음 10번의 반복(`0`부터 `9`까지의 값 중 `i`)에 대해서는 `참`이지만, `i`가 `10` 값이 되면 `거짓`이 됩니다.

The `for` loop has three clauses: the initialization clause (`var i=0`), the conditional test clause (`i <= 9`), and the update clause (`i = i + 1`). So if you're going to do counting with your loop iterations, `for` is a more compact and often easier form to understand and write.
for` 루프에는 초기화 절(`var i=0`), 조건부 테스트 절(`i <= 9`), 업데이트 절(`i = i + 1`)의 세 가지 절이 있습니다. 따라서 루프 반복문으로 계산을 수행하려는 경우 `for`가 더 간결하고 이해하기 쉽고 작성하기 쉬운 형태입니다.

There are other specialized loop forms that are intended to iterate over specific values, such as the properties of an object (see Chapter 2) where the implied conditional test is just whether all the properties have been processed. The "loop until a condition fails" concept holds no matter what the form of the loop.
개체의 속성(2장 참조)과 같이 특정 값을 반복하기 위한 다른 특수 루프 형식도 있는데, 여기서 암시된 조건부 테스트는 모든 속성이 처리되었는지 여부일 뿐입니다. "조건이 실패할 때까지 반복"이라는 개념은 루프의 형태와 상관없이 적용됩니다.

## Functions
## 기능

The phone store employee probably doesn't carry around a calculator to figure out the taxes and final purchase amount. That's a task she needs to define once and reuse over and over again. Odds are, the company has a checkout register (computer, tablet, etc.) with those "functions" built in.
휴대폰 매장 직원은 세금과 최종 구매 금액을 계산하기 위해 계산기를 들고 다니지 않을 것입니다. 한 번만 정의하고 반복해서 재사용해야 하는 작업이기 때문입니다. 회사에서 이러한 '기능'이 내장된 계산대(컴퓨터, 태블릿 등)를 보유하고 있을 가능성이 높습니다.

Similarly, your program will almost certainly want to break up the code's tasks into reusable pieces, instead of repeatedly repeating yourself repetitiously (pun intended!). The way to do this is to define a `function`.
마찬가지로, 프로그램도 코드의 작업을 반복적으로 반복하는 대신 재사용 가능한 부분으로 나누고 싶을 것입니다(말장난입니다!). 이를 위한 방법은 '함수'를 정의하는 것입니다.

A function is generally a named section of code that can be "called" by name, and the code inside it will be run each time. Consider:
함수는 일반적으로 이름으로 '호출'할 수 있는 명명된 코드 섹션으로, 그 안에 있는 코드가 매번 실행됩니다. 생각해 보세요:

```js
function printAmount() {
	console.log( amount.toFixed( 2 ) );
}

var amount = 99.99;

printAmount(); // "99.99"

amount = amount * 2;

printAmount(); // "199.98"
```

Functions can optionally take arguments (aka parameters) -- values you pass in. And they can also optionally return a value back.
함수는 선택적으로 인자(일명 매개변수), 즉 사용자가 전달하는 값을 받을 수 있습니다. 또한 선택적으로 값을 반환할 수도 있습니다.

```js
function printAmount(amt) {
	console.log( amt.toFixed( 2 ) );
}

function formatAmount() {
	return "$" + amount.toFixed( 2 );
}

var amount = 99.99;

printAmount( amount * 2 );		// "199.98"

amount = formatAmount();
console.log( amount );			// "$99.99"
```

The function `printAmount(..)` takes a parameter that we call `amt`. The function `formatAmount()` returns a value. Of course, you can also combine those two techniques in the same function.
함수 `printAmount(..)`는 `amt`라는 매개변수를 받습니다. 포맷금액()` 함수는 값을 반환합니다. 물론 동일한 함수에서 이 두 가지 기술을 결합할 수도 있습니다.

Functions are often used for code that you plan to call multiple times, but they can also be useful just to organize related bits of code into named collections, even if you only plan to call them once.
함수는 여러 번 호출하려는 코드에 자주 사용되지만, 한 번만 호출하려는 경우에도 관련 코드 비트를 명명된 컬렉션으로 구성하는 데 유용할 수 있습니다.

Consider:
생각해 보세요:

```js
const TAX_RATE = 0.08;

function calculateFinalPurchaseAmount(amt) {
	// calculate the new amount with the tax
	amt = amt + (amt * TAX_RATE);

	// return the new amount
	return amt;
}

var amount = 99.99;

amount = calculateFinalPurchaseAmount( amount );

console.log( amount.toFixed( 2 ) );		// "107.99"
```

Although `calculateFinalPurchaseAmount(..)` is only called once, organizing its behavior into a separate named function makes the code that uses its logic (the `amount = calculateFinal...` statement) cleaner. If the function had more statements in it, the benefits would be even more pronounced.
계산 최종 구매 금액(..)`은 한 번만 호출되지만, 그 동작을 별도의 명명된 함수로 구성하면 해당 논리(`amount = 계산 최종...` 문)를 사용하는 코드가 더 깔끔해집니다. 함수에 더 많은 문이 포함되어 있다면 이점은 훨씬 더 두드러질 것입니다.

### Scope
### 범위

If you ask the phone store employee for a phone model that her store doesn't carry, she will not be able to sell you the phone you want. She only has access to the phones in her store's inventory. You'll have to try another store to see if you can find the phone you're looking for.
휴대폰 매장 직원에게 매장에서 취급하지 않는 휴대폰 모델을 요청하면 해당 직원은 원하는 휴대폰을 판매할 수 없습니다. 직원은 자신의 매장 재고에 있는 휴대폰에만 액세스할 수 있습니다. 원하는 휴대폰을 찾을 수 있는지 확인하려면 다른 매장을 방문해야 합니다.

Programming has a term for this concept: *scope* (technically called *lexical scope*). In JavaScript, each function gets its own scope. Scope is basically a collection of variables as well as the rules for how those variables are accessed by name. Only code inside that function can access that function's *scoped* variables.
프로그래밍에는 이 개념에 대한 용어가 있습니다: *범위*(기술적으로는 *렉시컬 범위*라고 함)라는 용어가 있습니다. 자바스크립트에서는 각 함수가 고유한 범위를 갖습니다. 범위는 기본적으로 변수의 모음이자 변수를 이름으로 액세스하는 방법에 대한 규칙입니다. 해당 함수 내부의 코드만 해당 함수의 *범위* 변수에 액세스할 수 있습니다.

A variable name has to be unique within the same scope -- there can't be two different `a` variables sitting right next to each other. But the same variable name `a` could appear in different scopes.
변수 이름은 동일한 범위 내에서 고유해야 하며, 서로 다른 두 개의 `a` 변수가 바로 옆에 있을 수 없습니다. 그러나 동일한 변수 이름 `a`가 다른 범위에 나타날 수도 있습니다.

```js
function one() {
	// this `a` only belongs to the `one()` function
	var a = 1;
	console.log( a );
}

function two() {
	// this `a` only belongs to the `two()` function
	var a = 2;
	console.log( a );
}

one();		// 1
two();		// 2
```

Also, a scope can be nested inside another scope, just like if a clown at a birthday party blows up one balloon inside another balloon. If one scope is nested inside another, code inside the innermost scope can access variables from either scope.
또한 생일 파티에서 광대가 풍선 하나를 다른 풍선 안에 넣고 터뜨리는 것처럼 스코프는 다른 스코프 안에 중첩될 수 있습니다. 한 범위가 다른 범위 안에 중첩되면 가장 안쪽에 있는 코드에서 두 범위의 변수에 액세스할 수 있습니다.

Consider:
생각해 보세요:

```js
function outer() {
	var a = 1;

	function inner() {
		var b = 2;

		// we can access both `a` and `b` here
		console.log( a + b );	// 3
	}

	inner();

	// we can only access `a` here
	console.log( a );			// 1
}

outer();
```

Lexical scope rules say that code in one scope can access variables of either that scope or any scope outside of it.
어휘 범위 규칙에 따르면 한 범위의 코드는 해당 범위 또는 범위 외부의 모든 범위에 있는 변수에 액세스할 수 있습니다.

So, code inside the `inner()` function has access to both variables `a` and `b`, but code in `outer()` has access only to `a` -- it cannot access `b` because that variable is only inside `inner()`.
따라서 `inner()` 함수 내부의 코드는 `a`와 `b` 변수에 모두 액세스할 수 있지만 `outer()`의 코드는 `a`에만 액세스할 수 있으며, 해당 변수가 `inner()` 내부에만 있기 때문에 `b`에는 액세스할 수 없습니다.

Recall this code snippet from earlier:
앞서의 이 코드 조각을 기억해 보세요:

```js
const TAX_RATE = 0.08;

function calculateFinalPurchaseAmount(amt) {
	// calculate the new amount with the tax
	amt = amt + (amt * TAX_RATE);

	// return the new amount
	return amt;
}
```

The `TAX_RATE` constant (variable) is accessible from inside the `calculateFinalPurchaseAmount(..)` function, even though we didn't pass it in, because of lexical scope.
어휘 범위 때문에 전달하지 않았더라도 `TAX_RATE` 상수(변수)는 `calculateFinalPurchaseAmount(..)` 함수 내부에서 액세스할 수 있습니다.

**Note:** For more information about lexical scope, see the first three chapters of the *Scope & Closures* title of this series.
**참고: **어휘 범위에 대한 자세한 내용은 이 시리즈의 *범위 및 클로저* 제목의 처음 세 장을 참조하세요.

## Practice
## 연습

There is absolutely no substitute for practice in learning programming. No amount of articulate writing on my part is alone going to make you a programmer.
프로그래밍을 배우는 데 있어 연습을 대신할 수 있는 것은 절대 없습니다. 제가 아무리 명료하게 글을 쓴다고 해서 여러분이 프로그래머가 될 수는 없습니다.

With that in mind, let's try practicing some of the concepts we learned here in this chapter. I'll give the "requirements," and you try it first. Then consult the code listing below to see how I approached it.
이를 염두에 두고 이 장에서 배운 몇 가지 개념을 연습해 봅시다. 제가 '요구 사항'을 제시할 테니 여러분이 먼저 시도해 보세요. 그런 다음 아래 코드 목록을 참조하여 제가 어떻게 접근했는지 확인하세요.

* Write a program to calculate the total price of your phone purchase. You will keep purchasing phones (hint: loop!) until you run out of money in your bank account. You'll also buy accessories for each phone as long as your purchase amount is below your mental spending threshold.
* After you've calculated your purchase amount, add in the tax, then print out the calculated purchase amount, properly formatted.
* Finally, check the amount against your bank account balance to see if you can afford it or not.
* You should set up some constants for the "tax rate," "phone price," "accessory price," and "spending threshold," as well as a variable for your "bank account balance.""
* You should define functions for calculating the tax and for formatting the price with a "$" and rounding to two decimal places.
* **Bonus Challenge:** Try to incorporate input into this program, perhaps with the `prompt(..)` covered in "Input" earlier. You may prompt the user for their bank account balance, for example. Have fun and be creative!
* 휴대폰 구매의 총 가격을 계산하는 프로그램을 작성하세요. 은행 계좌에 돈이 다 떨어질 때까지 휴대폰을 계속 구매합니다(힌트: 반복!). 또한 구매 금액이 정신적 지출 한도 이하인 한 각 휴대폰에 맞는 액세서리를 구매합니다.
* 구매 금액을 계산한 후 세금을 더한 다음 계산된 구매 금액을 적절한 서식으로 인쇄합니다.
* 마지막으로 은행 계좌 잔액과 금액을 비교하여 감당할 수 있는지 확인합니다.
* '세율', '휴대폰 가격', '액세서리 가격', '지출 한도액'에 대한 상수를 설정하고 '은행 계좌 잔액'에 대한 변수를 설정해야 합니다."
* 세금을 계산하고 "$"로 가격 서식을 지정하고 소수점 둘째 자리까지 반올림하는 함수를 정의해야 합니다.
* 보너스 과제: 앞서 '입력'에서 다룬 '프롬프트(..)`를 사용하여 이 프로그램에 입력을 통합해 보세요. 예를 들어 사용자에게 은행 계좌 잔액을 묻는 메시지를 표시할 수 있습니다. 재미있게 창의력을 발휘하세요!

OK, go ahead. Try it. Don't peek at my code listing until you've given it a shot yourself!
자, 시작해 보세요. 해보세요. 직접 해보기 전에는 제 코드 목록을 들여다보지 마세요!

**Note:** Because this is a JavaScript book, I'm obviously going to solve the practice exercise in JavaScript. But you can do it in another language for now if you feel more comfortable.
**참고: 이 책은 자바스크립트 책이기 때문에 연습 문제는 당연히 자바스크립트로 풀 것입니다. 하지만 더 편하다면 지금은 다른 언어로 해도 됩니다.

Here's my JavaScript solution for this exercise:
이 연습을 위한 제 자바스크립트 솔루션은 다음과 같습니다:

```js
const SPENDING_THRESHOLD = 200;
const TAX_RATE = 0.08;
const PHONE_PRICE = 99.99;
const ACCESSORY_PRICE = 9.99;

var bank_balance = 303.91;
var amount = 0;

function calculateTax(amount) {
	return amount * TAX_RATE;
}

function formatAmount(amount) {
	return "$" + amount.toFixed( 2 );
}

// keep buying phones while you still have money
while (amount < bank_balance) {
	// buy a new phone!
	amount = amount + PHONE_PRICE;

	// can we afford the accessory?
	if (amount < SPENDING_THRESHOLD) {
		amount = amount + ACCESSORY_PRICE;
	}
}

// don't forget to pay the government, too
amount = amount + calculateTax( amount );

console.log(
	"Your purchase: " + formatAmount( amount )
);
// Your purchase: $334.76

// can you actually afford this purchase?
if (amount > bank_balance) {
	console.log(
		"You can't afford this purchase. :("
	);
}
// You can't afford this purchase. :(
```

**Note:** The simplest way to run this JavaScript program is to type it into the developer console of your nearest browser.
**참고:** 이 JavaScript 프로그램을 실행하는 가장 간단한 방법은 가까운 브라우저의 개발자 콘솔에 입력하는 것입니다.

How did you do? It wouldn't hurt to try it again now that you've seen my code. And play around with changing some of the constants to see how the program runs with different values.
어떻게 되었나요? 이제 제 코드를 보셨으니 다시 시도해 보셔도 나쁘지 않을 것 같습니다. 그리고 몇 가지 상수를 변경하여 프로그램이 다른 값으로 어떻게 실행되는지 살펴보세요.

## Review
## 리뷰

Learning programming doesn't have to be a complex and overwhelming process. There are just a few basic concepts you need to wrap your head around.
프로그래밍을 배우는 것이 복잡하고 부담스러운 과정일 필요는 없습니다. 몇 가지 기본 개념만 이해하면 됩니다.

These act like building blocks. To build a tall tower, you start first by putting block on top of block on top of block. The same goes with programming. Here are some of the essential programming building blocks:
이러한 개념은 빌딩 블록과 같은 역할을 합니다. 높은 탑을 쌓으려면 먼저 블록을 블록 위에 블록을 쌓는 것부터 시작해야 합니다. 프로그래밍도 마찬가지입니다. 다음은 몇 가지 필수 프로그래밍 빌딩 블록입니다:

* You need *operators* to perform actions on values.
* You need values and *types* to perform different kinds of actions like math on `number`s or output with `string`s.
* You need *variables* to store data (aka *state*) during your program's execution.
* You need *conditionals* like `if` statements to make decisions.
* You need *loops* to repeat tasks until a condition stops being true.
* You need *functions* to organize your code into logical and reusable chunks.
* 값에 대한 작업을 수행하려면 *연산자*가 필요합니다.
* '숫자'로 연산을 하거나 '문자열'로 출력하는 등 다양한 종류의 작업을 수행하려면 값과 *유형*이 필요합니다.
* 프로그램이 실행되는 동안 데이터(일명 *상태*)를 저장하려면 *변수*가 필요합니다.
* 결정을 내리기 위해 `if` 문과 같은 *조건문*이 필요합니다.
* 조건이 참이 될 때까지 작업을 반복하려면 *루프*가 필요합니다.
* 코드를 논리적이고 재사용 가능한 덩어리로 정리하려면 *함수*가 필요합니다.

Code comments are one effective way to write more readable code, which makes your program easier to understand, maintain, and fix later if there are problems.
코드 주석은 더 읽기 쉬운 코드를 작성하는 효과적인 방법 중 하나로, 나중에 문제가 발생했을 때 프로그램을 더 쉽게 이해하고, 유지 관리하고, 수정할 수 있게 해줍니다.

Finally, don't neglect the power of practice. The best way to learn how to write code is to write code.
마지막으로, 연습의 힘을 무시하지 마세요. 코드 작성 방법을 배우는 가장 좋은 방법은 코드를 작성하는 것입니다.

I'm excited you're well on your way to learning how to code, now! Keep it up. Don't forget to check out other beginner programming resources (books, blogs, online training, etc.). This chapter and this book are a great start, but they're just a brief introduction.
지금 코딩을 배우기 위한 여정이 순조롭게 진행되고 계신 것 같아 기쁩니다! 계속해 보세요. 다른 초급 프로그래밍 리소스(책, 블로그, 온라인 교육 등)를 확인하는 것도 잊지 마세요. 이 챕터와 이 책은 좋은 출발점이 되지만 간단한 소개에 불과합니다.

The next chapter will review many of the concepts from this chapter, but from a more JavaScript-specific perspective, which will highlight most of the major topics that are addressed in deeper detail throughout the rest of the series.
다음 장에서는 이 장의 많은 개념을 자바스크립트 특유의 관점에서 검토하고, 나머지 시리즈에서 더 자세히 다룰 대부분의 주요 주제를 강조할 것입니다.