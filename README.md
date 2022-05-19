# LeetCode-NoteBook
## 动态规划
* 53.最大子数组和
```java
class Solution {
    public int maxSubArray(int[] nums) {
        int n=nums.length;
        if(n==0) return 0;
        //dp 数组的含义：以 nums[i] 为结尾的「最⼤⼦数组和」为 dp[i]。
        //dp[i] 有两种「选择」，要么与前⾯的相邻⼦数组连接，形成⼀个和更⼤的⼦数组；要么不与前⾯的⼦数组连接，⾃成⼀派，⾃⼰作为⼀个⼦数组。
        int[] dp=new int[n];
        dp[0]=nums[0];//第一个元素前面没有子数组
        for(int i=1;i<n;i++)
            dp[i]=Math.max(nums[i],nums[i]+dp[i-1]);
        int res=Integer.MIN_VALUE;
        for(int i=0;i<n;i++)
        res=Math.max(res,dp[i]);
        return res;
    }
}
```
