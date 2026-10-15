# learn-yolov8
Learning and practicing YOLOv8 object detection, including dataset training, inference and visualization.
前置环境安装（省略）
（base）激活环境->（yolov8）conda activate yolov8

#demo_predict.py#


1.demo测试1：摄像头识别物体
from ultralytics import YOLO
yolo =YOLO("./yolov8n.pt",task="detect")
result=yolo(source=0)

注：Ctrl+C退出


2.demo测试2：识别图片物体
from ultralytics import YOLO
yolo = YOLO("./yolov8n.pt", task="detect")
result = yolo(source=r"D:\Desktop\ultralytics-main\R-C.jpg", show=True, save=True)


这里还可以加cof参数，cof越低圈出来的物体越多
YOLOv8 原生逻辑：只要你写 `save=True`，**它会自动创建 `runs/detect/predict` 文件夹**，不需要你手动指定保存路径，这是 ultralytics 库内置的默认行为。

3.数据集标注工具labelimg进行视频手动逐帧标注
首先激活环境
在vscode里面安装labelimg：pip install labelimg————输入labelimg->打开labelimg
打开文件夹进行标注（快捷键W开始标注，D下一张，A上一张）

4.make sence在线数据集标注工具
加载本地预训练好的模型（把训练好的 pt 模型，转成能放到 C++、移动端、嵌入式上面部署的模型文件。）
(yolov5) C:\Users\13716\Desktop\yolov5-master>python export.py --weights runs/train/exp2/weights/best.pt

5.roboflow公开数据集






