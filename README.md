**fsd-tagging**
# Freesound tagging, DCASE 2019 task 5

A multiple neural network solution to task 5 of DCASE 2019 is proposed. Successful convolutional neural networks (CNN) architectures are used/implemented in Python with PyTorch, without pre-training, so no transfer learning was performed. Their last layers are adapted to the multi-class classification task with simultaneous events. The outputs are combined and fed to a XGBoost classifier to further improve the results.

For preprocessing the data, two different transformations and silence removal were performed. A couple of transformations are considered, based on previous quantitative analysis works on similar problems **(QUOTE TRANSFORMS COMPARISON PAPER)**. Melspectrogram and DT-CWT transforms were taken and fed parallelly to the diferent networks. Only one method for data augmentation was tried: MixUp.

Training will be done with fastai 1Cycly policy on 5-fold cross-validation sets.

## CNN
The architectures used are:
* WideResNet
* ShuffleNet v2
* NASNet Mobile
* SqueezeNet
