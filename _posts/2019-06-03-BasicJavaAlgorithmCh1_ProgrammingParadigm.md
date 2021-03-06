---
layout: post
title: 자바 알고리즘 입문 ch1 (프로그래밍 패러다임)
category: Algorithm-Basic
tags: [Algorithm-Basic]
---
<br><br>
보요 시바타 저 ‘Do it! 자료구조와 함께 배우는 알고리즘 입문’의 ch1장 공부 내용 기록입니다.<br/>
이론적인 부분들이예요.<br/>
이해가 잘 안가는 부분은 위키백과 및 수많은 블로그를 찾아보았습니다.<br/>
쓰다보니 프로그래밍 패러다임 글이 되었네요;;
<br><br>
## 프로그래밍 패러다임
무슨 뜻인지 여러 블로그를 보아도 이해가 가지 않아 <br/>
사전에서 패러다임을 검색해봤더니 어떤 것인지 대략적으로 이해가 간다. <br/>
<br/>
**`패러다임`** : 어떤 한 시대 사람들의 견해나 사고를 근본적으로 규정하고 있는 <u style="color:#337ab7">테두리로서의 인식의 체계</u>. 또는 사물에 대한 이론적인 틀이나 체계.

##### 프로그래밍 패러다임의 특징
 - 소프트웨어 공학을 할 때의 패러다임 형태인 방법론과 비교된다.
 - 많은 프로그래밍 패러다임은 어떤 기법을 금지하거나 어떤 것을 가능하게 하는 것으로 널리 알려져 있다. 
 - 프로그래밍 패러다임은 프로그래머에게 프로그래밍의 관점을 갖게 해 주고, 결정하는 역할을 한다.<br/>
 <br/>
 <p style="color:#337ab7"><strong>객체지향 프로그래밍은 프로그래머들이 프로그램을 상호작용하는 객체들의 집합으로 볼 수 있게 하는 반면에, 함수형 프로그래밍은 상태값을 지니지 않는 함수값들의 연속으로 생각할 수 있게 해준다.</strong></p>
 <br/><br/><br/>
  
## 1. 명령형 프로그래밍 (Imperative programming)
`프로그래밍의 상태`와 `상태를 변경시키는 구문`의 관점에서 연산을 설명하는 프로그래밍 패러다임<br/>
명령형 프로그램은 컴퓨터가 수행할 명령들을 순서대로 써 놓은 것이다.<br/>
<br/>
거의 대부분의 컴퓨터 하드웨어는 명령형으로 구현된다.<br> 
<p style="color:#337ab7">거의 모든 컴퓨터 하드웨어들이 컴퓨터의 고유 언어인 <u>기계어</u>를 실행하도록 설계되어 있는데, 이것이 명령형으로 씌어 있다.</p>
<br>
 ▶ 명령형 프로그래밍 특징을 가진 언어 : C, C++, Java
<br/><br/><br/>

## 2. 선언형 프로그래밍 (Declarative programming)
프로그램이 어떤 방법으로 해야 하는지를 나타내기보다 `무엇과 같은지를 설명`하는 경우에 "선언형"이라고 한다.<br/>
<br/>
EX) <br>
{% highlight html %}
<h1>HTML is Declarative Programming!</h1>
<button onclick="fMove('d1')">div1로 이동</button>
<div id="div1">div1</div>
{% endhighlight %}
위와같이 웹 페이지는 선언형인데 웹페이지는 제목, 글꼴, 본문, 그림과 같이 "무엇"이 나타나야하는지를 묘사하는 것이지 "어떤 방법으로" 컴퓨터 화면에 페이지를 나타내야 하는지를 묘사하는 것이 아니기 때문이다. <br/><br/>
명령형 프로그래밍 언어는 프로그래머가 실행될 알고리즘을 명시해주어야 하는 것이다. <br/>
cf) 간단히 말하여, 명령형 프로그램은 `알고리즘을 명시하고 목표는 명시하지 않는 데` <br/>
반해 선언형 프로그램은 `목표를 명시하고 알고리즘을 명시하지 않는 것`이다.<br>
<br>
▶ 선언형 프로그래밍 특징을 가진 언어 : SQL, HTML
<br><br>


- - -
#### 명령형 프로그래밍(Imperative programming) vs 선언형 프로그래밍(Declarative programming)
[여기](https://github.com/chocoma87/ToyProject/wiki/%EA%B0%9C%EB%B0%9C%EC%9D%BC%EC%A7%80-6-(Imperative-vs-Declarative-Programming))분이 좋은 글을 번역해주셔서 쏙쏙 이해갔어요 감사합니다 ㅠㅠ<br><br>
**Example1)**
<br>
 - 명령형 접근 : 창가에 위치한 테이블이 비어있다. 나와 친구는 그쪽으로 걸어가서 앉았다.
 - 선언형 접근 : Table for two, please.
<br>
명령형 접근은 테이블에 앉기까지 절차를 나열하고 있다.<br>
선언형 접근은 내가 무엇을 원하는지만을 언급하고 있다.<br>
<br>

**Example2)**
<br>
예를 하나 더 들어보자. "지금 월마트에 있어. 여기서 너네 집까지 어떻게 가니?"<br>
 - 명령형 접근 : 주차장의 북쪽 입구로 나와서 좌회전 해라. 뱅갈 고속도로 표지판이 보일때까지 1-15길로 가라. 우회전해서 이케아가 보일때까지 직직해라. 첫번째 신호에서 우회전해라. 다음 신호까지 직진 한 다음 좌회전 해라. 내 집은 #298이다.
 - 선언형 접근 : 내 집 주소는 298 West Immutable Alley, Draper Utah 84020 이다.
 <br>
여기서 중한 것이, 많은 선언형 접근은 명령형 접근을 내포하고 있다. <br>
레스토랑에서 선언형으로 말할 때는 종업원이 우리를 테이블까지 안내하는 과정을 모두 알고 있을 것이라는 전제 하에 얘기하고 있다. 월마트 예에서는 찾아오는 사람이 gps 같은 것을 가지고 있어서, 집까지 어떻게 오는지 모든 과정을 알고 있을 것이라고 가정한다.<br>
<br>
▶ 명령형 & 선언형 프로그래밍 특징을 가진 언어 : Javascript, C#, Phtyon
<br>
---
<br><br><br>

## 3. Procedural Programming (절차적 프로그래밍)
`프로시저 호출`의 개념을 바탕으로 하고 있는 프로그래밍 패러다임<br/>
즉, 단순히 순차적인 명령 수행이 아니라 프로시저(루틴, 서브루틴, 메소드, 함수 등)을 이용한 프로그래밍 패러다임<br/>
<br/>
**`프로시저`** : 루틴, 하위프로그램, 서브루틴, 메서드, 함수 라고도 하는데, 간단히 말하여 <u style="color:#337ab7">수행되어야 할 연속적인 계산 과정</u>을 포함하고 있다.<br/>
 +) 프로그램의 아무 위치에서나 프로시저를 호출될 수 있는데, 다른 프로시저에서도 호출 가능하고 심지어는 자기 자신에서도 호출 가능하다.
<br/><br/><br/>

## 4. 구조적 프로그래밍 (Structured Programming)
절차적 프로그래밍의 하위 개념으로 볼 수 있다.<br>
구조로 프로그래밍을 보겠다는 건데 근본적으로 `구조`가 무엇인지 봐야한다.
<br/><br/>
#### 저수준 관점에서의 구조적 프로그래밍
저수준의 관점에서 구조적 프로그램은 간단하고, 계층적인 프로그램 `제어 구조`로 구성된다. <br/>
에츠허르 데이크스트라가 확인한 3가지 형태의 구조는 `순차`, `선택`, `반복`이라고 한다.<br/>
알고리즘이 보통 이런 제어구조들로 이루어져서 인지 제가 본 알고리즘 책에는 이 제어구조가 쓰여있었습니다.<br>
##### 1. Concatenation(순차적) 구조 
 : 여러 문장이 첫문장부터 순서대로 실행되는 구조
##### 2. Selection(선택) 
 : 조건에 따라 조건에 맞는 문장이 실행되는 구조
##### 3. Repetition(반복) 
 : 특정 상태에 도달할 때까지 구문을 반복하여 수행하거나, 집합체의 각각의 원소들에 대해 어떤 구문을 반복 수행하는 것<br/>
 
### 고수준 관점에서의 구조적 프로그래밍
##### 코드를 이해하기 쉬운 크기의 `작은 하부 프로그램(함수, 프로시저, 메서드, 블록, 등)`으로 나누어야 한다.
일반적으로 프로그램은 전역 변수는 거의 사용하지 않아야 하고 대신에 하부 프로그램은 지역 변수를 사용하거나, 값이나 참조에 의한 인자를 받아야 한다. <br/>
이런 기법은 전체 프로그램을 한번에 이해하지 않고, 분리된 작은 코드 조각(<<일종의 `모듈`인건가?)을 쉽게 이해하는 데 도움을 준다.<br/><br/>

structured programming은 GOTO문을 없애거나 GOTO문에 대한 의존성을 줄여주는 것으로 가장 유명하다.<br>
<br>
▶ 구조적 프로그래밍 특징을 가진 언어 : C, Pascal
<br/><br/><br/>

## 5. 객체 지향 프로그래밍 (Object-Oriented Programming, OOP)
컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위, 즉 **`객체`**들의 모임으로 파악하고자 하는 것이다.<br/>
 - 데이터(프로퍼티)와 절차(메서드,함수, 일종의 기능이나 동작, 프로시저)를 `객체`로 묶어 모듈화
<br>
각각의 객체는 메시지를 주고받고, 데이터를 처리할 수 있다.<br/>
<br><br>

### 객체 지향 프로그래밍의 기본 구성 단위
#### 1. 클래스(Class) 
- 같은 종류(또는 문제 해결을 위한)의 집단에 속하는 속성(attribute)과 행위(behavior)를 정의한 것으로 객체지향 프로그램의 기본적인 사용자 정의 데이터형(user define data type)이라고 할 수 있다. 클래스는 프로그래머가 아니지만 해결해야 할 문제가 속하는 영역에 종사하는 사람이라면 사용할 수 있고, 다른 클래스 또는 외부 요소와 독립적으로 디자인하여야 한다.

#### 2. 객체(Object) 
 - 클래스의 인스턴스(실제로 메모리상에 할당된 것)이다. 객체는 자신 고유의 속성(attribute)을 가지며 클래스에서 정의한 행위(behavior)를 수행할 수 있다. 객체의 행위는 클래스에 정의된 행위에 대한 정의를 공유함으로써 메모리를 경제적으로 사용한다.

#### 3.메서드(Method), 메시지(Message) 
 - 클래스로부터 생성된 객체를 사용하는 방법으로서 객체에 명령을 내리는 메시지라 할 수 있다. 메서드는 한 객체의 서브루틴(subroutine) 형태로 객체의 속성을 조작하는 데 사용된다. 또 객체 간의 통신은 메시지를 통해 이루어진다.
<br><br>
+)  [내 기준으로 쉽게 설명한 객체지향 프로그래밍 포스팅](http://blog.wishket.com/%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5-vs-%EC%A0%88%EC%B0%A8%EC%A7%80%ED%96%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D/)
<br/><br/><br/>

## 6. 함수형 프로그래밍
내가 봤을때 이해가 가장 어려웠고 좋고 싫음이 진짜 확실한 패러다임이다;;;<br/>
그래서 이 녀석이 좋아하는 것(순수함수, 함수의 명확한 입출력)과<br/> 
싫어하는 것(Side-effect, 가변성, 복잡성, 버그)을 명확히 알면 이해가 간다.<br/>
<br/><br/>

자료 처리를 수학적 함수의 계산으로 취급하고 상태와 `가변 데이터를 멀리하는` 프로그래밍 패러다임<br/>
<br>
'수학적 함수의 계산으로 취급'한다는 것이 무슨 말일까? <br>
수학적 함수와 명령형 프로그래밍에서 사용되는 함수는 차이가 있는데, 명령형의 함수는 프로그램의 상태의 값을 바꿀 수 있는 부작용이 생길 수 있다. <br>

그럼 일단 그 부작용부터 알아보자.
#### Side effect (부작용)
**명령형 함수의 부작용 발생 Example)**
{% highlight java %}
private Person personSykim = new Person();
private Person personJessica = new Person();

public void notPureFunc() {
    Person.armNum = 3; // 특정 클래스의 static 변수 혹은 함수 호출 (상태 및 프로퍼티 등등 이 호출로 변할 범위가 무궁무진함)
    personSykim.setName("ivy");
    personJessica.doNextProcess();
    // 전역 객체를 불러와 객체의 메소드 호출 (상태 및 프로퍼티 등등 이 호출로 변할 범위가 무궁무진함)
}
{% endhighlight %}

위 notPureFunc() 메소드는 입력 파라미터 및 출력 리턴값이 없다.<br>
그럼에도 함수 내에서 실행되는 여러 기능으로 인하여 입출력처럼 외부 상태를 변경할 수 있는데<br>
바로 이렇듯 함수선언만으론 알 수 없는 비밀스런 프로그램 상태변경 작용(?)들을 `Side-effect (부작용)`이라고 한다.<br>
<br>
이 '부작용'때문에 명령형 함수는 참조 투명성이 없고, 같은 코드라도 실행되는 프로그램의 상태에 따라 다른 결과값을 낼 수 있다.<br>
그리고 이런 부작용을 매우 싫어하는 함수형 프로그래밍은 명령형 프로그래밍이 아닌 (프로그래밍이 문이 아닌 식이나 선언으로 수행되는) 선언형 프로그래밍 패러다임을 따르고 있다.<br>
<br><br>
그렇다면, 함수형 프로그래밍은 어떻게 프로그래밍하는 것인가?<br>
바로 순수함수로 작성하여 부작용을 최대한 없애는 것이다<br>
#### 순수함수 (Pure fuction)
: 함수의 실행이 외부에 영향을 끼치지 않는 함수<br>
 - 외부 영향이 없어 스레드 안전하고, 병렬적인 계산이 가능하다.
<br/>
**순수 함수로 바꿔본 위의 부작용 Example)**
{% highlight java %}
private Person personSykim = new Person();
private Person personJessica = new Person();

public void notPureFunc(Person p1, String changeName, Person p2) {
    Person changeNamePerson = p1.clone();
    Person doNextProcessPerson = p2.clone();
    changeNamePerson.setName(changeName);
    doNextProcessPerson.doNextProcess();
}
{% endhighlight %}
 - 순수 함수는 수학적 함수 y = f(x)처럼 x를 입력하면 항상 y라는 동일값이 나오도록 해야한다.
 - 순수 함수는 수행 과정에서 side-feect 작용(상태값 변경 등등)이 있어선 안된다.
<br/><br/>

더불어 위 예시에는 함수형 프로그래밍의 특징 `불변성 (Immutability)`이 적용되어 있다. <br>
#### 불변성 (Immutability)
위와 같이 데이터가 변할 수 없도록 하며, 데이터 변경이 필요한 경우 데이터 복사본을 만들어 변경 작업을 진행한다.<br>
더불어 함수형 프로그래밍의 특징이 더 있다.
<br><br>

#### Frist Object (1급 객체)
아래와 같은 연산을 지원할 때 일급 객체라고 한다.
<br/>
  - 변수나 데이터에 할당 가능
  {% highlight javascript %}
  val firstObj = { x: Int, y: Int -> x+y } // return type Method : (x: Int, y: Int) -> Int
  {% endhighlight %}
  <br/>
  
  - 함수에 매개변수로 전달 가능
  {% highlight javascript %}
    val firstObj = { x: Int, y: Int -> x+y }
    fun tempFuction(func: (x: Int, y: Int) -> Int) {
        func.hashCode()
    }
    
    
    @JvmStatic
    fun main(args: Array<String>) {
      tempFuction(firstObj)
    }
  {% endhighlight %}
  <br/>
  - 리턴값으로 사용가능
  {% highlight javascript %}
  fun tempFuction(): (x: Int, y: Int) -> Int {
     return { n1: Int, n2: Int -> n1 + n2 }
  }
  {% endhighlight %}
<br/>
<br><br>

#### 고차 함수 (High-Order Function)
함수를 다루는 함수를 뜻하며 `1급 객체`에서 이미 언급한 부분들이다.<br/> 
사실 함수형 언어에서는 함수도 '값(value)'으로 취급한다. 그러므로 정수 1이나 인수를 제곱하는 함수나 동등한 입장에서 다룰 수 있다. <br/>
 - (정수를 함수의 인수로 전달할 수 있듯이) 어떤 **함수도 다른 함수의 인수로 전달할 수 있다.**
 - 함수의 결과 값으로 정수를 반환할 수 있듯이 **함수를 반환할 수도 있다.**
 
<br><br>
▶ 함수형 프로그래밍 특징을 가진 언어 : Kotlin, Haskell, Sheme
<br/><br/>
이 외 함성 함수, 커링 등등 더 많은 것들이 있지만 이하 생략합니다...<br>
<br><br>

<br><br><br>

## Java 값 입력 받기
키보드와 연결된 입력 스트림 System.in으로부터 입력받은 값을 가져오는 장치 역할이라고 한다.
{% highlight java %}
   Scanner stdIn = new Scanner(System.in);
   int v1 = stdIn.nextInt(); // 정수값 입력받음 원하는 입력 타입에 맞는 함수를 사용하면 된다.
{% endhighlight %} 

<br>
## 알고리즘?
책의 개념은 너무 어렵다. <br/>
맞는지 모르겠지만 내가 이해한 개념은 아래와 같다. 
`문제를 해결하기 위한 일렬의 논리구조(명확하고 규칙으로 이루어져 있는)`


<br/><br/><br/>


## Refs

* [프로그래밍 패러다임, 위키백과](https://ko.wikipedia.org/wiki/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D_%ED%8C%A8%EB%9F%AC%EB%8B%A4%EC%9E%84)
* [Imperative programming, 명령형 프로그래밍](https://ko.wikipedia.org/wiki/%EB%AA%85%EB%A0%B9%ED%98%95_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
* [Declarative programming, 선언형 프로그래밍, 위키백과](https://ko.wikipedia.org/wiki/%EC%84%A0%EC%96%B8%ED%98%95_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
*[Imperative vs Declarative Programming 번역](https://github.com/chocoma87/ToyProject/wiki/%EA%B0%9C%EB%B0%9C%EC%9D%BC%EC%A7%80-6-(Imperative-vs-Declarative-Programming))
*[Imperative vs Declarative Programming 원본](https://tylermcginnis.com/imperative-vs-declarative-programming/)
* [Procedual programming, 절차적 프로그래밍, 위키백과](https://ko.wikipedia.org/wiki/%EC%A0%88%EC%B0%A8%EC%A0%81_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
* [Procedural programming, 절차적 프로그래밍, 나무위키](https://namu.wiki/w/%EC%A0%88%EC%B0%A8%EC%A0%81%20%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
* [Structured programming, 구조적 프로그래밍, 위키백과](https://ko.wikipedia.org/wiki/%EA%B5%AC%EC%A1%B0%EC%A0%81_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
* [객체지향 프로그래밍, 위키백과](https://ko.wikipedia.org/wiki/%EA%B0%9D%EC%B2%B4_%EC%A7%80%ED%96%A5_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)

* [함수형 프로그래밍, 위키백과](https://ko.wikipedia.org/wiki/%ED%95%A8%EC%88%98%ED%98%95_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)
* [(번역) 함수형 프로그래밍이란 무엇인가?](https://medium.com/@jooyunghan/%ED%95%A8%EC%88%98%ED%98%95-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80-fab4e960d263)
* [함수형 프로그래밍 요약](https://velog.io/@kyusung/%ED%95%A8%EC%88%98%ED%98%95-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EC%9A%94%EC%95%BD)
* [함수형 프로그래머가 되고 싶다고? (Part 1)
](https://github.com/FEDevelopers/tech.description/wiki/%ED%95%A8%EC%88%98%ED%98%95-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%A8%B8%EA%B0%80-%EB%90%98%EA%B3%A0-%EC%8B%B6%EB%8B%A4%EA%B3%A0%3F-(Part-1))
* [1급 객체, 위키백과](https://ko.wikipedia.org/wiki/%EC%9D%BC%EA%B8%89_%EA%B0%9D%EC%B2%B4)
* [1급 객체(First-class citizen) 란? with Kotlin](https://medium.com/@lazysoul/functional-programming-%EC%97%90%EC%84%9C-1%EA%B8%89-%EA%B0%9D%EC%B2%B4%EB%9E%80-ba1aeb048059)

* [보요 시바타, Do it! 자료구조와 함께 배우는 알고리즘 입문, 강민,  이지스퍼블리싱(2018)](https://book.naver.com/bookdb/book_detail.nhn?bid=13560672)
