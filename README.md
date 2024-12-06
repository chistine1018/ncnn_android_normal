﻿# ncnn_android_normal

 Android方面
 1. CMakeLists.txt 注意opencv 位置以及版本
 2. CMakeLists.txt 注意ncnn 位置以及版本
 3. CMakeLists.txt 注意so name
 4. jni folder 放入cpp, h, CMakeLists.txt, ncnn lib, opencv lib
 5. yolov8ncnn.cpp 注意JNI function name 需要跟android的Yolov8Ncnn.java packagename一致
 6. yolo.cpp Extractor 注意輸入的參數名稱
 7. yolo.cpp class_names 注意改成自己的類別
 8. yolo.cpp num_class 注意改成自己的類別數量


 模型方面
 1. pt 轉 onnx ，windows需要改設定(可以用anaconda pt2onnx, 另外normal, seg需要改動的地方也不一樣,最好分兩個env)
    change c2f split to slice  
![image](https://github.com/user-attachments/assets/f3ae92ea-94e2-4ecb-a1a3-485cc781c4b8)  
    for Detection model change class Detect output
    ![image](https://github.com/user-attachments/assets/23ac6fc8-2fcb-483b-a908-e66a520ca2f3)  

    for Segmentation model change class Detect output and Segment output
    ![image](https://github.com/user-attachments/assets/a4c04aaf-2215-4896-bcd1-c4b898cb3e14)  
    ![image](https://github.com/user-attachments/assets/0e7a5ef3-f14d-4550-b894-a0de392e3762)  


 2. 再透過onnx2ncnn 轉換(這邊可以用windows or ubuntu , ubuntu比較簡單)

![image](https://github.com/user-attachments/assets/5ec7d8e0-e690-438a-904d-6dc6b336b30f)
