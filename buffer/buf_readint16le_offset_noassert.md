<!-- YAML
added: v0.5.5
-->

* `offset` {Integer} 开始读取的位置，必须满足：`0 <= offset <= buf.length - 2`
* `noAssert` {Boolean} 是否跳过 `offset` 检验？**默认:** `false`
* 返回: {Integer}

用指定的尾数格式（`readInt16BE()` 返回大尾数，`readInt16LE()` 返回小尾数）从 `buf` 中指定的 `offset` 读取一个有符号的16位整数值。

设置 `noAssert` 为 `true` 则 `offset` 可超出 `buf` 的末尾，但后果是不确定的。

从 `Buffer` 中读取的整数值会被解析为二进制补码值。

例子：

```js
const buf = Buffer.from([0, 5]);

// 输出: 5
console.log(buf.readInt16BE());

// 输出: 1280
console.log(buf.readInt16LE(1));

// 抛出异常: RangeError: Index out of range
console.log(buf.readInt16LE(1));
```

