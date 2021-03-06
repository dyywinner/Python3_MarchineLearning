tensorflow-gpu: 1.4.0<br>
tensorflow: 1.12.0<br>
cuda-8.0 & cuddnV6.0<br>

tensorflow属于计算密集型框架:
- 1  图graph
- 2  会话session：运算程序的图；分配资源计算；掌握资源
- 3  tensor: 张量
- 4  变量：特殊的张量，存储永久化，默认被训练
- 5  模型保存与加载
- 6  自定义命令行参数

operation: 运算操作节点，所有操作是一个op(只要是tensorflow定义的api都是)<br>
tensor: 就是指代的数据<br>

tensorflow由前段和后端：
- 前段： 定义程序图结构
- 后端： 运算图结构

图：图默已经注册，一组表示tf.operation计算单位的对象和tf.Tensor表示操作之间流动的数据单元的对象.<br>
获取调用：
- tf.get_default_graph()
- op, sess, tensor的graph属性
- 图可以创建，tf.Graph()
- 图和会话，可以用*上下文管理器*指定图去运行;run只能tensorflow张量，不能run python的Int

张量:
- 类型化N维数组tf.Tensor
- 阶
- Tensor("Add_11:0", shape=(), dtype=float32) op名字，形状，数据类型
- 形状的改变很常用，动态性状与静态性状
- 创建01张量，更多的是创建随机值张量(正态分布)
- tensor类型变换

可视化学习Tensorboard:
- 数据序列化-events文件
- 启动TensorBoard
- 节点符号

计算节点保存与加载:
- tf.train.Saver()
- saver.load()

IO流队列：
- tf.FIFOQueue()
- tf.train.QueueRunner() 队列管理器
- tf.train.Coordinator() 线程协调器
文件读取队列：
- 1 构造文件队列 tf.train.string_input_producer()
- 2 读取队列内容 tf.TextLineReader/tf.FixedLengthRecordReader/tf.TFRecordReader 
- 3 读取队列内容中一个样本的内容 tf.decode_csv()/tf.decode_raw()
- 4 批处理
图像读取：
- [长，宽，通道]
- 缩小图片 tf.image.resize_images()

神经网络APImodule:
- 1 tf.nn: 卷积conv, 池化pooling, 归一化, loss, 分类, embeding, RNN, evaluation
- 2 tf.layers: 高层神经网络, 主要和卷积相关, 对tf.nn进一步封装
- 3 tf.contrib: tf.contrib.layers 提供计算图中的网络层，正则化，摘要操作，是构建计算图的高级操作
