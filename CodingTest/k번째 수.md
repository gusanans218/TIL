# K번째 수
```kt
class Solution {
    fun solution(array: IntArray, commands: Array<IntArray>): IntArray {
        var answer = intArrayOf()
        var tempArray1 = intArrayOf()
        var tempArray2 = intArrayOf()
        var tempArrayLength = 0
        var startIndex = 0
        var endIndex = 0

        var tempArrayLength2 = commands.size-1
        tempArray2 =  IntArray(tempArrayLength2+1, { 0 })

        for(h in 0..tempArrayLength2) {

            tempArrayLength = commands[h][1] - commands[h][0] + 1
            startIndex = commands[h][0] - 1
            endIndex = commands[h][1] - 1


           var k = 0
            tempArray1 =  IntArray(tempArrayLength, { 0 })
            for (i in startIndex..endIndex) {
                tempArray1[k] = array[i]
                k++
            }

            tempArray1 = tempArray1.sortedArray()

            tempArray2[h] = tempArray1[commands[h][2] - 1]

        
        }

        answer = tempArray2
        return answer
        }
}