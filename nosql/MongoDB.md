# 1. 什么是MongoDB?
    文档型数据库。
# 2. 优缺点
优点:
- 高并发读取 为啥高性能，为啥比MySQL快。
- 海量数据存储
- 结构不固定
缺点:
- 不支持事务?
# 3. 索引
    用B树数据结构来实现。平衡搜索多叉树，每个节点都放数据。B+树是只有叶子节点才放数据。
- 单字段索引
- 复合索引
# 4. 复制集
    主节点和多个从节点，一般加起来是奇数。数据同步通过oplog来同步。
# 5. 选举
    较新的oplog、配置的优先级、和多数节点能保持连接。
# 6. 读写策略
    写策略: writeConcern参数: 有多少个节点成功才算成功。默认为1。majority是大多数节点成功才成功。all所有节点成功才成功。
    读策略:
        readPreference: 只主，优先主，只从，优先从，最近的节点。
        readConcern: majority 读取大多数节点提交的数据。
# 7. 分片集群
    分片方式: 基于范围、哈希、自定义。