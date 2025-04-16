# 1. 官方文档
    https://arthas.aliyun.com/doc/quick-start.html
# 2. Arthas原理
    java -jar 启动时，就是把arthas-agent.jar加载到目标进程中。和目标进程在启动参数中加javaagent参数一样。
    在agent入口类AgentBootstrap中，premain()和agentmain()方法都实现了。也就是说可以以两种形式进行agent。
    一种是启动时通过javaagent参数调用premain方法来agent。另一种是通过工具类在运行时加载agent，调用agentmain方法来agent。

    注意: attach需要用到tools.jar，这个是默认没有导入的。