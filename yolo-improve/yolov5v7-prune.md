# YOLOV5,YOLOV7剪枝项目介绍((不包含v8，但入手过这个剪枝项目，后续v8也会有对应的优惠))

##### 对于群里的剪枝相关问题,我基本都会回复,对于一些剪枝问题,我都会给出建议。  

### 首先剪枝是什么？  
模型剪枝是深度学习中的一种技术，旨在通过减少神经网络中不必要的参数和连接，来优化模型的效率和性能。模型剪枝可以分为结构剪枝和参数剪枝两种类型。  

### 为什么需要剪枝？  
剪枝可以很好地衡量模型轻量化程度与精度的关系,是替换轻量化结构完全没办法比的,比如我模型剪枝可以压缩百分之30的计算量,精度只下降了百分之1,但是你通过换模块来达到压缩百分之30的计算量,一般时间就会变长,因为大部分轻量化模块都是由时间换空间,而且精度还会下降得比较多,但是剪枝可以很好地避免这个问题.

### 目前剪枝项目包含：
1. yolov5-PAGCP
2. yolov7-PAGCP
3. yolov7-prune
4. yolov5-prune

### 其中prune中的剪枝方法包含:
1. L1 
2. Random 
3. Slim 
4. GroupSlim 
5. GroupNorm 
6. LAMP 
7. GroupSL 
8. GroupReg

### 其中prune系列还有一些细节：
1. 支持稀疏训练时候可视化BN稀疏程度和数值。
2. 稀疏训练的稀疏系数会进行线性调整，让稀疏训练后期精度更容易回升，更稳定。
3. 支持设定加速比例，模型会进行自动压缩，压缩到指定比例或者达到最大压缩次数后会自动进入finetune。

大家关心最多的一个问题就是，我的结构能不能剪之类的，目前剪枝都是基于Torch_Pruning库进行剪枝，其中PAGCP是版本比较旧的Torch_Pruning库，prune系列的都是最新Torch_Pruning库，所以PAGCP剪枝上兼容性会比prune系列的低，prune系列的可以跳过一些不能剪枝的层(某些复杂的结构可能在构建动态图的时候失败,这些就只能换结构)，这个项目会有比较多的示例和视频教程教大家如何去剪自己的结构,注意点在哪里等等。这个剪枝项目是没办法保证所有的结构都能剪，有一定的风险，是否入手请自行考虑！ 