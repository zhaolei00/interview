# 1. Optional是什么?
    是一个对象容器，为了解决避免NPE异常书写麻烦而产生的类。更符合函数式编程。
# 2. Optional设计原理?
    构造私有化，创建Optional对象都是通过静态方法来创建。
    如果值为空，都是返回同一个空对象。内存优化。这个很重要，所有操作都用这个空对象来减少内存使用。
# 3. 都有哪些操作?
    of()、ofNullable()、filter()、map()、flatMap()
# 4. 默认实现的数据类型
    OptionalDouble、OptionalInt、OptionalLong