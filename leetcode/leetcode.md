## leetcode总结

### 一、链表

#### 1、反转链表

#### 2、相交链表

#### 3、合并两个有序链表

### 二、哈希表

#### 1、有效的字母异位词

[242. 有效的字母异位词 - 力扣（LeetCode）](https://leetcode.cn/problems/valid-anagram/)

```c++
// 定义数组-26, 
bool isAnagram(string s, string t) {
    int num[26] = {0};
    for(int i=0;i<s.size();i++){
    	num[s[i]-'a']++;
    }
    for(int j=0;j<t.size();j++){
    	num[t[j]-'a']--;
    }
    for(int i=0;i<26;i++){
        if(num[i]!=0){
        	return false;
        }
    }
    return true;
}
```

```java
public boolean isAnagram(String s, String t) {
    char[] record = new char[26];
    for(char i : s.toCharArray()){
        // System.out.println(i);
        record[i - 'a']++;
    }
    for(char j : t.toCharArray()){
    	record[j - 'a']--;
    }
    for(int i : record){
        if(i != 0){
        	return false;
        }
    }
    return true;
}
```

#### 2、两个数组的交集



