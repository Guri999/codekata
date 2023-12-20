JadenCase 문자열 만들기
=
## 🕵️문제설명
JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)
문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.
## ⚠️제한사항

s는 길이 1 이상 200 이하인 문자열입니다.
s는 알파벳과 숫자, 공백문자(" ")로 이루어져 있습니다.
숫자는 단어의 첫 문자로만 나옵니다.
숫자로만 이루어진 단어는 없습니다.
공백문자가 연속해서 나올 수 있습니다.


## 🔎로직설명
```kotlin
class Solution {
    fun solution(s: String): String {
        return s.split(" ").map { it.mapIndexed { i, v -> if (i == 0)v.uppercase() else v.lowercase() }.joinToString("") }.joinToString(" ")
    }
}
```
난이도 뭐냐

```kotlin
fun solution(s: String): String {
        return s.split(" ").joinToString(" ") { it.toLowerCase().capitalize() }
    }
```
가독성 면에서 아래가 좋긴한대 효율면에서 안좋고 

capitalize가 1.5부터 deprecated된다고함