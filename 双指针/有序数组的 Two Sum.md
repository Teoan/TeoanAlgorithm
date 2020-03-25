# 有序数组的 Two Sum 

```
Input: numbers={2, 7, 11, 15}, target=9
Output: index1=1, index2=2
```
**题目描述**：题目描述：在有序数组中找出两个数，使它们的和为 target。

**思路**：使用双指针，index1指向小的元素，index2指向大的元素，index1从前往后扫描，index2从后往前扫描。

* 当两元素和sum==target时，得到结果。
* 当sum>target时，移动index2，使sum小一点。
* 当sum<target时，移动index1，使sum大一点。

数组中的元素最多遍历一次，时间复杂度为 O(N)，空间复杂度为 O(1)。

```java
    public int[] getTowSum(int[] numbers, int target){
        int index1 = 0;
        int index2 = numbers.length-1;
        while(index1<index2){
            if (numbers[index1]+numbers[index2]==target) {
                return new int[]{index1+1,index2+1};
            }else if(numbers[index1]+numbers[index2]>target){
                index2--;
            }else{
                index1++;
            }
        }
        return null;
    }
```