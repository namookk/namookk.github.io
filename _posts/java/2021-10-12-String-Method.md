---
layout: post
title: 문자열 클래스의 차이 ( String, StringBuffer, StringBuilder)
date: 2021-10-12 14:22:20 +0900
description: 
categories : java
fig-caption: # Add figcaption (optional)
tags: [String, StringBuffer, StringBuilder]
---
자바에서 문자열을 다루는 클래스로 String, StringBuffer, StringBuilder 3가지 클래스가 존재합니다.
위 3가지 클래스는 모두 문자열을 관리하고 저장하는 클래스이지만 각각 차이가 존재합니다 그 차이를 알아봅시다.

### String
String 객체는 new 연산을 통해 생성되며 생성 후 그 인스턴스의 메모리공간은 절대 변하지 않습니다.
따라서 객체를 수정할때마다 메모리 공간이 변하는것이 아니라 새로운 String 객체를 new로 생성하여 새로운 메모리공간을 만드는 것입니다.

새로운 객체를 계속해서 생성하는 이유로 기존의 객체는 가비지 콜렉터에 의해 제거돼어야 합니다.
하지만 언제 제거될지 모르는 단점이있고. 문자열 연산이 많아질수록 계속해서 객체를 생성하는 오버헤드가 발생하므로 성능이 떨어지는 단점이 있습니다.

String 클래스의 객체는 불변객체이므로 단순 조회 연산에서 다른 문자열 클래스보다 더 빠르게 읽을 수 있습니다.
또 불변객체의 특성으로 Multi Thread 환경에서 동기화를 신경쓰지 않아도 됩니다.

### StringBuffer

StringBuffer 클래스의 객체는 String 클래스의 객체와 다르게 가변객체입니다.
문자열 생성할때 한번 만든 후 객체를 수정할때 해당 메모리의 크기를 변경시켜 문자열을 수정합니다.
또, StringBuilder 클래스의 Method들이 같으므로 호환이 가능합니다 

### StringBuilder

StringBuilder 클래스도 StringBuffer와 같이 가변객체입니다. 단, StringBuffer와의 차이점은 
Multi Thread환경에서 synchronized 키워드를 사용하지 못하여 동기화가 불가능하여 thread-safe하지 못하는 단점이있지만
동기화를 고려하지 않아도 되는 환경에서 StringBuffer보다 성능이 뛰어난 장점이 있습니다.

### String, StringBuffer, StringBuilder의 차이

위에서 언급했듯 String은 불변객체, StringBuffer, StringBuilder 는 가변객체이므로
문자열 연산이 많으면 String보단 StringBuffer, StringBuilder 를 사용하는 것이 효율적입니다.

또, Multi Thread환경에서 thread-safe 한 클래스는 String과 StringBuffer 사용하는 것이 바람직합니다.




