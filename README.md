# S4

Target -99.4% validation accuracy.

Parameters should be exactly between 12000 to 18000.

Epochs should be exactly 19.

Implement with BN, Dropout, a Fully connected layer & GAP. 

Dropout must have 0.069 as the dropout value.

Batch size must be exactly 128.

Add random rotation to your images between -5 to +5 degrees.
Modified the code given in MNIST Base Code to achieve 99.4% validation accuracy with 17k Parameters exactly at 19th epoch.

Intuition behind the step by step approach we followed to reduce the number of parameters and to improve accuracy with less params:

At first, we reduced the number of parameters using Convolution Blocks with less number of output channels (removed 64, 128, 256 and 512 for every layer) and removed bias
Added a Transition Block (max pooling followed by 1x1).
Added a GAP layer to convert 2d to 1d
Added a FC layer after GAP i.e used 1x1 after GAP (Note: 1x1 is fully connected layer when applied on 1d data)
We used Batch Normalization after every convolution layer except the last one
Used Augmentation technique like image rotation
Added Dropout after every layer, we added dropout after we tried out all possible options. Adding drop out, helped reduced the gap between training and test loss.
We used OneCycleLR Learning Rate to tune the model
Had to increase the number of channels to achieve 99.4 accuracy exactly at 19th epoch.
Achieved a test accuracy of 99.4% from 14th epoch till 19th epoch
