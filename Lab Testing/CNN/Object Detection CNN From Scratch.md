#AI #CNN

# 1. [Training an object detector from scratch in PyTorch](https://pyimagesearch.com/2021/11/01/training-an-object-detector-from-scratch-in-pytorch/)

# 2. [YOLO Paper](https://arxiv.org/pdf/1506.02640)

# 3. [Pytorch Finetune Object Detection](https://pytorch.org/tutorials/intermediate/torchvision_tutorial.html#writing-a-custom-dataset-for-pennfudan)

# 4. [Custom RCNN From Scratch](https://github.com/SharathHebbar/ML-Project-list/blob/master/computer-vision/object-detection/face_mask_detection/object-detection-using-pytorch.ipynb)

# RCNN
![[Pasted image 20250208141007.png|800]]

- Input: Ảnh
- Sử dụng Selective Search để tìm ra các vùng ảnh nổi bật rồi đưa vào CNN để classification
- Output: Bounding box (xmin, ymin, xmax, ymax) + label

# Faster RCNN
![[Pasted image 20250208141038.png|800]]

- Xử lý song song các vùng ảnh cùng lúc.
- Xử lý feature map và ROI Pooling Layer để reshape output rồi predict bounding box và label

# YOLO
![[Pasted image 20250208141153.png|800]]

- Xử lý toàn bộ ảnh trong một CNN.
- Dự đoán Bounding Box và Class trên SxS grid rồi sử dụng IOU (Intersection over Union) để ghép các vùng trùng lặp với nhau