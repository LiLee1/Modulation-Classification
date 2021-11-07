# 对4种调制信号识别性能进行了比对，分别是CNN、RNN、ResNet、CLDNN
利用四种模型对Mathworks Dataset和RadioML Dataset两个数据集分别进行了测试。
（1）参考了几篇文献，关于调制信号识别和如何利用matlab生成数据集；
（2）在（1）的基础上自己搭建了一个real真实数据集和一个Synthetic合成数据集。

# Modulation-Classification
Detecting the Modulation Scheme of Received Signal using AutoML Techniques.

## AutoML
- AutoML Procedure is used for Traning and Testing of Generated Data. AutoKeras are used for performing AutoML for Deep Learning Models.

## References
- [How to choose a neural network architecture? – A modulation classification example](https://ieeexplore.ieee.org/document/9221167)
- [Modulation Classification with Deep Learning](https://in.mathworks.com/help/deeplearning/ug/modulation-classification-with-deep-learning.html)
- [Convolutional Radio Modulation Recognition Networks](https://arxiv.org/pdf/1602.04105.pdf)
- [Fast Deep Learning for Automatic Modulation Classification](https://arxiv.org/pdf/1901.05850.pdf)

## Synthetic Datasets

### Data-Generation
- Data represents Constellation Received-Signal at the Receiver's End.
- Data is generated using Basic MatLab Commands.
- Modulation Schemes: QPSK, 16-QAM, 64-QAM.
- SNR Ratios = [-15,-10,-5,0,5,10,15,20,25,30]dB.
- Signal is passed through Rayleigh's Multi-Path Fading Channel and AWGN for various SNR ratios.
- For Rayleigh Multi-Path Fading, ChannelLengths = [2,3] are considered. Channel Model is changed for each and every SNR Ratio.

### Visualisations
- Visualising generated Data.

### Architectures
- AutoML StructuredClassifier, AutoML ImageClassifer for AWGN Data.
- AutoML ImageClassifier, AutoML Customised RNN, CNN form Reseach Paper.

### Training and Testing
- Dataset is split into Training and Testing sets. Both sets have Received Signals of all SNR Ratios.
- Training and Testing on Synthetic Datasets is complete.

## Real Datasets

### Data-Generation for Mathworks Dataset
- Data is generated from the code in [Modulation Classification with Deep Learning](https://in.mathworks.com/help/deeplearning/ug/modulation-classification-with-deep-learning.html).
- Modulation Schemes: QPSK, 16-QAM, 64-QAM.
- Note that Channel in this case is Rician.
- Data is generated for 2200 Frames and for SNR Ratios = [-15,-10,-5,0,5,10,15,20,25,30]dB.

### RadioML Dataset
Dataset: RML2016.10a.tar.bz2, RML2016.10b.tar.bz2 \
Source of Dataset: [https://www.deepsig.ai/datasets](https://www.deepsig.ai/datasets)
- All Modulation Schemes and SNRs of the RadioML Dataset are considered for Training and Testing.

### Architectures
- AutoML Customised CNN, AutoML Customised RNN, AutoML Customised CLDNN, CNN from Mathworks Example for Mathworks Datset.
- AutoML Customised CNN, AutoML Customised RNN, AutoML Customised CLDNN, AutoML ResNet Model for RadioML Dataset.

### Training and Testing

#### For Mathworks Dataset
- 2000 Frames of Data for each SNR of each Modulation Scheme is used for Training the Model and 200 Frames of Data for each SNR of each Modulation Scheme is used for Testing the Model.
- Training and Testing on Mathworks Dataset is complete.

#### For RadioML Dataset
- Data of each SNR of every Modulation Scheme is split such that 80% of it is used for Training and 20% of it is used for Testing.
- Training and Testing on RadioML Dataset: RML2016.10a is complete.


**Note:**
This Project is still under Development.
