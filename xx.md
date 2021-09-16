#### 先遍历判断运输类型 type

#### 定义字典：

- 网点 --> 转运中心：1
- 转运中心 --> 转运中心 ：2
- 转运中心(集散) --> 集散 ：3
- 转运中心 --> 集散: 4
- 其他：0

#### 谈论 A=>B 的可能

```js
if (A.type == 0) {
  //忽略
} else if (A.type == 1) {
  // 网点(A)-->转运中心(B)
  // 直接计算下一个节点的应发时间和 应到时间
  B.shouldSend = getSendTime(A.到达时间 + 1(2), B.type, B.cty, C.city);
  B.sholdArrived = getArriveTime(A.到达时间 + 1(2), B.type, B.cty, C.city);
} else if (B.type == 2 || B.type == 3) {
  // 转运中心(B) --> 转运中心C（集散）区别就是从干线表还是支线表获取时间

  if (B.arrive + 1(2) > B.shouldSend) {
    // 判定 A 节点延误
    // 举个例子：最早班次 B.shouldSend 是 12:00，B.arrive 是 11:30
    // 11:30 + 1 = 12:30 >12:00 ，判断上一个节点到达延误
  } else if (B.send > B.shouldSend) {
    // 判断 B 节点延误
    //举个栗子：由于上个节点正常到达，B 自身原因没发
  } else {
    // 计算下一个节点的应发时间和 应到时间
    C.shouldSend = getSendTime(B.sholdArrived + 1(2), C.type, C.cty, D.city);
    C.sholdArrived = getArriveTime(
      B.sholdArrived + 1(2),
      C.type,
      C.cty,
      D.city
    );
  }
} else if (type === 4) {
  // 集散(C)->网点（D）
  if (D.arrive > D.sholdArrived) {
    //判断C延误
  }
}
```
