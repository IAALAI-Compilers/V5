# V5

***

`V5` is a `JavaScript` engine developed using `C++`, which aims to imitate the design and functions of the open source engine `V8` developed by Google.

`V5` partially implements ECMAScript as specified in ECMA-262, with some features omitted or simplified

`V5` is a graduation project that showcases an understanding and application of the principles and completion of `JavaScript` engine development

## About

V5 尽可能实现EMCAScript的大部分功能.该项目使用了Cmake进行管理.同时在debian的llvm和windows的msvc下进行测试和开发.

V5 可以编译和执行JavaScript代码,同时处理对象的内存分配,并且收集不再需要的对象.

JavaScript 通常用于浏览器脚本,同时也能用于服务端应用程序开发.V5并不提供诸如global这样的全局对象.V5只提供EMCA标准中指定的数据类型,运算符,对象和函数.

## Workflow

### flow chart

``` mermaid
graph TB
    RawData(Network , Service Worker , Cache)
    --> |Bianry Byte Stream| Buffer(Byte Stream Decoder)
    --> |cast char| string(Parser)
    --> |analysis| AST(Ignition Interpreter)
    --> |hotspot| exec(TurboFan Optimizer)
```

### brief overview

先从各种位置传入原始数据,比如网络或者缓存.

然后读取字节流将其转化为字符串.

将字符串构建为抽象语法树

由 `Ingition` 转换字节码进行执行

如果是热点代码,就交由 `TurboFan` 再次进行优化
