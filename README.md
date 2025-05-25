# NNDL-Midterm

## 项目结构

```
|----mask_rcnn
|--------20250523_005102 
|------------vis_data # Tensor Board可视化数据
|------------20250523_005102.log # 模型训练日志
|--------mask_rcnn_r50_fpn_1x_voc0712.py # 训练启动脚本
|----sparse_rcnn
|--------20250523_110151
|------------vis_data # Tensor Board可视化数据
|------------20250523_110151.log # 模型训练日志
|--------sparse-rcnn_r50_fpn_1x_voc0712.py # 训练启动脚本
|----part2.ipynb # 手动查看模型效果
```

## 训练

根据自己的需求, 在mmdection项目文件夹中做以下修改:

- `configs/_base_/default_runtime.py`中添加Tensor Board可视化后端.
- `configs/_base_/models/mask-rcnn_r50_fpn.py`中修改Mask R-CNN的模型结构.
- `configs/_base_/datasets/voc0712.py` 中修改训练和验证的批次大小.

然后进行训练. 

启动Mask R-CNN训练:

```
python tools/train.py configs/mask_rcnn/mask_rcnn_r50_fpn_1x_voc0712.py --work_dir ./mymodels/mask_rcnn
```

其中`mask_rcnn_r50_fpn_1x_voc0712.py`可以在本项目中`mask_rcnn`文件夹中找到. `mymodels`目录将保存训练日志和模型权重.

启动Sparse R-CNN训练:

```
python tools/train.py configs/sparse_rcnn/sparse-rcnn_r50_fpn_1x_voc0712.py --work_dir ./mymodels/spasrse_rcnn
```

## 测试

模型在测试集中的指标可以通过Tensor Board查看.

如果想手动检查效果, 请参考`part2.ipynb`.
