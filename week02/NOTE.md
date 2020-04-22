# 每周总结可以写在这里

### 编程语言通识

系统类型

- 动静划分
  - 动态类型系统
  - 静态类型系统
- 按是否隐式转换划分
  - 强类型
  - 弱类型
- 按复合类型划分
  - 结构体
  - 函数签名
- 加入继承后
  - 逆变
  - 协变

图灵完备性

- 命令式-图灵机
  - 用goto实现
  - 用if和while实现
- 声明式-lambda
  - 用递归实现

### Javascript词法、类型

unicode

- CJK
- BMP基本字符
- \u转义

inputElement

- whiteSpack
  - <TAB>
  - <VT>纵向制表符
  - <FF>Form Feed
  - <SP>
  - <NBSP> 处理排版时，如果是普通的SP，会在一行放不下时，将它左右断开;<NBSP>它的左右不会断开
  - <ZWNBSP>
  - <USP>
- LineTerminator
  - <LF>Line Feed \n推荐开发时使用
  - <CR>回车\r
  - <LS>
  - <PS>
- Comment
  - //
  - /**/
- Token
  - Punctuator符号
  - IdentifierName
    - Identifier标识符
      - 变量名
      - 属性
    - Keywords关键字
  - Literal直接量
    - Number
      - DecimalLiteral(十进制)
      - BinaryIntegerLiteral(二进制)
      - OctallIntegerLiteral(八进制)
      - HexIntegerLiteral(十六进制)
    - String
      - Character字符
      - code point码点
      - Encoding
        - UTF-8
        - UTF-16实际内存中是这种方式的
      - grammar
        - "abc"
        - 'abc'
        - `abc`
    - Boolean
    - Null
    - Undefined