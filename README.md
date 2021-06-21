# Sinhala Optical Character Recognition (OCR) using Neural Network

#### Main Library:
- Tensorflow 1.14
- OpenCV 4.5.2

#### Dataset
All images in the Dataset are extraxted from Sinhala Font
- BhashitaComplex
- Iskoola Potha
- LK-LUG
- Nirmala UI
- Noto Sans Sinhala
- Noto Sans Sinhala Bold

![](https://github.com/chamara96/sinhala-letters-OCR/blob/main/dataset/train/bhashita_complex_0.png)
![](https://github.com/chamara96/sinhala-letters-OCR/blob/main/dataset/train/iskoola_pota_0.png)
![](https://github.com/chamara96/sinhala-letters-OCR/blob/main/dataset/train/lklug_0.png)
![](https://github.com/chamara96/sinhala-letters-OCR/blob/main/dataset/train/nirmala_ui_0.png)
![](https://github.com/chamara96/sinhala-letters-OCR/blob/main/dataset/train/noto_sans_sinhala_0.png)
![](https://github.com/chamara96/sinhala-letters-OCR/blob/main/dataset/train/noto_sans_sinhala_bold_0.png)

```python
classes = ['ක', 'ඛ', 'ග', 'ඝ', 'ඟ', 'ච', 'ඡ', 'ජ', 'ට', 'ඩ', 'න', 'ණ', 'ත', 'ථ', 'ද',
           'ධ', 'ප', 'ඵ', 'බ', 'භ', 'ම', 'ඹ', 'ය', 'ර', 'ල', 'ව', 'ශ', 'ෂ', 'ස', 'හ', 'ළ', 'ෆ']
```

There are  32 classes (letters). For the Training dataset, each class has 6 examples. So Total number of examples in the training dataset is 6x32 = 192.
For the Testing dataset, each class has 1 examples. So Total number of examples in the testing dataset is 1x32 = 32.

A data example has 70 rows and 70 columns, then it is resized into 28x28.

#### Training
Tensorflow default ANN architecture.
`<Tensorflow v1>` : <https://github.com/tensorflow/docs/tree/master/site/en/r1/tutorials>

```
Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
flatten (Flatten)            (None, 784)               0         
_________________________________________________________________
dense (Dense)                (None, 512)               401920    
_________________________________________________________________
dropout (Dropout)            (None, 512)               0         
_________________________________________________________________
dense_1 (Dense)              (None, 32)                16416     
=================================================================
Total params: 418,336
Trainable params: 418,336
Non-trainable params: 0
_________________________________________________________________
```

| **Accuracy** : 96.88% |
<br>
| **Loss** : 0.9942  |

#### Results

![](https://github.com/chamara96/sinhala-letters-OCR/blob/main/image.jpg)
![](https://github.com/chamara96/sinhala-letters-OCR/blob/main/result.png)

Limitation:
Each letter should have enough margin.
In the Contour detection, character height and width should between 32 - 320 pixels.
Further: Increase the dataset with more characters
