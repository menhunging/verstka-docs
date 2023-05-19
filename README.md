# Правила написания scss(css) и js кода 

В первую очередь устанавливаем "Prettier - Code formatter". С его помощью большая часть требований описанных ниже делается автоматически. 

* БЭМ

Для именования классов рекомендуется использовать [БЭМ-нотацию](https://ru.bem.info/methodology/naming-convention/).

```scss
.block {
    &__element {
        &--modificator {
            // ...
        }
    }
}
```
* Классы состояний

Классы состояний рекомендуется записывать кратко:

```scss
.is-active {
    // ...
}

.is-current {
    // ...
}

.is-open {
    // ...
}

.is-hidden {
    // ...
}
```

## Синтаксис и форматирование

* Не должно быть пробелов в конце строк.

* `!important` используется только для того, чтобы перебить значение `style`-атрибута.

* В коде не должно быть вендорных префиксов. Если это SCSS, если же SCSS код не используется в проекте, то использование вендорных префиксов допускается. Иначе выноси это все в @mixin

* Селекторы, свойства, `@`-правила, названия переменных, миксин, функций, `#`-цвета — все записывается в нижнем регистре.

**Неправильно:**

```scss
$Color-Cod-Gray: #1A1A1A;

.Form {
    INPUT {
        color: $Color-Cod-Gray;
    }
}
```

**Правильно:**

```scss
$color-cod-gray: #1a1a1a;

.form {
    input {
        color: $color-cod-gray;
    }
}
```

* CSS-правила отделяются друг от друга пустой строкой.

**Неправильно:**

```scss
.header {
    position: relative;
    margin: 0 auto;
    padding: 15px;
    max-width: 1000px;
    background: url("../images/header.jpg") 50% 50% no-repeat;
    @include retina {
        background-image: url("../images/header@2x.jpg");
    }
    @media (min-width: 1000px) {
        padding-top: 30px;
        padding-bottom: 30px;
    }
}
```

**Правильно:**

```scss
.header {
    position: relative;
    margin: 0 auto;
    padding: 15px;
    max-width: 1000px;
    background: url("../images/header.jpg") 50% 50% no-repeat;

    @include retina {
        background-image: url("../images/header@2x.jpg");
    }

    @media (min-width: 1000px) {
        padding-top: 30px;
        padding-bottom: 30px;
    }
}
```

* Не должно быть более одной пустой строки подряд.

**Неправильно:**

```scss
.button {
    display: inline-block;


    &::before {
        content: "";
    }
}
```

**Правильно:**

```scss
.button {
    display: inline-block;

    &::before {
        content: "";
    }
}
```

* Между свойствами не должно быть пустых строк.

**Неправильно:**

```scss
.button {
    display: inline-block;

    border: solid 1px $color-black;
    border-radius: 4px;

    padding: 5px 10px;

    font-family: $font-family-roboto;
    font-weight: 300;
    font-size: 16px;
    line-height: 1.5;

    text-align: center;
    text-decoration: none;

    cursor: pointer;
}
```

**Правильно:**

```scss
.button {
    display: inline-block;
    border: solid 1px $color-black;
    border-radius: 4px;
    padding: 5px 10px;
    font-family: $font-family-roboto;
    font-weight: 300;
    font-size: 16px;
    line-height: 1.5;
    text-align: center;
    text-decoration: none;
    cursor: pointer;
}
```

* При перечислении селекторов каждый записывается на отдельной строке.

**Неправильно:**

```scss
.prev, .next {
    position: absolute;
    top: 50%;
}
```

**Правильно:**

```scss
.prev,
.next {
    position: absolute;
    top: 50%;
}
```

* Перед `{` ставится один пробел, а после — один перенос строки.

**Неправильно:**

```scss
.header{
    position: relative;
}

.banner  {
    max-width: 1000px;
}

.footer
{
    margin-top: 15px;
}

.container {

    margin: 0 auto;
}
```

**Правильно:**

```scss
.header {
    position: relative;
}

.banner {
    max-width: 1000px;
}

.footer {
    margin-top: 15px;
}

.container {
    margin: 0 auto;
}
```

* Перед `}` не должно быть пустых строк.

**Неправильно:**

```scss
a {
    text-decoration: none; }

p {
    margin: 15px 0;

}
```

**Правильно:**

```scss
a {
    text-decoration: none;
}

p {
    margin: 15px 0;
}
```

* Перед `:` и `,` не должно быть пробелов, а после ставится один пробел.

**Неправильно:**

```scss
.container {
    padding  :  0 15px;
    max-width:  1000px;
    background: none;
}

.button {
    box-shadow: inset 0 0 2px 1px $color-black ,0 5px 4px 0 rgba($color-black, 0.25);
    transition: color 0.3s , opacity 0.3s;
}
```

**Правильно:**

```scss
.container {
    padding: 0 15px;
    max-width: 1000px;
    background: none;
}

.button {
    box-shadow: inset 0 0 2px 1px $color-black, 0 5px 4px 0 rgba($color-black, 0.25);
    transition: color 0.3s, opacity 0.3s;
}
```

* После открывающей и до закрывающей скобки не должно быть пробелов.

**Неправильно:**

```scss
a[ href ] {
    color: darken( $color-blue, 10% );
    cursor: pointer;
}
```

**Правильно:**

```scss
a[href] {
    color: darken($color-blue, 10%);
    cursor: pointer;
}
```

* Перед и после операторов (`+`, `-`, `*`, `/`) и комбинаторов (`+`, `>`, `~`) ставится один пробел.

**Неправильно:**

```scss
.sidebar {
    width: calc((100%- 30px)/2);

    >a {
        display: block;
    }
}
```

**Правильно:**

```scss
.sidebar {
    width: calc((100% - 30px) / 2);

    > a {
        display: block;
    }
}
```

* Строки записываются в двойных кавычках.

**Неправильно:**

```scss
li {
    list-style: none;

    &::before {
        content: '';
        display: inline-block;
        vertical-align: middle;
        width: 10px;
        height: 10px;
        background-image: url(../images/point.png);
    }
}
```

**Правильно:**

```scss
li {
    list-style: none;

    &::before {
        content: "";
        display: inline-block;
        vertical-align: middle;
        width: 10px;
        height: 10px;
        background-image: url("../images/point.png");
    }
}
```

* Пути записываются в двойных кавычках.

**Неправильно:**

```scss
@import 'vendor/player';

.button-play {
    background: url(../images/play.png) 50% 50% no-repeat;
}
```

**Правильно:**

```scss
@import "vendor/player";

.button-play {
    background: url("../images/play.png") 50% 50% no-repeat;
}
```

* Значения атрибутов записываются в двойных кавычках.

**Неправильно:**

```scss
a[target=_blank]::after {
    content: "";
    display: inline-block;
    width: 15px;
    height: 15px;
    background-image: url("../images/new-page.png");
}
```

**Правильно:**

```scss
a[target="_blank"]::after {
    content: "";
    display: inline-block;
    width: 15px;
    height: 15px;
    background-image: url("../images/new-page.png");
}
```

* Названия шрифтов записываются в двойных кавычках, за исключением ключевых слов.

**Неправильно:**

```scss
$font-family-roboto: Roboto, sans-serif;

.button {
    font-family: $font-family-roboto;
}
```

**Правильно:**

```scss
$font-family-roboto: "Roboto", sans-serif;

.button {
    font-family: $font-family-roboto;
}
```

* Псевдоэлементы записываются с помощью `::`.

**Неправильно:**

```scss
.list {
    &__item {
        &:before {
            content: "";
            display: inline-block;
            vertical-align: middle;
            border-radius: 50%;
            width: 8px;
            height: 8px;
            background-color: currentColor;
        }
    }
}
```

**Правильно:**

```scss
.list {
    &__item {
        &::before {
            content: "";
            display: inline-block;
            vertical-align: middle;
            border-radius: 50%;
            width: 8px;
            height: 8px;
            background-color: currentColor;
        }
    }
}
```

* Не должно быть дублирующихся свойств.

**Неправильно:**

```scss
.button {
    display: inline-block;
    border: solid 1px $color-black;
    border-radius: 4px;
    padding: 5px;
    font-family: $font-family-roboto;
    font-weight: 300;
    font-size: 16px;
    line-height: 1.5;
    text-align: center;
    text-decoration: none;
    cursor: pointer;
    border: none;
}
```

**Правильно:**

```scss
.button {
    display: inline-block;
    border: none;
    border-radius: 4px;
    padding: 5px;
    font-family: $font-family-roboto;
    font-weight: 300;
    font-size: 16px;
    line-height: 1.5;
    text-align: center;
    text-decoration: none;
    cursor: pointer;
}
```

* `font-weight` записывается в числовом формате.

**Неправильно:**

```scss
b {
    font-weight: bold;
}
```

**Правильно:**

```scss
b {
    font-weight: 700;
}
```

* У нулевых значений не указываются единицы измерений (кроме времени).

**Неправильно:**

```scss
.button {
    margin: 0px auto;
    padding: 5px 0px 6px;
}
```

**Правильно:**

```scss
.button {
    margin: 0 auto;
    padding: 5px 0 6px;
}
```

* Для чисел в интервале `(-1, 1)` указывается ведущий ноль.

**Неправильно:**

```scss
a {
    transition: color .3s;
}
```

**Правильно:**

```scss
a {
    transition: color 0.3s;
}
```

* Вместо именованных цветов используется `#`-запись.

**Неправильно:**

```scss
$color-black: black;
```

**Правильно:**

```scss
$color-black: #000;
```

* Для записи `#`-цвета следует использовать сокращенный вариант, если это возможно.

**Неправильно:**

```scss
$color-black: #000000;
```

**Правильно:**

```scss
$color-black: #000;
```

# JS

* Не должно быть пробелов в конце строк.

* Всегда ставится `;`.

* Используется строгое сравнение `===` и `!==` (вместо `==` и `!=`).

**Неправильно:**

```js
$('.test__button').on('click', () => {
    if (test.currentQuestionIndex == test.questions.length - 1) {
        test.finish();
    }

    test.answer();
});
```

**Правильно:**

```js
$('.test__button').on('click', () => {
    if (test.currentQuestionIndex === test.questions.length - 1) {
        test.finish();
    }

    test.answer();
});
```

* Не должно быть неиспользуемых переменных.

**Неправильно:**

```js
let dx = event.clientX - start.clientX;
let dy = event.clientY - start.clientY;

$slider.css({
    '-webkit-transform': `translate(${dx}px, 0)`,
    'transform': `translate(${dx}px, 0)`,
});
```

**Правильно:**

```js
let dx = event.clientX - start.clientX;

$slider.css({
    '-webkit-transform': `translate(${dx}px, 0)`,
    'transform': `translate(${dx}px, 0)`,
});
```

* Переменные объявляются на отдельных строках.

**Неправильно:**

```js
function showPage($page) {
    let $currentPage = $('.page--current'),
        $header = $('.header'),
        $footer = $('.footer');

    new TimelineMax()
        .to([
            $header,
            $footer,
            $currentPage,
        ], 1, {
            opacity: 0,
            onComplete() {
                $currentPage.removeClass('page--current');
            },
        })
        .from([
            $header,
            $footer,
            $page,
        ], 1, {
            clearProps: 'all',
            onStart() {
                $page.addClass('page--current');
            },
        });
}
```

**Правильно:**

```js
function showPage($page) {
    let $currentPage = $('.page--current');
    let $header = $('.header');
    let $footer = $('.footer');

    new TimelineMax()
        .to([
            $header,
            $footer,
            $currentPage,
        ], 1, {
            opacity: 0,
            onComplete() {
                $currentPage.removeClass('page--current');
            },
        })
        .from([
            $header,
            $footer,
            $page,
        ], 1, {
            clearProps: 'all',
            onStart() {
                $page.addClass('page--current');
            },
        });
}
```

* Не следует сокращать названия переменных и функций.

**Неправильно:**

```js
$('.js-scroll').on('click', (e) => {
    let $l = $(e.currentTarget);
    let h = $l.attr('href');
    let t = $(h).offset().top;

    $('html, body').animate({
        scrollTop: t,
    }, 500);
});
```

**Правильно:**

```js
$('.js-scroll').on('click', (event) => {
    let $link = $(event.currentTarget);
    let href = $link.attr('href');
    let top = $(href).offset().top;

    $('html, body').animate({
        scrollTop: top,
    }, 500);
});
```

* После определения переменных следует оставлять пустую строку.

**Неправильно:**

```js
$('form').on('submit', (event) => {
    let $form = $(event.currentTarget);
    let $button = $form.find('submit');
    event.preventDefault();
    $button.prop('disabled', true);
    submitForm($form);
});
```

**Правильно:**

```js
$('form').on('submit', (event) => {
    let $form = $(event.currentTarget);
    let $button = $form.find('submit');

    event.preventDefault();
    $button.prop('disabled', true);
    submitForm($form);
});
```

* Операторы в выражениях отделяются одним пробелом.

**Неправильно:**

```js
function sum(a, b) {
    return a+b;
}
```

**Правильно:**

```js
function sum(a, b) {
    return a + b;
}
```

* Перед `return` следует оставлять пустую строку.

**Неправильно:**

```js
function getQueryParam(key) {
    let params = location.search.slice(1).split('&');

    for (let param of params) {
        param = param.split('&');

        if (param[0] === key) {
            return param[1];
        }
    }
    return null;
}
```

**Правильно:**

```js
function getQueryParam(key) {
    let params = location.search.slice(1).split('&');

    for (let param of params) {
        param = param.split('&');

        if (param[0] === key) {
            return param[1];
        }
    }

    return null;
}
```

* Многострочные конструкции и выражения отделяются пустой строкой.

**Неправильно:**

```js
function f() {
    console.log('f');
}
function g() {
    console.log('g');
}
let timer = {
    start() {
        this.stop();
        this.intervalId = setInterval(() => {
            console.log('Tick');
        }, 1000);
    },
    stop() {
        clearInterval(this.intervalId);
    },
};
if (x > 5) {
    x = 0;
}
if (!items.length) {
    items.push(42);
}
switch (number) {
    case 4:
        console.log('a');
        break;
    case 5:
        console.log('b');
        break;
    case 1:
        console.log('c');
        break;
    default:
        console.log('d');
        break;
}
for (let i = 0; i < 10; i++) {
    y *= i;
}
$('.button').on('click', (event) => {
    event.preventDefault();
    run();
});
```

**Правильно:**

```js
function f() {
    console.log('f');
}

function g() {
    console.log('g');
}

let timer = {
    start() {
        this.stop();

        this.intervalId = setInterval(() => {
            console.log('Tick');
        }, 1000);
    },

    stop() {
        clearInterval(this.intervalId);
    },
};

if (x > 5) {
    x = 0;
}

if (!items.length) {
    items.push(42);
}

switch (number) {
    case 4:
        console.log('a');
        break;

    case 5:
        console.log('b');
        break;

    case 1:
        console.log('c');
        break;

    default:
        console.log('d');
        break;
}

for (let i = 0; i < 10; i++) {
    y *= i;
}

$('.button').on('click', (event) => {
    event.preventDefault();
    run();
});
```

* Не более одной пустой строки подряд.

**Неправильно:**

```js
$('.js-scroll-to').on('click', (event) => {
    event.preventDefault();
    scrollTo(event.currentTarget.href);
});


$('.js-close').on('click', (event) => {
    $(event.currentTarget).parent().removeClass('is-open');
});
```

**Правильно:**

```js
$('.js-scroll-to').on('click', (event) => {
    event.preventDefault();
    scrollTo(event.currentTarget.href);
});

$('.js-close').on('click', (event) => {
    $(event.currentTarget).parent().removeClass('is-open');
});
```

* Не следует использовать однострочную запись `if` без фигурных скобок.

**Неправильно:**

```js
function resizeItems() {
    if (!items.length) return;

    items.forEach((item) => {
        item.resize();
    });
}
```

**Правильно:**

```js
function resizeItems() {
    if (!items.length) {
        return;
    }

    items.forEach((item) => {
        item.resize();
    });
}
```

* Следует использовать сокращенную запись методов объекта.

**Неправильно:**

```js
TweenMax.from($element, 1, {
    opacity: 0,
    clearProps: 'all',
    onStart: () => {
        $element.removeClass('is-hidden');
    },
});
```

**Правильно:**

```js
TweenMax.from($element, 1, {
    opacity: 0,
    clearProps: 'all',
    onStart() {
        $element.removeClass('is-hidden');
    },
});
```
