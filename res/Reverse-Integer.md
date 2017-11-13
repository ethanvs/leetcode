# Reverse Integer

### 原题

Given a 32-bit signed integer, reverse digits of an integer.

#### Example 1:

    Input: 123
    Output:  321

#### Example 2:


    Input: -123
    Output: -321

#### Example 3:

    Input: 120
    Output: 21
#### Note:
Assume we are dealing with an environment which could only hold integers within the 32-bit signed integer range. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.

### 翻译

给定一个32位有符号整数，整数的反转数字。

> 注意：假设我们正在处理一个只能保持32位有符号整数范围内的整数的环境。出于这个问题的目的，假设你的函数在反向整数溢出时返回0。

### 结果

```javascript

/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
    if(x >= 0) {
        x = String(x);
        var res = parseInt(x.split('').reverse().join(''));
        return res.toString(2).length > 31 ? 0 : res;
    } else {
        x = String(x + (0 - x)*2);
        var res = parseInt(x.split('').reverse().join(''));
        return res.toString(2).length > 31 ? 0 : (res - res*2);
    }
};


```