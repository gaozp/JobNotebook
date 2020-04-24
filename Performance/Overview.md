#### 以下是性能优化重要的参考文档：

##### Android core technologies，核心模块的简要介绍都在这里，ART/Debugging/Performance这几个模块需要详细看看，不过Performance介绍的很少
https://source.android.com/devices/tech/

##### Android Interfaces and Achiteture，比上一篇的内容更加深入，可以深入学习一下重要模块
https://source.android.com/devices/

1. Architecture，需要通过这里架构图完全理解整个Android系统软件的工作流程
https://source.android.com/devices/architecture/

2. Graphics，这是详细讲述Android graphics的最好文档
https://source.android.com/devices/graphics/

3. Input，可以根据需要阅读
https://source.android.com/devices/input/

##### Evaluating Performance，这篇一定要重点阅读，包含systrace的使用/典型问题的debug等等
https://source.android.com/devices/tech/debug/eval_perf

##### Bootcamp文档，bootcamp是Google为手机厂商组织，深入介绍新版本系统特性的会议，包含很多性能相关的内容
2018: Systems，Runtime
2016: BootCamp 2016 System performance
Linux内核
内存
调度
#### 看完以上文档后需要掌握的知识点：

##### 熟悉应用启动和view绘制的大致流程
##### systrace使用：
1. 熟悉input/gfx/am/wm/view/sched/freq/binder_driver/dalvik等类别的含义
2. 在systrace上跟踪整个渲染流程，包括input发送/view draw/render thread/buffer dequeue, queue/
3. surfaceflinger合成
4. 在systrace上识别应用启动的各个环节
5. 在systrace上确认task的运行状态，running/runnable/uninterruptible sleep/sleep各自代表的含义
6. 进程间wait关系的确认，java等锁如何识别owner，binder transaction如何识别对端，uninterruptible sleep状态如何确认wake up进程
##### Linux kernel
1. 调度基本基本概念以及在systrace上分析task运行情况
2. page fault原理以及内存回收的触发时机和主要回收手段，lowmemorykiller/zRAM的工作原理