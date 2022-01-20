# RepaintBoundary

> 为其子项创建单独的显示列表的小部件

**当子部件与父部件刷新时间不同时，可以用它来提高性能**

下面代码可以在列表滚动的时候避免重绘 item

这是因为列表在滚动过程中判断了 child 的 isRepaintBoundary 方法，
在 paintChild 方法中，只要 child.isRepaintBoundary 为 false，那么就会执行 paint 方法，这里就直接跳过了 shouldRepaint。

```dart
RepaintBoundary(
    child: Container(),
);
```