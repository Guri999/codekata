K번째수
=
## 🕵️문제설명
배열 array의 i번째 숫자부터 j번째 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하려 합니다.

예를 들어 array가 [1, 5, 2, 6, 3, 7, 4], i = 2, j = 5, k = 3이라면

array의 2번째부터 5번째까지 자르면 [5, 2, 6, 3]입니다.
1에서 나온 배열을 정렬하면 [2, 3, 5, 6]입니다.
2에서 나온 배열의 3번째 숫자는 5입니다.
배열 array, [i, j, k]를 원소로 가진 2차원 배열 commands가 매개변수로 주어질 때, commands의 모든 원소에 대해 앞서 설명한 연산을 적용했을 때 나온 결과를 배열에 담아 return 하도록 solution 함수를 작성해주세요.


## ⚠️제한사항

- array의 길이는 1 이상 100 이하입니다.
- array의 각 원소는 1 이상 100 이하입니다.
- commands의 길이는 1 이상 50 이하입니다.
- commands의 각 원소는 길이가 3입니다

## 🔎로직설명

### 내코드
```kotlin
fun solution(array: IntArray, commands: Array<IntArray>): IntArray {
    val answer = IntArray(commands.size)

    for (i in 0 until commands.size) {
        var arrIn = array.sliceArray(commands[i][0]-1 until commands[i][1])
        arrIn.sort()
        answer[i] = arrIn[commands[i][2]-1]
    }
    return answer
}
```
i를 배열의 사이즈 만큼 반복한다

`sliceArray`로 배열을 잘라주고 정렬

k번째 있는(commands[i][2]= k) arrIn의 원소를 answer에 넣어준다


### 다른사람들

```kotlin
fun solution(array: IntArray, commands: Array<IntArray>): IntArray {
            return commands.map { command ->
                array.slice(IntRange(command[0] - 1, command[1] - 1)).sorted()[command[2] - 1]
            }
                .toIntArray()
        }
```
commands를 매핑하고 array에서 범위를 정해 slice해준뒤 정렬한 배열에 [command[2] - 1]를 리턴한다