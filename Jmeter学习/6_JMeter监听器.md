## 1. JMeter监听器
长时间执行测试计划使用的监听器主要是Summary Report或者Aggregate Report


### 1.1 Summary Report
Summary Report以表格的形式显示取样器结果，如果不同的取样器(不同请求)，拥有相同的名字，那么在Summary Report中会统计到同一行，所以在给取样器取别名时最好不要为空，按照业务功能来取名
![Summary Report](image\6-1.png)


1. 在Summary Report中点击![image/6-2](image\6-2.png) ，可以设置结果属性，默认的已经可以满足需求，不要勾选太多，会对负载机的IO产生影响(负载机是指发送请求的JMeter所在的机器，不是应用部署的机器)。
2. 下面是关于表格中字段的介绍
    1. Label：取样器的别名，或者说事务名
    2. \#Samples：取样器运行次数
    3. Average：请求(事务)的平均响应时间
    4. Min：请求的最小响应时间内
    5. Max：请求的最大响应时间
    6. Std.Dev.：响应时间的标准差
    7. Error%：事务错误率
    8. Throughput：吞吐量，通常说的TPS
    9. KB/sec：每秒数据包流量，单位KB
    10. Avg.Bytes：平均数据流量，单位Byte
3. 如果想保存测试结果，可以在![image/6-3](image\6-3.png) 处指定结果保存路径，如果你在测试计划中添加了多个监听器，请牢记<font color=red>测试结果只能在一个监听器中设置，如果多个监听器中设置会重复写，内容是一样的，没有必要，还影响负载机性能</font>

### 1.2 Aggregate Report
1. 以表格的形式显示取样器结果
![image\6-4](image\6-4.png)
2. 下面是关于表格中字段的介绍
    1. Label：取样器的别名，或者说事务名
    2. \#Samples：取样器运行次数
    3. Average：请求(事务)的平均响应时间
    4. Median：响应时间中间值
    5. 90% Line：90%事务响应时间范围
    6. Min：请求的最小响应时间内
    7. Max：请求的最大响应时间
    8. Error%：事务错误率
    9. Throughput：吞吐量，通常说的TPS
    10. KB/sec：数据传输量，单位KB
