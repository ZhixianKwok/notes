### 字符串方法

#### 判断字符串占用多少个字节 ?

> 将双字节字符替换为 aa ，如果不是双字节，那就是单字节
>
> - \u0391-\uFFE5 匹配双字节字符（汉字+符号）

```js
const byteLen = str.replace(/[\u0391-\uFFE5]/g, "aa").length;
```
