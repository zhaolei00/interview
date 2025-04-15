# 1. LocalTime原理
    LocalTime原理是时、分、秒、纳秒四个不可变字段组成。
    时分秒都是1字节存储(byte)，纳秒因为最大是10亿，所以用int存储。节约内存。
    都是通过计算出纳秒值，再计算出具体的时分秒。如果是整点，会用缓存对象。
# 2. 创建LocalTime对象
    System.currentTimeMillis(): 时间戳是东0区的从1970年1月1日 0时0分0秒到现在的毫秒数。
    在生成LocalTime时，是根据时间戳和时区偏移量计算的时分秒纳秒。
    比较时，时分秒纳秒一次比较，只有有不同就跳出。
# 3. LocalDate原理
    用年月日三个不可变字段组成。
# 4. 创建LocalDate对象
    根据时间戳和时区偏移量，计算出年月日(此算法很复杂)。
# 5. LocalDateTime原理
    有LocalDate和LocalTime两个字段。
# 6. ZoneDateTime原理
    保存LocalDateTime、偏移量、时区三个不可变字段。