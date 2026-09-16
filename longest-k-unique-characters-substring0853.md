<!-- problem:start -->

# [Longest Substring with K Uniques](https://practice.geeksforgeeks.org/problems/longest-k-unique-characters-substring0853)

## Description

<!-- description:start -->

<p data-start="157" data-end="313"><span style="font-size: 14pt;">You are given a string <strong>s</strong> </span><span style="font-size: 18.6667px;">consisting only lowercase alphabets </span><span style="font-size: 14pt;">and an integer </span><strong style="font-size: 14pt;">k</strong><span style="font-size: 14pt;">. Your task is to find the <strong>length </strong>of the <strong>longest substring</strong> that contains exactly </span><strong style="font-size: 14pt;">k</strong><span style="font-size: 14pt;"> distinct characters.</span></p><p data-start="157" data-end="313"><span style="font-size: 14pt;"><span style="font-size: 14pt;"><strong>Note :</strong> If no such substring exists, return </span><strong style="font-size: 14pt;">-1</strong><span style="font-size: 14pt;">.&nbsp;</span></span></p><p><span style="font-size: 18px;"><strong>Examples:</strong></span></p><pre><span style="font-size: 18px;"><strong>Input: </strong>s = "aabacbebebe</span><span style="font-size: 18px;">", k = 3
<strong>Output:</strong> 7
<strong>Explanation</strong>: The longest substring with exactly 3 distinct characters is "cbebebe", which includes 'c', 'b', and 'e'.
</span></pre><pre><span style="font-size: 18px;"><strong>Input</strong>: s = "aaaa", k = 2
<strong>Output:</strong> -1
<strong>Explanation</strong>: There's no substring with 2 distinct characters.<br></span></pre><pre><span style="font-size: 14pt;"><strong>Input: </strong>s = "aabaaab", k = 2
<strong>Output:</strong> 7
<strong>Explanation</strong>: </span><span style="font-size: 14pt;">The entire string "aabaaab" has exactly 2 unique characters 'a' and 'b', making it the longest valid substring.</span></pre>

<!-- description:end -->

## Solutions

<!-- solution:start -->

<!-- tabs:start -->

#### Java

```java
class Solution {
    public int longestKSubstr(String s, int k) {
                int low=0;
                int res=-1;
                HashMap<Character,Integer>f=new HashMap<>();
                for(int high=0;high<s.length();high++){
                    char c= s.charAt(high);
                    f.put(c,f.getOrDefault(c,0)+1);
                    while(f.size()>k){
                        char l=s.charAt(low);
                        f.put(l,f.get(l)-1);
                        if(f.get(l)==0)
                        f.remove(l);
                        low++;
                    }
                    if(f.size()==k){
                        int len=high-low+1;
                        res=Math.max(res,len);
                    }
                }
                return res;
    }
}
```

<!-- tabs:end -->

<!-- solution:end -->

<!-- problem:end -->
