---
layout: category
title : HTML
subtitle : HTML - Hypertext Markup Language
info : HTML(Hypertext Markup Language)에 대한 소개와 구조화를 설명합니다.
---

# 소개
HTML(Hypertext Markup Language)은 아쉽게 프로그래밍 언어는 아닙니다. HTML의 기능은 웹 페이지와 그 내용을 구조화하기 위해 사용하는 코드입니다. HTML은 컨텐츠의 서로 다른 부분들을 씌우거나 감싸서 다른 형식으로 보이게하거나 특정한 방식으로 동작하도록 하는 일련의 요소(elements:엘리먼트)로 이루어져 있습니다.

# 시작하기
그럼 HTML에서 구조화는 어떻게 할까요? 예를 들어 다음과 같은 글이 있다고 과정해봅시다.
```ex
안녕하세요! CodePin!
```
다음과 같은 글을 HTML 문법에 맞춰 구조화 하기위해서는 앞과 뒤에 태그(Tags)를 붙여 하나의 문단임을 명시할 수 있습니다.
```html
<p>안녕하세요! CodePin!</p>
```

# 구조 분석
다음 예제 내용을 분석해보겠습니다.

![](https://developer.wade.pw/assets/contents/htmlstructure.png)

1. **여는 태그(opening tag)** : 이것은 요소의 이름으로 구성되고 (여기에서는 p), 여닫는 꺾쇠괄호(<>)로 감싸집니다. 이것은 요소가 시작되는 곳에 위치하게 되며 이 예제에서 여는 태그는 `<p>`입니다.
2. **닫는 태그(closing tag)** : 이것은 여는 태그와 같지만, 요소의 이름 앞에 전방향 슬래시(/)가 포함된다는 점이 다릅니다. 이것은 요소의 끝을 나타냅니다. 이 예제에서 닫는 태그는 `</p>`입니다.
3. **컨텐츠(content)** : 이것은 요소 안의 내용(content)으로 이 예제에서는 `안녕하세요! CodePin!`이 내용(content)입니다.
4. **요소(element)** : 요소는 여는 태그와 닫는 태그, 그리고 컨텐츠로 이루어집니다. 위 사진에서는 `<p>안녕하세요! CodePin!</p>`이 하나의 요소입니다.

또한 요소는 속성(Attributes)을 가질 수 있게됩니다.
