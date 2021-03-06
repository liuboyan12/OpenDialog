# OpenDialog

~~我们现在拥有了测试接口了，搜索微信公众号 `OpenDialog` 可以使用~~

OpenDialog提供一系列transformer-based的**中文**开放域对话模型（闲聊对话），网罗已有的资源并持续不断的补充对应的中文对话系统的数据集，意图构建一个强大的开源的中文闲聊对话平台。


## OpenDialog的优势

1. 持续追踪目前开放域对话系统的研究前沿，提供大量基于transformer的可用对话系统
    * Bert检索式对话系统
    * GPT2生成式对话系统
2. 搜集整理目前可以获得的中文对话数据

## 使用教程

### 1. 项目结构和文件简述

OpenDialog核心文件和目录:

* `data`: 数据集，配置文件，词表，词向量，数据集处理脚本
* `models`: 对话模型
* `metrics`: 评价指标
* `multiview`: 多角度重排模型，针对获得对话候选回复进行重排序
* `ckpt`: 存放训练模型
* `rest`: 存放tensorboard日志和test阶段生成的结果文件
* `utils`: 存放工具函数
* `dataloader.py`: 数据集加载脚本
* `main.py`: 主运行文件
* `header.py`: 需要导入的package
* `eval.py`: 调用`metrics`中的评价指标的评估脚本，测试`rest`中生成文件的结果
* `run.sh`: 运行批处理脚本
* `run_flask.sh`: 调用模型，启动服务

### 2. 准备环境

1. 系统环境:
    * Linux/Ubuntu-16.04+
    * Python 3.6+
    * GPU (default 1080 Ti)

2. 根据`requirements.txt`安装python依赖库

```bash
pip install -r requirements.txt
```

3. 安装 `ElasticSearch`
    基于检索的对话系统需要首先使用`elasticsearch`进行粗筛

4. 安装 `mongodb`
    启动服务之后，会使用`mongodb`存储会话历史和必要的数据


### 3. 准备数据

百度云链接: https://pan.baidu.com/s/1qwUj6xevOIPr_7v7apwA0A; 提取码: 3erj

将对应的数据文件存放在`data`目录下对应的子目录中，词向量文件`chinese_w2v.txt`和`english_w2v.bin`存放在`data`下即可。数据细节和预处理数据详见`data/README.md`。

### 5. 训练模型

### 6. 测试模型

**并不是所有的模型都有测试阶段**

### 7. 启动flask服务
