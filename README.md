# 肺炎X光影像智能检测系统

基于深度学习的医学影像分析系统，使用迁移学习技术自动检测胸部X光片中的肺炎症状。

## 项目特点

- 🏥 **专业医疗辅助**: 为医生提供快速肺炎筛查工具
- 🤖 **先进AI技术**: 基于VGG16的迁移学习模型
- 📊 **高精度检测**: 测试准确率85%，肺炎检测精确度96%
- 🌐 **友好界面**: 基于Gradio的Web交互界面
- ⚖️ **数据平衡**: 采用类别权重处理数据不平衡问题

## 技术架构

### 模型架构
- 基础模型: VGG16 (预训练权重)
- 自定义层: GlobalAveragePooling2D + Dense(128) + Dropout(0.5)
- 输出层: Sigmoid (二分类)

### 数据处理
- 图像尺寸: 224×224像素
- 数据增强: 旋转、平移、缩放、翻转
- 归一化: 像素值缩放到[0,1]范围

## 数据集

使用公开胸部X光数据集:
https://www.kaggle.com/datasets/nih-chest-xrays/data/
- 训练集: 5,216张图像
  - 正常: 1,341张
  - 肺炎: 3,875张
- 测试集: 624张图像

## 安装与运行

### 环境要求
```bash
pip install tensorflow opencv-python pillow numpy pandas matplotlib seaborn scikit-learn jupyter gradio
```

### 训练模型
```python
python train.py
```

### 启动Web界面
```python
python app.py
```

## 使用方法

1. 启动Gradio界面
2. 上传胸部X光影像
3. 系统自动分析并返回结果:
   - "正常" 或 "肺炎"
   - 置信度百分比

## 性能指标

| 指标 | 数值 |
|------|------|
| 测试准确率 | 85% |
| 肺炎检测精确度 | 96% |
| 正常病例召回率 | 94% |

## 项目结构

```
pneumonia-detection/
├── chest_xray/          # 数据集目录
├── best_pneumonia_model.h5  # 训练好的模型
├── pneumonia_detection.ipynb  # 完整代码笔记本
├── train.py            # 训练脚本
├── app.py             # Web应用脚本
└── README.md          # 项目说明
```

## 注意事项

- 本系统为辅助诊断工具，不能替代专业医生诊断
- 建议在医生指导下使用检测结果
- 模型性能可能受图像质量和拍摄条件影响

## 未来改进

- [ ] 支持更多肺部疾病检测
- [ ] 提高模型泛化能力
- [ ] 优化移动端部署
- [ ] 增加批量处理功能

## 许可

本项目仅供学习使用。Learning Only
