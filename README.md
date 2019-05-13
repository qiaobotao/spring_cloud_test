hystrix_test
====
Hystrix提供了熔断、隔离、Fallback、cache、监控等功能，能够在一个、或多个依赖同时出现问题时保证系统依然可用。

#### Hystrix的设计原则是什么？
* 资源隔离（线程池隔离和信号量隔离）机制：限制调用分布式服务的资源使用，某一个调用的服务出现问题不会影响其它服务调用。
* 限流机制：限流机制主要是提前对各个类型的请求设置最高的QPS阈值，若高于设置的阈值则对该请求直接返回，不再调用后续资源。
* 熔断机制：当失败率达到阀值自动触发降级（如因网络故障、超时造成的失败率真高），熔断器触发的快速失败会进行快速恢复。
* 降级机制：超时降级、资源不足时（线程或信号量）降级 、运行异常降级等，降级后可以配合降级接口返回托底数据。
* 缓存支持：提供了请求缓存、请求合并实现
* 通过近实时的统计/监控/报警功能，来提高故障发现的速度
* 通过近实时的属性和配置热修改功能，来提高故障处理和恢复的速度

#####参考文章
[文章连接](https://www.jianshu.com/p/76dc45523807)
