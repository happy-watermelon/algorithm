### 解题思路
暴力匹配,两个指针移动就完事了
### 代码

```java
class Solution {
    public int strStr(String haystack, String needle) {
        //字符串转成字符数组
        char []c1=haystack.toCharArray();
        char []c2=needle.toCharArray();
        //res记录haystack匹配过程中与needle首字符相等的index
        int res=0;
        //两个数组的指针
        int first=0,second=0;
        int length1=c1.length,length2=c2.length;
        while(first<length1){
            if(second==0){
                    res=first;
                }
                //指针指向的字符相等,字符向后移动,继续匹配
            if(c1[first]==c2[second]){
                first++;
                second++;
                //匹配完成返回res
                if(second==length2)
                return res;
            }else{
                //匹配失败,needle回到字符数组首
                first=res+1;
                second=0;
            }
        }
        return -1;
    }
}
```