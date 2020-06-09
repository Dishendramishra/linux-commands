### sed 

sed = stream editor



**Replacing using regular expression:**

1. **whitespaces**

   

   replace first occurrence only

   ```shell
   ➜  ~ echo "==== abcd ====" | sed  's/[[:space:]]//'
   ====abcd ====
   ```

   

   replace all occurrences (`g` for global)

   ```shell
   ➜  ~ echo "==== abcd ====" | sed  's/[[:space:]]//g'
   ====abcd====
   ```

   

2. **alpha or num or alphanum**

   ```shell
   ➜  ~ echo "====abcd====" | sed  's/a[a-z]*d/new/'
   ====new====
   ```

   

   for more options check table below:

   | type                                                         | class name                |
   | ------------------------------------------------------------ | ------------------------- |
   | alpha                                                        | [[:alpha:]]     [a-zA-z]  |
   | num                                                          | [[:digit:]]       [0-9]   |
   | alphanum                                                     | [[:alnum:]]   [0-9A-Za-z] |
   | lowercase                                                    | [[:lower:]]    [a-z]      |
   | uppercase                                                    | [[:upper:]]   [A-Z]       |
   | space <br />(tab, newline, vertical tab, <br />form feed, carriage return, <br />and space) | [[:space:]]               |

   for more see [link](https://www.gnu.org/software/sed/manual/html_node/Character-Classes-and-Bracket-Expressions.html).



### backtick (`)

Everything you type between backticks is evaluated (executed) by the shell before the main command and the *output* of that execution is used by that command, just as if you'd type that output at that place in the command line.

Command below will `cd` to location of `bash`

```shell
cd `which bash | sed 's/\/bash//'`
```