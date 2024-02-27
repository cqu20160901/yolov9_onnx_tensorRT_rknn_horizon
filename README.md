# yolov9_onnx_tensorRT_rknn_horizon
yolov9 部署，便于移植不同平台（onnx、tensorRT、rknn、Horizon），全网首个通用部署示例。

导出onnx参考[【yolov9 瑞芯微RKNN和地平线Horizon芯片仿真测试部署，部署工程难度小、模型推理速度快】](https://blog.csdn.net/zhangqian_1/article/details/135523096)。

# 文件夹结构说明

yolov9n_onnx：onnx模型、测试图像、测试结果、测试demo脚本

yolov9n_TensorRT：TensorRT版本模型、测试图像、测试结果、测试demo脚本、onnx模型、onnx2tensorRT脚本(tensorRT-7.2.3.4)

yolov9n_rknn：rknn模型、测试（量化）图像、测试结果、onnx2rknn转换测试脚本

yolov9n_horizon：地平线模型、测试（量化）图像、测试结果、转换测试脚本、测试量化后onnx模型脚本

由于模型文件比较大，所有的模型文件放在[【onnx模型、rknn模型、trt模型、地平线模型】](https://github.com/cqu20160901/yolov9_onnx_tensorRT_rknn_horizon/releases/tag/v1.0)


# 模型训练

在 yolov9 官方代码上把“SiLU激活函数替换成了RelU”，由于是有些平台还不支持SiLU，详细训练参考yolov9官方代码。

# 测试结果

pytorch测试结果

![test](https://github.com/cqu20160901/yolov9_onnx_tensorRT_rknn_horizon/assets/22290931/5708d6a5-e8fd-4feb-9aa0-61e6267407d3)

onnx测试效果

![image](https://github.com/cqu20160901/yolov9_onnx_tensorRT_rknn_horizon/blob/main/yolov9_onnx/test_onnx_result.jpg)

说明：推理测试预处理没有考虑等比率缩放，使用训练数据不多，且迭代的次数不多，效果并不是很好，仅供测试流程用。
