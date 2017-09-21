#Android关于OOM的解决方案
##OOM
* 内存溢出（Out Of Memory）
* 也就是说内存占有量超过了VM所分配的最大(Dalvik Heap size)可以通过adb shell getprop | grep dalvik.vm.heapgrowthlimit查看限制大小



##出现OOM的原因
1. 加载对象过大
2. 相应资源过多，来不及释放*
3. 过多的内存泄露

##如何解决
1. 在内存引用上做些处理，常用的有软引用、强化引用、弱引用
2. 在内存中加载图片时直接在内存中作处理，如图片边界压缩
3. 动态回收内存*
4. 优化Dalvik虚拟机的堆内存分配(调整最大最小空闲内存以及堆利用率) 通过android:largeHeap = true使用dalvik.vm.heapsize
5. 自定义堆内存大小*


