---
published: true
title : PHP 상수
info : PHP 상수에 대해 알아보도록 하겠습니다.
categories : [PHP]
tag : [기초]
order: 4
---


# 상수(constant)
상수(constant)란 변숭와 마찬가지로 데이터를 저장 할 수 있는 메모리 공간을 의미합니다.
하지만 상수가 변수와 다른 점은 한번 선언되면, 스크립트가 실행되는 동안 그 데이터를 변경하거나 해제(undefined)할 수 없다는 점입니다.

## define() 함수
define() 함수를 사용하여 상수를 선언할 수 있습니다.

define() 함수의 원형은 다음과 같습니다.
```php
define(상수이름, 상숫값, 대소문자구분여부)
```
이 함수는 첫 번째 인수로 상수의 이름을 전달받고, 두 번째 인수로 그 값을 전달받습니다.

세 번째 인수는 상수의 이름이 대소문자를 구분하는가를 설정하며, 기본값은 false로 대소문자를 구분합니다.
```php
define("PHP", "Hello World<br>"); // 대소문자를 구분함.(기본 설정)
echo PHP; // Hello World
echo php; // php
define("PHP", "<br>Hello World", true); // 대소문자를 구분하지 않음.
echo php; // Hello World
echo Php; // Hello World
```
이렇게 선언된 상수는 스크립트의 어디에서라도 참조할 수 있습니다.

단, 해당 상수가 선언되기 이전의 스크립트 영역에서는 해당 상수를 참조할 수 없습니다.
```php
function defFunc()
{
    echo PHP; // PHP
    define("PHP", "Hello World");
    echo PHP; // Hello World
}
defFunc();
echo PHP;     // Hello World
```
위의 예제에서 상수가 선언되기 전의 영역에서 호출한 echo() 함수는 해당 상수의 값을 참조하지 못합니다.
또한, 험수 내부에서 선언된 상수가 함수의 호출이 종료된 후에도 사용할 수 있음을 보여줍니다.

## 마법 상수(magic constants)
어떤 스크립트에서도 사용할 수 있는 미리 정의된 다양한 상수를 제공합니다.

다음 예제는 미리 정의된 모든 상수를 출력해 주는 예제입니다.
```php
echo "<pre>";
print_r(get_defined_constants(true));
echo "</pre>";
```
위와 같이 미리 정의된 상수 이외에도 어디에 사용하느냐에 따라 용도가 변경되는 8개의 마법 상수를 제공합니다.
이러한 마법 상수(magic constants)는 대소문자를 구분하지 않습니다.


|상수 이름|설명|
|:---:|:---|
|\__LINE__|파일의 현재 줄 번호를 반환함.|
|\__FILE__|파일의 전체 경로와 이름을 반환함.<br/>include 내부에서 사용할 경우 include된 파일명을 반환함.|
|\__DIR__|파일의 디렉터리를 반환함.<br/>포함한 파일 안에서 사용할 경우 포함된 파일의 디렉터리를 반환함.<br/>dirname(\__FILE__)과 같은 결과를 반환함.|
|\__FUNCTION__|함수의 이름을 반환함.|
|\__CLASS__|클래스의 이름을 반환함. 클래스 이름은 대소문자를 구분함.|
|\__TRAIT__|트레이트(trait)의 이름을 반환함.<br/>트레이트의 이름은 트레이트를 선언한 네임스페이스를 포함함.|
|\__METHOD__|클래스의 메소드 이름을 반환함.|
|\__NAMESPACE__|현재 네임스페이스의 이름을 반환함.|


클래스와 메소드에 대한 더 자세한 사항은 [클래스와 객체](https://wade.pw/php/classObject)에서 확인할 수 있습니다.