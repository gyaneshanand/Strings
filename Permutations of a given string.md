<h2> Permutations of a given string : </h2>
Given a string S. The task is to print all permutations of a given string in lexicographically sorted order.
 
**Example 1:**

Input: ABC <br/>
Output: <br/> 
ABC ACB BAC BCA CAB CBA <br/>
Explanation: Given string ABC has permutations in 6 forms as ABC, ACB, BAC, BCA, CAB and CBA .

**Example 2:**

Input: ABSG <br/>
Output: <br/>
ABGS ABSG AGBS AGSB ASBG ASGB BAGS BASG BGAS BGSA BSAG BSGA GABS GASB GBAS GBSA GSAB GSBA SABG SAGB SBAG SBGA SGAB SGBA <br/>
Explanation: Given string ABSG has 24 permutations.

----------------------------------------------------------------------------------------------------------------------------------------

<h3> Solution : </h3>

Time Complexity :

```java
class Solution {
    public List<String> find_permutation(String S) 
    {
        char[] ch=S.toCharArray();
        Arrays.sort(ch);
        List<String> ans = permutation(new String(ch),"");
        return ans;
    }
    public List<String> permutation(String str, String s)
    {
        ArrayList<String> arr=new ArrayList<String>();
        if(str.length()==0)
            arr.add(s);
        int i;
        for(i=0;i<str.length();i++)
        {
            char ch=str.charAt(i);
            String s1=str.substring(0,i)+str.substring(i+1);
            permutation(s1,s+ch);
        }
        for(i=0;i<arr.size();i++)
            System.out.print(arr.get(i)+" ");
        return arr;
    }
}

```


