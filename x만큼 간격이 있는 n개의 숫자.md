>**문제설명**

함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다. 다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.


>**제한사항**

x는 -10000000 이상, 10000000 이하인 정수입니다.
n은 1000 이하인 자연수입니다.

>**진행**

리스트 작성을 위해 배열을 쓰자

배열의 크기는 n 으로 하고 x를 입력받자
```kotlin
println("정수를 입력하세요")
    val x = readln().toInt()
    println("배열의 크기를 입력하세요")
    val n = readln().toInt()
```
이제 솔루션을 작성할 차례다

```kotlin
var answer = LongArray(n)
```
위에서 입력 받은 배열의 크기가 적용되게 해주고

```kotlin
    while (i < n){
        answer[i] = num.toLong()
        num += x
        i++
    }

```
배열의 크기만큼 반복해준다

이제 이 문자열을 우리가 볼수 있게 출력해야한다

JoinToString 함수를 사용해보자
```kotlin
 println("${solution(x,n).joinToString(" , ")}")
```

>**코드**

```kotlin
package com.example.codekata

fun main() {

    println("정수를 입력하세요")
    val x = readln().toInt()
    println("배열의 크기를 입력하세요")
    val n = readln().toInt()

    println("${solution(x,n).joinToString(" , ")}")
}
fun solution(x: Int, n: Int): LongArray {
    var answer = LongArray(n)
    var i = 0
    var num = x

    while (i < n){
        answer[i] = num.toLong()
        num += x
        i++
    }

    return answer!
}

```


