---
layout: post
title: Kotlin의 class에 대하여 알아보기 1
---

오늘은 코틀린에서의 class에 대하여 알아보려 합니다.

## class 선언 방식

```java
class test(){
}
```


## class 구성

속성와 함수로 이루어져 있습니다.

```java
class test(){
    var a : Int = 1
    var b : Int = 2

    fun sum():Int{
        return a + b
    }
}
```

## class 활용

```java
class test(){
    var name : String = "test"
    var a : Int = 1
    var b : Int = 2
    fun sum():Int{
        return a + b
    }
}

fun main(args: Array<String>) {
    var real = test()
    var result = real.sum();
    println(result)
}
```

먼저 test라는 클래스를 만들고, 각종 속성을 선언하고 값을 초기화하며 대입합니다.

그리고 그 클래스의 함수를 작성합니다.

마지막으로 메인에서 test 클래스의 객체를 생성하면서 온점으로 함수에 접근할 수 있습니다.

## class 상속

타 언어와 같이 상위 클래스에서 정보를 상속 받을 수 있습니다.

open 키워드를 사용하여 상속해줄 수 있는 속성과 함수를 정할 수 있습니다.

```java
open class test(){
    open var name : String = "test"
    var a : Int = 1
    var b : Int = 2
    open fun sum():Int{
        return a + b
    }
}

class test2() : test(){
    override var name : String = "test2"
}

fun main(args: Array<String>) {
    var real = test2()
    var result = real.sum();
    println(result)
    println(real.name)
}
```

상속받은 클래스로 객체를 생성하면 상위 클래스에 있는 내용이 상속되어 중복 작성을 피하게 됩니다.

## 인터페이스

위의 기존 코드에 인터페이스를 추가해보겠습니다.

```java
interface Itest{
}
```

인터페이스는 위와 같은 구조로 이루어져 있습니다.


```java
open class test():Itest{
    override fun TestInterface(){
        println("interface")
    }
}
```

인터페이스를 상속받아서 오버라이드를 해주면 됩니다.

```java
interface Itest{
    fun TestInterface()
}

open class test():Itest{
    open var name : String = "test"
    var a : Int = 1
    var b : Int = 2
    open fun sum():Int{
        return a + b
    }
    override fun TestInterface(){
        println("interface")
    }
}

class test2() : test(){
    override var name : String = "test2"
}

fun main(args: Array<String>) {
    var real = test2()
    var result = real.sum();
    println(result)
    println(real.name)
}
```

위 예시 코드에 인터페이스를 붙여 작성한 코드입니다.

상위 클래스에 인터페이스를 상속받아서 오버라이드한 모습니다.