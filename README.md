# **YOLO Evaluation on Oxford Pets Dataset**

This repository contains a detailed evaluation of various YOLO versions on the Oxford Pets Dataset. The primary objective is to compare model performance in terms of accuracy (mAP), ability to detect small objects, and computational efficiency across different versions of YOLO.

---

## **Table of Contents**

1. [Dataset](#10-dataset)
2. [YOLO Versions Compared](#20-yolo-versions-compared)
   - [Model Layers, Parameters, and GFLOPs](#21-evaluate-layers-parameters-and-gflops)
   - [10 Epochs vs 30 Epochs Evaluation](#22-evaluate-10-epochs-and-30-epochs)
3. [How to Use](#30-how-to-use)
   - [Clone the Repository](#clone-the-repository)
   - [Install Dependencies](#install-dependencies)
   - [Train and Evaluate Models](#train-and-evaluate-models)
4. [Results](#results)
5. [License](#license)

---

## **1.0 Dataset**

- **Dataset**: [Oxford Pets Dataset](https://public.roboflow.com/object-detection/oxford-pets)
- **Train/Valid/Test Split**:
  - Train: 2,576 images
  - Validation: 736 images
  - Test: 368 images

This dataset contains images of various pets (cats and dogs) with bounding box annotations for object detection tasks.

---

## **2.0 YOLO Versions Compared**

We evaluate the following versions of YOLO:

- **YOLOv8s**  
  [Link to Documentation](https://docs.ultralytics.com/vi/models/yolov8/)
- **YOLOv9s**  
  [Link to Documentation](https://docs.ultralytics.com/vi/models/yolov9/)
- **YOLOv10s**  
  [Link to Documentation](https://docs.ultralytics.com/vi/models/yolov10/)

---

## **2.1 Evaluate Layers, Parameters, and GFLOPs**

![YOLO Evaluation v8s](image/v8s.jpg)  
![YOLO Evaluation v9s](image/v9s.jpg)  
![YOLO Evaluation v10s](image/v10s.jpg)

| **Model**   | **Layers** | **Parameters**  | **GFLOPs** |
|-------------|------------|-----------------|------------|
| YOLOv8s     | 225        | 11,166,560      | 28.8       |
| YOLOv9s     | 917        | 7,288,182       | 27.4       |
| YOLOv10s    | 402        | 8,128,272       | 25.1       |

- **Model Depth**:  
  - YOLOv9s has the highest number of layers (917), enabling deep feature learning, but this also makes training more complex and prone to vanishing gradients.
  - YOLOv10s also has many layers (402), providing deep learning capability, but it’s less complex than YOLOv9s.
  - YOLOv8s has the fewest layers (225), making it easier to train, though its feature learning capability is not as deep as the other two models.
  
- **Number of Parameters**:  
  - YOLOv8s has the largest number of parameters (11,166,560), allowing it to capture more detailed features, but this also makes the model heavier and more resource-intensive.
  - YOLOv9s has the fewest parameters (7,288,182), making it more memory-efficient and lightweight.
  - YOLOv10s has a moderate number of parameters (8,128,272), providing a balance between learning capability and resource consumption.
  
- **Computational Efficiency (GFLOPs)**:  
  - YOLOv8s has the highest GFLOPs (28.8), meaning it has better processing power but also consumes more computational resources.
  - YOLOv9s and YOLOv10s have lower GFLOPs (27.4 and 25.1, respectively), optimizing for faster computation while maintaining a balance between speed and complexity.
  
- **Conclusion**:  
  - **YOLOv9s**: Suitable for tasks that require deep feature learning but comes with the challenge of complex training and moderate computational demands.
  - **YOLOv10s**: Balances depth and speed, being lighter than YOLOv9s, and ideal for applications needing efficiency in both speed and computation.
  - **YOLOv8s**: Easier to train but demands more resources, making it well-suited for complex tasks that require detailed feature learning.

---

## **2.2 Evaluate 10 Epochs and 30 Epochs**

### Results after 10 epochs:
At 10 epochs, YOLOv9s demonstrated the best performance compared to YOLOv8s and YOLOv10s.

![YOLO Evaluation Results 10 Epochs](image/10ep.jpg)

### Results after 30 epochs:
After 30 epochs, YOLOv8s improved significantly, particularly in terms of precision and recall.

![YOLO Evaluation Results 30 Epochs](image/30ep.jpg)

---

## **3.0 How to Use**

### Clone the Repository

```bash
git clone https://github.com/yourusername/YOLO_Oxford_Pets_Evaluation.git
cd YOLO_Oxford_Pets_Evaluation
