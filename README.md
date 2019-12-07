# ObserverDDS
网络订阅发布模型  
本程序采用组播方式寻找节点地址  
通过UDP，TCP发送数据  
TCP已经避免粘包；UDP采用最大努力投递  
NetPublisher为发布类，提供类单例；NetSubscriber为订阅类，提供类单例  

2019-12  
  1.修改线程使用，将主要流程Task修该Thread，防止线程占用无法完成主要工作  
  2.修改socket参数  
2019-12  
  1.修改注册回复，注册信息立即触发地址刷新，而不是触发轮训刷新  
  
  2019-12  
  1.修复2节点不能及时注册的问题  
  2.增加跨网段桥接问题，如果组播不能跨网段，可以设置点对点替代，找一个桥接节点  
  3.增加UDP接收缓存，固定保持大小不变，默认80M