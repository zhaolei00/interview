### 1.Lua
    减少RTT，一次可以执行多个命令。
    原子操作。不会被其他命令插入。
    复用性。Lua脚本只需要发送一次，后续只发送参数即可。
    用途: 限流(固定窗口算法、滑动窗口算法、漏桶、令牌桶)