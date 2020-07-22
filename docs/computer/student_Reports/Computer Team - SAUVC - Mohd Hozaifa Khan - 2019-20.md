# Report on Precautionary System during  COVID-19 for ZHECT

> _under AUV_

---

Submitted by: **Mohd Hozaifa Khan**

Mail: [mhozaifakhan98@gmail.com](mailto:mhozaifakhan98@gmail.com)

Work during: _15 May - 09 June 2020_  

Under the Guidance of

**Dr. Saleem Anwar Khan**

_Associate Professor, Mechanical Engg., ZHCET_

_Teacher In-charge_, **_AUV Club_**

Submitted on: *20th July 2020*

---

## Summary/Abstract

Considering the rapid growth in infection rates and current situation of Examinations there arises a need to have a precautionary system setup at colleges to control further infections. We thought of building a system to utilize Body Temperature along with Mask detection to filter out possible Corona infected people and henceforth reduce chances of further infections. Special care was given to Adversarial cases which might arise and hamper the system.

Note: _Only Mask detection system was developed. So this report only covers that part._

---

## Content

1. [Introduction](#introduction)
2. [Technologies Used](#technologies-used)
3. [Methodology](#methodology)
4. [Problems faced](#problems-faced)
5. [Conclusion](#conclusion)
6. [Future Development](#future-developement)

---

## Introduction

The year 2020 has been pretty harsh and evidently threw a lot thorns in our ways. Overcoming these trails and tribulations is also up to us. And, the hardest trial has been defeating COVID-19 pandemic which has already engulfed almost a lakh people now.

Having an automatic system to filter out possible Corona infected people can act as a first line of prevention.
The system will detect body temperature of person entering the main gate as well as verify whether the person is wearing face mask (also properly) and then take a decision to allow or refer to concerned authorities.

---

## Technologies Used

**Language**: Python 3.7

**Object Detection System** : **YOLO** *version 4*

**Hardware**:

1. Logitech Camera *for Mask detection*
2. Board: Raspberry Pi 3
3. Temperature sensor: *Not used yet*

*incomplete list*

---

## Methodology

Detecting face mask can be simplified as a classification task of wearing a mask or not wearing a mask and localizing that object. So, we used transfer learning to train a pre-trained Object Detection model and fine-tune it for our task.

We used YOLO framework for Object Detection. YOLO being one of many Single Shot object detection techniques proves to be a good option giving a considerable FPS and accuracy in practical applications.
We especially trained it on few Adversarial Cases so as to equip our system to detect possible fraudulent attempts and fool the system. These case can be covering your faces or using techniques to simply cover nose and mouth temporarily.

### [YOLO](https://pjreddie.com/darknet/yolo/)

It stands for You Only Look Once.
Based on Darknet Framework which is a C++ based Deep Learning framework. Also available in other frameworks.
Written by Joseph Redmon and Ali Farhadi.

#### Concept of YOLO in brief

Unlike prior detection systems which were repurposed classifiers or localizers to perform detection YOLO applies a single neural network to the full image. This network divides the image into regions and predicts bounding boxes and probabilities for each region. These bounding boxes are weighted by the predicted probabilities.

### Dataset

We used face mask dataset available on Kaggle. It was available in YOLO format and so there no extra effort involved in conversion. [Kaggle Competition Link]()

| Type | Count |
| :--  | --:   |
| faces with mask | |
| faces without mask| |
| Total | |

Also, I compiled a list of Face dataset with diverse set of cases and so it can help system detect type of mask, handkerchief on face, etc.

[Link to Dataset Folder]() 

---

## Results and Performance

No practical testing was done. And, we only tested using webcam.  

---

## Conclusion

PASS

---

## Further Development

The actual testing of any system is only possible in actual scenario. There is a possibility of few problems:

* Adversarial Cases
* Lower FPS
* Robustness

For adversarial cases we can have more diverse dataset with various cases that we might encounter. I have one such dataset which can help system detect type of mask, handkerchief on face, etc. The model can trained on such dataset to make it more robust and immune to adversarial attacks.

Other object detection techniques can be utilized and practically tested for better performance and accuracy.  
Few Options are:

* [EfficientDet](http://ai.googleblog.com/2020/04/efficientdet-towards-scalable-and.html) - Scalable and Efficient Object Detection by Google.
* SSD with MobileNetv3 or EfficientNetB4 - proven to work very well on Raspberry Pi.
* YOLOv5 - released few days ago.

## Resources

* YOLO Resources:
  - [Understanding YOLO](https://hackernoon.com/understanding-yolo-f5a74bbc7967)
  - [Train on Custom Dataset](https://blog.roboflow.ai/training-yolov4-on-a-custom-dataset/)
  - [What's new in YOLOv4?](https://towardsdatascience.com/whats-new-in-yolov4-323364bb3ad3)
  - [Another good Explanation](https://towardsdatascience.com/yolo-you-only-look-once-real-time-object-detection-explained-492dc9230006)