# Golf scores

Consider the following functions of n, a positive whole number:

* M(n), the largest number that can be formed with n characters,
* m(n), the smallest number that can be formed with n characters,
* p(n), the smallest *positive* number that can be formed with n characters.

All of these are in `Python`.

## Current records

Here is the best we've done so far

n | Best M(n) | My best M(n) | Code
---|---|---|---
1|9|9|`9`
2||99|`99`
3||999|`999`
4||[9]|`9**9`
5||[95]|`9**99`
6||[1047]|`9**999`
7||[405997935]|`9**9**9`
8||[[94]]|`9**9**99`
9||[[1025]]|`9**9**999`

n | Best m(n) | My best m(n) | Code
---|---|---|---
1||0|`0`
2||-9|`-9`
3||-99|`-99`
4||-999|`-999`
5||[9]|`-9**9`
6||[95]|`-9**99`
7|||``
8|||``
9|||``

n | Best p(n) | My best p(n) | Code
---|---|---|---
1||1|`1`
2||0.1|`.1`
3||0.01|`.01`
4||0.001|`.001`
5||[-9]|`9**-9`
6||[-95]|`9**-99`
7||[-1047]|`9**-999`
8||[405997935]|`9**-9**9`
9|||``
