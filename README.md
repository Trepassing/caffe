# 环境配置

    ubuntu：18.04

    cuda：10.0

    cudnn：7.6.5

    caffe: 1.0

    OpenCV：3.4.2

    Anaconda3：5.2.0

    caffe安装

    git clone https://github.com/Trepassing/caffe.git

    cd caffe

    命令行输入如下内容：

    export CPLUS_INCLUDE_PATH=/home/你的用户名/anaconda3/include/python3.6m

    make all -j8

    make pycaffe -j8

    vim ~/.bashrc

    export PYTHONPATH=/home/你的用户名/caffe/python:$PYTHONPATH

    source ~/.bashrc

# caffe模型推理

    定位到ycaffe目录下

    cd tools

    vim caffe_yolov5s.cpp

    设置如下参数：

    INPUT_W（模型输入宽度）

    INPUT_H（模型输入高度）

    NUM_CLASS（模型有多少个类别，例如我训练的模型是安全帽检测，只有1类，所以设置为1，不需要加背景类）

    NMS_THRESH（做非极大值抑制的阈值）

    CONF_THRESH（类别置信度）

    prototxt_path（caffe模型的prototxt路径）

    caffemodel_path（caffe模型的caffemodel路径）

    pic_path（预测图片的路径）

    定位到yolov5_caffe目录下

    make -j8

    cd build

    ./tools/caffe_yolov5s 输出平均推理时间，以及保存预测图片到当前目录下，至此，部署完成！
