- 写一个正则表达式 匹配所有 Number 直接量

  ``` javascript
   /((((0|[1-9]([0-9]+)?)\.([0-9]+)?([eE][+-]?[0-9]+)?|\.[0-9]+([eE][+-]?[0-9]+)?|(0|[1-9]([0-9]+)?)([eE][+-]?[0-9]+)?)|0[bB][01]+|0[oO][0-7]+|0[xX][0-9a-fA-F]+))/
  
  ```

  

- 写一个 UTF-8 Encoding 的函数

  ```javascript
  function encodeCodePoint(code) {
    if (code <= 0x7F) {
      return [code]
    } else if (code <= 0x7FF) {
      return [
        0xC0 | ((code >> 6) & 0x1F),
        0x80 | ((code) & 0x3F),
      ]
    } else if (code <= 0xFFFF) {
      return [
        0xE0 | ((code >> 12) & 0xF),
        0x80 | ((code >>  6) & 0x3F),
        0x80 | ((code) & 0x3F)
      ]
    } else {
      return [
        0xF0 | ((code >> 18) & 0x7),
        0x80 | ((code >> 12) & 0x3F),
        0x80 | ((code >>  6) & 0x3F),
        0x80 | ((code) & 0x3F)
      ]
    }
  }
  
  function UTF8_Encoding(string) {
    const codes = [];
    for (let ch of string) {
      const bytes = encodeCodePoint(ch.codePointAt(0));
      codes.push(...bytes);
    }
    const array = new Uint8Array(codes);
    return array.buffer;
  }
  ```

  

- 写一个正则表达式，匹配所有的字符串直接量，单引号和双引号

```javascript
/ (("([^"\r\n\u2028\u2029\\]|\u2028|\u2029|\\((['"\bfnrtv]|[^'"\bfnrtvdxu\r\n\u2028\u2029])|0(?!d)|x[0-9a-fA-F][0-9a-fA-F]|(u[0-9a-fA-F]{4}|u{(0[0-9a-fA-F]{5}|10[0-9a-fA-F]{4}|[0-9a-fA-F]{1,4})}))|\\(\r\n|[\r\n\u2028\u2029]))*"|'([^'\r\n\u2028\u2029\\]|\u2028|\u2029|\\((['"\bfnrtv]|[^'"\bfnrtvdxu\r\n\u2028\u2029])|0(?!d)|x[0-9a-fA-F][0-9a-fA-F]|(u[0-9a-fA-F]{4}|u{(0[0-9a-fA-F]{5}|10[0-9a-fA-F]{4}|[0-9a-fA-F]{1,4})}))|\\(\r\n|[\r\n\u2028\u2029]))*'))
/
```

