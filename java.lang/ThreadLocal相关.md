# 1. ThreadLocal原理
    有个hashcode，每次新建自增一个值。以获取最优分布的哈希值。
    在线程上有两个ThreadLocalMap属性, 来存储线程隔离的值。
        threadLocals: 父不往子线程不进行同步数据。
        inheritableThreadLocals: 父往子线程进行同步数据。
    ThreadLocalMap就是自定义的Map，Entry的key是WeakReference(ThreadLocal类型)。哈希冲突采用开放地址法。HashMap是链地址法。
# 2. InheritableThreadLocal 和 ThreadLocal 的区别?
    InheritableThreadLocal 是 ThreadLocal的子类。实际就是获取Thread的不同ThreadLocalMap属性。