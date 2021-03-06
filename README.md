# 使用 gluon 实现狗品种分类

本项目是为了熟悉 gluon 操作的练手作，可以在测试集上获得0.28228的分数。

环境参考：

* mxnet 0.12.1
* numpy 1.13.3
* tqdm 4.11.2
* pandas 0.20.3
* sklearn 0.19.0

# 思路

复现步骤分为以下几步：

* 下载并解压数据集：[https://www.kaggle.com/c/dog-breed-identification/data](https://www.kaggle.com/c/dog-breed-identification/data)
* 运行 [preprocessing.ipynb](preprocessing.ipynb)，构建 for_train 和 for_test 的文件夹结构，为 [ImageFolderDataset](https://mxnet.incubator.apache.org/api/python/gluon/data.html?highlight=imagefolderdataset#mxnet.gluon.data.vision.ImageFolderDataset) 做准备
* 运行 [get_features.ipynb](get_features.ipynb)，导出 resnet152_v1, densenet161 和 inception_v3 等模型输出的特征，参考[model_zoo](https://mxnet.incubator.apache.org/versions/master/api/python/gluon/model_zoo.html)
* 运行 [model.ipynb](model.ipynb)，拼接特征，训练一个2层的神经网络，然后在测试集上进行预测
