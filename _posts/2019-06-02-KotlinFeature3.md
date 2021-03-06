---
layout: post
title: 코틀린 주요 특징3 (조건문, 반복문, 기타등등 관련)
category: Kotlin
tags: [Kotlin]
---

# 코틀린 주요 특징 3 (Kotlin Feature)
<br/>
코틀린은 기존 자바와 동일한 점도 많지만 다른 점도 분명하다.
<br/>
조건문에는 뉴페이스를 만들어버렸고, 애용하던 Java의 for문은 일부 지원하지 않도록 변경되었다.
<br/><br/>

## Kotlin 조건문
### switch문이 없고, when문을 사용한다.
* `Kotlin` Code Example
{% highlight java %}
    when (keyCode) {
      KeyEvent.KEYCODE_DPAD_UP -> {
         true
      }
      KeyEvent.KEYCODE_DPAD_LEFT,
      KeyEvent.KEYCODE_DPAD_RIGHT -> {
         playEffectSound(EFFECT_MOVE)
         false
      }
      else -> {
         true
      }
    }
{% endhighlight %}

* `Java` Code Example
{% highlight java %}
    switch (keyCode) {
      case KeyEvent.KEYCODE_DPAD_UP:
         retValue = true;
         break;
      case KeyEvent.KEYCODE_DPAD_LEFT:
      case KeyEvent.KEYCODE_DPAD_RIGHT:
         playEffectSound(EFFECT_MOVE);
         retValue = false;
         break;
      default:
         retValue = true;
         break;
    }
{% endhighlight %}

<br/><br/><br/>

## Kotlin 반복문
### for문을 지원하지 않고, for each문, while문을 지원한다

<br/><br/><br/><br/>

## 기타 외 특징들
### 1. 람다 표현식(Lamda)을 지원한다
### 2. 스트림 API(Stream API)를 지원한다

<br/><br/><br/><br/>

## Refs

* [김태호, 차세대 안드로이드 개발자를 위한 커니의 코틀린, 인사이트(2017)](https://book.naver.com/bookdb/book_detail.nhn?bid=12801360)
* [Kotlin Basic Syntax](https://kotlinlang.org/docs/reference/basic-syntax.html)
* [Kotlin API](https://kotlinlang.org/api/latest/jvm/stdlib/)
