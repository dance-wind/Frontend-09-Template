学习笔记

## [乔姆斯基谱系](https://zh.wikipedia.org/wiki/乔姆斯基谱系)：

是计算机科学中刻画形式文法表达能力的一个分类谱系，是由诺姆·乔姆斯基于 1956 年提出的。它包括四个层次：

- 0- 型文法（无限制文法或短语结构文法）包括所有的文法。
- 1- 型文法（上下文相关文法）生成上下文相关语言。
- 2- 型文法（上下文无关文法）生成上下文无关语言。
- 3- 型文法（正规文法）生成正则语言。

## 产生式：

 在计算机中指 Tiger 编译器将源程序经过词法分析（Lexical Analysis）和语法分析（Syntax Analysis）后得到的一系列符合文法规则（Backus-Naur Form，BNF）的语句。

### [巴科斯诺尔范式](https://zh.wikipedia.org/wiki/巴科斯范式)：

即巴科斯范式（英语：Backus Normal Form，缩写为 BNF）是一种用于表示上下文无关文法的语言，上下文无关文法描述了一类形式语言。

- BNF是一种用于表示上下文无关文法的语言
- 用尖括号括起来的名称来表示语法结构名
- 语法结构分成基础结构和需要用其他语法结构定义的复杂结构
  - 基础结构称终结符
  - 复合结构称非终结符
- 引号和中间的字符表示终结符
- 可以有括号
- *表示重复多次
- | 表示或
- +表示至少一次

```
<MultiplicativeExpression>::= <Number> |
    <MultiplicativeExpression> "*" <Number> |
    <MultiplicativeExpression> "/" <Number> |
<AddtiveExprssion>::=<MultiplicativeExpression> |
    <AddtiveExprssion>"+" <MultiplicativeExpression> |
    <AddtiveExprssion>"-" <MultiplicativeExpression>

四则运算：1 + 2 * 3
终结符：Number 、+ 、- 、* 、/
非终结符：MultiplicativeExpression 、AddtiveExprssion
```

### 通过产生式理解乔姆斯基谱系

- 0型 无限制文法 ?::=?
- 1型 上下文相关文法 ?< A >?::=?< B >?
- 2型 上下文无关文法 < A > ::=?
- 3型 正则文法 < A >::=< A >?

### 编程语言性质

#### 1、图灵完备性

- 命令式——图灵机
  - goto
  - if和while
- 声明式——lambda -递归

#### 2、动态与静态

- 动态
  - 在用户的设备/在线服务器上
  - 时机：产品实际运行时
  - 术语：Runtime
- 静态
  - 在程序员的设备上
  - 时机：产品开发时
  - 术语：Compiletime

#### 3、类型系统

- 动态类型系统与静态类型系统
- 强类型(无隐式转换)与弱类型(有隐式转换)
- 复合类型
  - 结构体
  - 函数签名（参数类型，返回值类型）
- 子类型
- 泛型
  - 逆变/协变

### javascript 类型

- Numble
- String
- Boolean
- Null
- Undefined
- Object
  - obj三要素：唯一标识、状态、行为
  - 设计原则：设计对象的状态和行为时，总是遵循 "行为改变状态" 的原则
- Symbol