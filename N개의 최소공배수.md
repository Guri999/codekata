N개의 최소공배수
=
## 🕵️문제설명
두 수의 최소공배수(Least Common Multiple)란 입력된 두 수의 배수 중 공통이 되는 가장 작은 숫자를 의미합니다. 예를 들어 2와 7의 최소공배수는 14가 됩니다. 정의를 확장해서, n개의 수의 최소공배수는 n 개의 수들의 배수 중 공통이 되는 가장 작은 숫자가 됩니다. n개의 숫자를 담은 배열 arr이 입력되었을 때 이 수들의 최소공배수를 반환하는 함수, solution을 완성해 주세요.
## ⚠️제한사항

arr은 길이 1이상, 15이하인 배열입니다.
arr의 원소는 100 이하인 자연수입니다.


## 🔎로직설명
```kotlin
class Solution {
    fun solution(arr: IntArray): Int {
        for (i in arr.indices) {
            if (i+1 < arr.size) arr[i+1] = arr[i] * arr[i+1] / gcd(arr[i],arr[i+1])
        }
        return arr.last()
    }
    tailrec fun gcd(a:Int, b:Int): Int = if (b == 0) a else gcd(b, a % b)
}
```
수학 문제

꼬리재귀를 이용해서 최소공배수를 나타내는 함수를 만들었다