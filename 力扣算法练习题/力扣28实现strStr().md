### ����˼·
����ƥ��,����ָ���ƶ���������
### ����

```java
class Solution {
    public int strStr(String haystack, String needle) {
        //�ַ���ת���ַ�����
        char []c1=haystack.toCharArray();
        char []c2=needle.toCharArray();
        //res��¼haystackƥ���������needle���ַ���ȵ�index
        int res=0;
        //���������ָ��
        int first=0,second=0;
        int length1=c1.length,length2=c2.length;
        while(first<length1){
            if(second==0){
                    res=first;
                }
                //ָ��ָ����ַ����,�ַ�����ƶ�,����ƥ��
            if(c1[first]==c2[second]){
                first++;
                second++;
                //ƥ����ɷ���res
                if(second==length2)
                return res;
            }else{
                //ƥ��ʧ��,needle�ص��ַ�������
                first=res+1;
                second=0;
            }
        }
        return -1;
    }
}
```