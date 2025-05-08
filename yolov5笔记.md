# 1.yolov5导出onnx命令

```
#导出onnx命令
!python export.py --weights coco/yolov5n.pt --include onnx
```

# 2.推理命令

```
#推理图片
!python detect.py --weights coco/yolov5s.pt --source data/images/bus.jpg
```

# 3.性能指标

```
train/box_loss：边界框回归的损失，数值越低越好。

train/obj_loss：物体检测的损失，数值越低越好。

train/cls_loss：分类损失，数值越低越好。

metrics/precision：模型的精确度，数值越高越好，表示模型预测的正样本中有多少是真正的正样本。

metrics/recall：模型的召回率，数值越高越好，表示所有正样本中有多少被模型正确检测出。

metrics/mAP_0.5：平均精度（AP）在 IoU=0.5 时的结果，数值越高越好，表示在0.5 IoU阈值下的总体性能。

metrics/mAP_0.5:0.95：平均精度（AP）在不同 IoU 阈值（0.5 到 0.95）下的结果，数值越高越好，表示不同阈值下的总体性能。

val/box_loss：验证集上的边界框回归损失，数值越低越好。

val/obj_loss：验证集上的物体检测损失，数值越低越好。

val/cls_loss：验证集上的分类损失，数值越低越好。

x/lr0：学习率，表示训练过程中调整模型权重的步长，通常开始时较大，逐渐减小。

x/lr1：学习率，通常用于细调特定层的权重。

x/lr2：学习率，通常用于细调特定层的权重。

一般来说，模型准确度高时，你会看到：

低的 train/box_loss，train/obj_loss 和 train/cls_loss。

高的 metrics/precision 和 metrics/recall。

高的 metrics/mAP_0.5 和 metrics/mAP_0.5:0.95。

这些指标的具体值会因任务和数据集而异。你可以参考这些指标来调整模型参数和改进模型性能。希望这些解释对你有帮助，如果你还有其他问题，请随时告诉我！
```

# 4.开启虚拟环境

[pip安装解决报错：WARNING: Running pip as the ‘root‘ user can result in broken permissions and conflicting_warning: running pip as the 'root' user can result-CSDN博客](https://blog.csdn.net/m0_58782029/article/details/129049587)

# 5.配置数据集文件,用与训练

![1](img\2.png)

# 6.训练命令

python train.py --weights yolov5n.pt

# 7.parse模块

 

![1](img\3.png)

```
在控制面版里面输入 name_or_flags参数就行
列子:
python train.py  --weight  带上模型
python train.py  --epochs  训练轮数
```

