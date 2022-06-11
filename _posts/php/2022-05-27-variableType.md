---
title : PHP 변수의 종류
info : PHP 변수의 종류에 대해 알아보도록 하겠습니다.
categories : [PHP]
tag : [기초]
order: 3
---


# 변수의 종류
변수는 스크립트 내 어느 곳에서나 선언할 수 있습니다.
변수의 유효 범위(variable scope)란 특정 변수를 참조되거나 사용할 수 있는 스크립트 내의 범위를 의미합니다.
이러한 변수의 유효 범위에 따라 변수의 종류를 다음과 같이 구분합니다.

1. 지역 변수(local variable)
2. 전역 변수(global variable)
3. 정적 변수(static variable)

## 지역 변수(local variable)
함수 내부에서 선언된 변수는 오직 함수 내부에서만 접근할 수 있습니다.
또한, 함수 내부에서 선언된 변수는 함수의 호출이 종료되면 메모리에서 제거됩니다.

이렇게 함수 내부에서 선언된 변수를 지역 변수(local variable)라고 합니다.
```php
function varFunc() {
    $var = 10; // 지역 변수로 선언함
    echo "함수 내부에서 호출한 지역 변수 var의 값은 {$var}입니다.<br>";
}
varFunc();
echo "함수 밖에서 호출한 지역 변수 var의 값은 {$var}입니다.";
```
위의 예제에서는 함수 밖에서 함수 내부의 지역 변수 var를 참조하려고 합니다.
하지만 함수의 호출이 종료되었으므로, 함수 내부에서 선언된 모든 지역 변수들은 메모리에서 이미 제거되었습니다.
따라서 함수 밖에서 지역 변수를 참조하려고 하면 아무런 값도 얻을 수 없습니다.


## 전역 변수(global variable)
함수 밖에서 선언된 변수는 함수 밖에서만 바로 접근할 수 있습니다.
함수 밖에서 선언된 변수를 함수 내부에서 접근하고자 할 때는 global 키워드를 함께 사용해야 합니다.

이렇게 함수 밖에서 선언된 변수를 전역 변수(global variable)라고 합니다.
```php
$var = 10;       // 전역 변수로 선언함
function varFunc() {
    echo "함수 내부에서 호출한 전역 변수 var의 값은 {$var}입니다.<br>";
    global $var; // 함수 내에서 사용할 전역 변수를 명시함
    echo "함수 내부에서 호출한 전역 변수 var의 값은 {$var}입니다.<br>";
}
varFunc();
echo "함수 밖에서 호출한 전역 변수 var의 값은 {$var}입니다.";
```
위의 예제에서 맨 처음 호출한 echo 함수는 아무런 값도 출력하지 못합니다.
하지만 사용할 전역 변수를 global 키워드로 명시하고 나서 다시 호출한 echo 함수는 정확한 전역 변수의 값을 출력합니다.

모든 전역 변수를 $GLOBALS 배열에 저장합니다.
이 배열에 인덱스로 변수의 이름을 사용하면, 해당 전역 변수의 값에 접근할 수 있습니다.
이 배열은 함수 내부에서도 접근할 수 있으며, 이 배열을 통해 바로 전역 변수의 값을 변경할 수도 있습니다.
```php
$var = 10; // 전역 변수로 선언함
function varFunc() {
    echo "함수 내부에서 호출한 전역 변수 var의 값은 {$var}입니다.<br>";
    echo "함수 내부에서 호출한 전역 변수 var의 값은 {$GLOBALS['var']}입니다.<br>";
}
varFunc();
echo "함수 밖에서 호출한 전역 변수 var의 값은 {$var}입니다.";
```
위의 예제는 함수 내부에서 global 키워드를 사용하는 대신에 $GLOBALS 배열을 사용하여 전역 변수에 접근하고 있습니다.

## 슈퍼 글로벌(superglobal)
미리 정의된 전역 변수인 슈퍼 글로벌(superglobal)을 제공합니다.
이러한 슈퍼 글로벌은 특별한 선언 없이 스크립트 내의 어디에서라도 바로 사용할 수 있습니다.

제공하는 슈퍼 글로벌은 다음과 같습니다.
1. $GLOBALS
2. $_SERVER
3. $_GET
4. $_POST
5. $_FILES
6. $_COOKIE
7. $_SESSION
8. $_REQUEST
9. $_ENV

\$GLOBALS를 제외한 나머지는 [Form](https://wade.pw/php/form_handling) 과 [쿠키와 세션](https://wade.pw/php/cookieSession_cookie) 에서 더 자세히 확인할 수 있습니다.

## 정적 변수(static variable)
정적 변수(static variable)란 함수 내부에서 static 키워드로 선언한 변수를 의미합니다.

함수 내부에서 선언된 정적 변수는 함수의 호출이 종료되더라도 메모리상에서 사라지지 않습니다.
하지만 지역 변수처럼 해당 함수 내부에서만 접근할 수 있습니다.
```php
function counter() {
    static $count = 0;
    echo "함수 내부에서 호출한 static 변수 count의 값은 {$count}입니다.<br>";
    $count++;
}
counter();
counter();
counter();
```
위의 예제에서 정적 변수인 $count는 함수의 호출이 종료된 후에도 계속해서 그 값을 유지하고 있습니다.
