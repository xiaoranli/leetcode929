# 20、leetcode929. 独特的电子邮件地址
解法一：
--  
思路：
--
    去重想到set集合。    
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/18 13:00
 * @descriptor  929. 独特的电子邮件地址
 */
public class NumUniqueEmails_929 {
    public static int numUniqueEmails(String[] emails) {
        Set<String> set = new HashSet<>();
        for (String s:emails) {
            int i = s.indexOf('@');
            String left = s.substring(0,i);
            String right = s.substring(i);
            if(left.contains("+")){
                left = left.substring(0,s.indexOf("+"));
               left = left.replace(".","");
            }
            set.add(left+right);
        }
        return set.size();
    }
    public static void main(String[] args) {
        String[] s  = {"test.email+alex@leetcode.com",
                "test.e.mail+bob.cathy@leetcode.com",
                "testemail+david@lee.tcode.com"};
        int i = numUniqueEmails(s);
        System.out.println(i);
    }
}
</pre>
