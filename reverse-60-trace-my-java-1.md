## Trace my Java \#1

### Reverse Engineering, 60pts

You may be able to find this problem elsewhere, but try solving it yourself. Trace down this program, and figure out the flag. The flag is NOT in standard format, but starts with character `a`and ends with character `s`.

**No hints.**

```
/*
 * Code written by Kiernan Dempsey
 * Rights reserved for original author.
 */
import java.util.Scanner;
​
    public static void main(String[] args)
    {
        Scanner s = new Scanner(System.in);
        String input = s.next();
        if(input.length() != 9)
        {
            System.out.println("WRONG: try again! ");
            input = s.next();
        }
        else
        {
            String solution = change1(change2(input));
            if(solution == "djckktjbq")
                System.out.println("The flag is: " + input);
            else
            {
                System.out.println("WRONG: try again! ");
                input = s.next();
            }
        }
    }
    public static String change1(String w)
    {
        int[] arr = {4, 3, 5, 6, 1, 2, 3, 3, 1};
        char[] tmp = new char[9];
        for(int i = 0; i < 9; i++)
        {
            tmp[i] = (char)(w.charAt(i) + arr[i]);
        }
        return new String(tmp);
    }
    public static String change2(String w)
    {
        int[] arr = {1, 7, 5, 3, 5, 4, 2, 6, 3};
        char[] tmp = new char[9];
        for(int i = 0; i < 9; i++)
        {
            tmp[i] = (char)(w.charAt(i) - arr[i]);
        }
        return new String(tmp);
    }
```



