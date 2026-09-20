<!-- problem:start -->

# [Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement)

## Description

<!-- description:start -->

<p>You are given a string <code>s</code> and an integer <code>k</code>. You can choose any character of the string and change it to any other uppercase English character. You can perform this operation at most <code>k</code> times.</p>

<p>Return <em>the length of the longest substring containing the same letter you can get after performing the above operations</em>.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;ABAB&quot;, k = 2
<strong>Output:</strong> 4
<strong>Explanation:</strong> Replace the two &#39;A&#39;s with two &#39;B&#39;s or vice versa.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;AABABBA&quot;, k = 1
<strong>Output:</strong> 4
<strong>Explanation:</strong> Replace the one &#39;A&#39; in the middle with &#39;B&#39; and form &quot;AABBBBA&quot;.
The substring &quot;BBBB&quot; has the longest repeating letters, which is 4.
There may exists other ways to achieve this answer too.</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= s.length &lt;= 10<sup>5</sup></code></li>
	<li><code>s</code> consists of only uppercase English letters.</li>
	<li><code>0 &lt;= k &lt;= s.length</code></li>
</ul>


<!-- description:end -->

## Solutions

<!-- solution:start -->

<!-- tabs:start -->

#### Java

```java
class Solution {
    public int characterReplacement(String s, int k) {
        int []a=new int[256];
        int low=0;
        int max=0;
        int len=0;
        int res=0;
        for(int high=0;high<s.length();high++){
            char c=s.charAt(high);
            a[c]++;
            max=Math.max(max,a[c]);
            len=high-low+1;
            int diff=len-max;
            while(diff>k){
                a[s.charAt(low)]--;
                low++;
                max=Math.max(max,a[c]);
                len=high-low+1;
                diff=len-max;
            }
            len=high-low+1;
            res=Math.max(len,res);
        }
        return res;

    }
}
```

<!-- tabs:end -->

<!-- solution:end -->

<!-- problem:end -->
