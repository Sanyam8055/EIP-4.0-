## Assignment 4a
Project saved through online tool</br>
[Export CSV](https://github.com/Sanyam8055/EIP-4.0-/blob/master/Assignment4/Assignment4a/via_export_csv.csv)</br>
## Assignment 4b
**Problem Statement**</br>
To create ResNet18 Network </br>
Train on CIFAR10 data.</br>  
Run for 50 Epochs and cross 88% Validation Accuracy</br>
Show GradCam results for 10 images.</br> 
### I got an Accuracy of 88.06% within 50 epochs.</br>
## Model
__________________________________________________________________________________________________
    Layer (type)                    Output Shape         Param #     Connected to                     
    input_1 (InputLayer)            (None, 32, 32, 3)    0                                            
    conv2d_1 (Conv2D)               (None, 32, 32, 16)   448         input_1[0][0]                    
    batch_normalization_1 (BatchNor (None, 32, 32, 16)   64          conv2d_1[0][0]                   
    activation_1 (Activation)       (None, 32, 32, 16)   0           batch_normalization_1[0][0]      
__________________________________________________________________________________________________
    conv2d_2 (Conv2D)               (None, 32, 32, 16)   2320        activation_1[0][0]               
__________________________________________________________________________________________________
    batch_normalization_2 (BatchNor (None, 32, 32, 16)   64          conv2d_2[0][0]                   
__________________________________________________________________________________________________
    activation_2 (Activation)       (None, 32, 32, 16)   0           batch_normalization_2[0][0]      
__________________________________________________________________________________________________
    conv2d_3 (Conv2D)               (None, 32, 32, 16)   2320        activation_2[0][0]               
__________________________________________________________________________________________________
    batch_normalization_3 (BatchNor (None, 32, 32, 16)   64          conv2d_3[0][0]                   
__________________________________________________________________________________________________
    add_1 (Add)                     (None, 32, 32, 16)   0           activation_1[0][0]               
                                                                 batch_normalization_3[0][0]      
__________________________________________________________________________________________________
    activation_3 (Activation)       (None, 32, 32, 16)   0           add_1[0][0]                      
__________________________________________________________________________________________________
    conv2d_4 (Conv2D)               (None, 32, 32, 16)   2320        activation_3[0][0]               
__________________________________________________________________________________________________
    batch_normalization_4 (BatchNor (None, 32, 32, 16)   64          conv2d_4[0][0]                   
__________________________________________________________________________________________________
    activation_4 (Activation)       (None, 32, 32, 16)   0           batch_normalization_4[0][0]      
__________________________________________________________________________________________________
    conv2d_5 (Conv2D)               (None, 32, 32, 16)   2320        activation_4[0][0]               
__________________________________________________________________________________________________
    batch_normalization_5 (BatchNor (None, 32, 32, 16)   64          conv2d_5[0][0]             
    add_2 (Add)                     (None, 32, 32, 16)   0           activation_3[0][0]               
                                                                     batch_normalization_5[0][0]      
__________________________________________________________________________________________________
    activation_5 (Activation)       (None, 32, 32, 16)   0           add_2[0][0]                      
__________________________________________________________________________________________________
    conv2d_6 (Conv2D)               (None, 32, 32, 16)   2320        activation_5[0][0]               
__________________________________________________________________________________________________
    batch_normalization_6 (BatchNor (None, 32, 32, 16)   64          conv2d_6[0][0]                   
__________________________________________________________________________________________________
    activation_6 (Activation)       (None, 32, 32, 16)   0           batch_normalization_6[0][0]      
__________________________________________________________________________________________________
    conv2d_7 (Conv2D)               (None, 32, 32, 16)   2320        activation_6[0][0]               
__________________________________________________________________________________________________
    batch_normalization_7 (BatchNor (None, 32, 32, 16)   64          conv2d_7[0][0]                   
__________________________________________________________________________________________________
    add_3 (Add)                     (None, 32, 32, 16)   0           activation_5[0][0]               
                                                                    batch_normalization_7[0][0]      
__________________________________________________________________________________________________
    activation_7 (Activation)       (None, 32, 32, 16)   0           add_3[0][0]                      
__________________________________________________________________________________________________
    conv2d_8 (Conv2D)               (None, 16, 16, 32)   4640        activation_7[0][0]               
__________________________________________________________________________________________________
    batch_normalization_8 (BatchNor (None, 16, 16, 32)   128         conv2d_8[0][0]                   
__________________________________________________________________________________________________
    activation_8 (Activation)       (None, 16, 16, 32)   0           batch_normalization_8[0][0]      
__________________________________________________________________________________________________
    conv2d_9 (Conv2D)               (None, 16, 16, 32)   9248        activation_8[0][0]               
__________________________________________________________________________________________________
    conv2d_10 (Conv2D)              (None, 16, 16, 32)   544         activation_7[0][0]               
__________________________________________________________________________________________________
    batch_normalization_9 (BatchNor (None, 16, 16, 32)   128         conv2d_9[0][0]                   
__________________________________________________________________________________________________
    add_4 (Add)                     (None, 16, 16, 32)   0           conv2d_10[0][0]                  
                                                                    batch_normalization_9[0][0]      
__________________________________________________________________________________________________
    activation_9 (Activation)       (None, 16, 16, 32)   0           add_4[0][0]                      
__________________________________________________________________________________________________
    conv2d_11 (Conv2D)              (None, 16, 16, 32)   9248        activation_9[0][0]               
__________________________________________________________________________________________________
    batch_normalization_10 (BatchNo (None, 16, 16, 32)   128         conv2d_11[0][0]                  
__________________________________________________________________________________________________
    activation_10 (Activation)      (None, 16, 16, 32)   0           batch_normalization_10[0][0]     
__________________________________________________________________________________________________
    conv2d_12 (Conv2D)              (None, 16, 16, 32)   9248        activation_10[0][0]              
__________________________________________________________________________________________________
    batch_normalization_11 (BatchNo (None, 16, 16, 32)   128         conv2d_12[0][0]                  
__________________________________________________________________________________________________
    add_5 (Add)                     (None, 16, 16, 32)   0           activation_9[0][0]               
                                                                    batch_normalization_11[0][0]     
__________________________________________________________________________________________________
    activation_11 (Activation)      (None, 16, 16, 32)   0           add_5[0][0]                      
__________________________________________________________________________________________________
    conv2d_13 (Conv2D)              (None, 16, 16, 32)   9248        activation_11[0][0]              
__________________________________________________________________________________________________
    batch_normalization_12 (BatchNo (None, 16, 16, 32)   128         conv2d_13[0][0]                  
__________________________________________________________________________________________________
    activation_12 (Activation)      (None, 16, 16, 32)   0           batch_normalization_12[0][0]     
__________________________________________________________________________________________________
    conv2d_14 (Conv2D)              (None, 16, 16, 32)   9248        activation_12[0][0]              
__________________________________________________________________________________________________
    batch_normalization_13 (BatchNo (None, 16, 16, 32)   128         conv2d_14[0][0]                  
__________________________________________________________________________________________________
    add_6 (Add)                     (None, 16, 16, 32)   0           activation_11[0][0]              
                                                                     batch_normalization_13[0][0]     
__________________________________________________________________________________________________
    activation_13 (Activation)      (None, 16, 16, 32)   0           add_6[0][0]                      
__________________________________________________________________________________________________
    conv2d_15 (Conv2D)              (None, 8, 8, 64)     18496       activation_13[0][0]              
__________________________________________________________________________________________________
    batch_normalization_14 (BatchNo (None, 8, 8, 64)     256         conv2d_15[0][0]                  
__________________________________________________________________________________________________
    activation_14 (Activation)      (None, 8, 8, 64)     0           batch_normalization_14[0][0]     
__________________________________________________________________________________________________
    conv2d_16 (Conv2D)              (None, 8, 8, 64)     36928       activation_14[0][0]              
__________________________________________________________________________________________________
    conv2d_17 (Conv2D)              (None, 8, 8, 64)     2112        activation_13[0][0]              
__________________________________________________________________________________________________
    batch_normalization_15 (BatchNo (None, 8, 8, 64)     256         conv2d_16[0][0]                  
__________________________________________________________________________________________________
    add_7 (Add)                     (None, 8, 8, 64)     0           conv2d_17[0][0]                  
                                                                    batch_normalization_15[0][0]     
__________________________________________________________________________________________________
    activation_15 (Activation)      (None, 8, 8, 64)     0           add_7[0][0]                      
__________________________________________________________________________________________________
    conv2d_18 (Conv2D)              (None, 8, 8, 64)     36928       activation_15[0][0]              
__________________________________________________________________________________________________
    batch_normalization_16 (BatchNo (None, 8, 8, 64)     256         conv2d_18[0][0]                  
__________________________________________________________________________________________________
    activation_16 (Activation)      (None, 8, 8, 64)     0           batch_normalization_16[0][0]     
__________________________________________________________________________________________________
    conv2d_19 (Conv2D)              (None, 8, 8, 64)     36928       activation_16[0][0]              
__________________________________________________________________________________________________
    batch_normalization_17 (BatchNo (None, 8, 8, 64)     256         conv2d_19[0][0]                  
__________________________________________________________________________________________________
    add_8 (Add)                     (None, 8, 8, 64)     0           activation_15[0][0]              
                                                                    batch_normalization_17[0][0]     
__________________________________________________________________________________________________
    activation_17 (Activation)      (None, 8, 8, 64)     0           add_8[0][0]                      
__________________________________________________________________________________________________
    conv2d_20 (Conv2D)              (None, 8, 8, 64)     36928       activation_17[0][0]              
__________________________________________________________________________________________________
    batch_normalization_18 (BatchNo (None, 8, 8, 64)     256         conv2d_20[0][0]                  
__________________________________________________________________________________________________
    activation_18 (Activation)      (None, 8, 8, 64)     0           batch_normalization_18[0][0]     
__________________________________________________________________________________________________
    conv2d_21 (Conv2D)              (None, 8, 8, 64)     36928       activation_18[0][0]              
__________________________________________________________________________________________________
    batch_normalization_19 (BatchNo (None, 8, 8, 64)     256         conv2d_21[0][0]                  
__________________________________________________________________________________________________
    add_9 (Add)                     (None, 8, 8, 64)     0           activation_17[0][0]              
                                                                    batch_normalization_19[0][0]     
__________________________________________________________________________________________________
    activation_19 (Activation)      (None, 8, 8, 64)     0           add_9[0][0]                      
__________________________________________________________________________________________________
    average_pooling2d_1 (AveragePoo (None, 1, 1, 64)     0           activation_19[0][0]              
__________________________________________________________________________________________________
    flatten_1 (Flatten)             (None, 64)           0           average_pooling2d_1[0][0]        
__________________________________________________________________________________________________
    dense_1 (Dense)                 (None, 10)           650         flatten_1[0][0]                  


## Log
Using real-time data augmentation.
Epoch 1/50
Learning rate:  0.003
 - 56s - loss: 1.6323 - acc: 0.4583 - val_loss: 2.0657 - val_acc: 0.4555

Epoch 00001: val_acc improved from -inf to 0.45550, saving model to /content/saved_models/cifar10_ResNet20v1_model.001.h5
Epoch 2/50
Learning rate:  0.003
 - 47s - loss: 1.2492 - acc: 0.6251 - val_loss: 1.3825 - val_acc: 0.6169

Epoch 00002: val_acc improved from 0.45550 to 0.61690, saving model to /content/saved_models/cifar10_ResNet20v1_model.002.h5
Epoch 3/50
Learning rate:  0.003
 - 46s - loss: 1.1137 - acc: 0.6802 - val_loss: 1.3814 - val_acc: 0.5894

Epoch 00003: val_acc did not improve from 0.61690
Epoch 4/50
Learning rate:  0.003
 - 47s - loss: 1.0411 - acc: 0.7140 - val_loss: 1.3231 - val_acc: 0.6682

Epoch 00004: val_acc improved from 0.61690 to 0.66820, saving model to /content/saved_models/cifar10_ResNet20v1_model.004.h5
Epoch 5/50
Learning rate:  0.003
 - 46s - loss: 0.9888 - acc: 0.7325 - val_loss: 1.0839 - val_acc: 0.7132

Epoch 00005: val_acc improved from 0.66820 to 0.71320, saving model to /content/saved_models/cifar10_ResNet20v1_model.005.h5
Epoch 6/50
Learning rate:  0.003
 - 46s - loss: 0.9553 - acc: 0.7496 - val_loss: 1.3600 - val_acc: 0.6698

Epoch 00006: val_acc did not improve from 0.71320
Epoch 7/50
Learning rate:  0.003
 - 46s - loss: 0.9274 - acc: 0.7613 - val_loss: 1.0691 - val_acc: 0.7229

Epoch 00007: val_acc improved from 0.71320 to 0.72290, saving model to /content/saved_models/cifar10_ResNet20v1_model.007.h5
Epoch 8/50
Learning rate:  0.003
 - 46s - loss: 0.9033 - acc: 0.7691 - val_loss: 1.1050 - val_acc: 0.7267

Epoch 00008: val_acc improved from 0.72290 to 0.72670, saving model to /content/saved_models/cifar10_ResNet20v1_model.008.h5
Epoch 9/50
Learning rate:  0.003
 - 46s - loss: 0.8899 - acc: 0.7749 - val_loss: 1.0847 - val_acc: 0.7135

Epoch 00009: val_acc did not improve from 0.72670
Epoch 10/50
Learning rate:  0.0015
 - 46s - loss: 0.7624 - acc: 0.8137 - val_loss: 0.9293 - val_acc: 0.7656

Epoch 00010: val_acc improved from 0.72670 to 0.76560, saving model to /content/saved_models/cifar10_ResNet20v1_model.010.h5
Epoch 11/50
Learning rate:  0.0015
 - 46s - loss: 0.7114 - acc: 0.8234 - val_loss: 0.9530 - val_acc: 0.7659

Epoch 00011: val_acc improved from 0.76560 to 0.76590, saving model to /content/saved_models/cifar10_ResNet20v1_model.011.h5
Epoch 12/50
Learning rate:  0.0015
 - 46s - loss: 0.6967 - acc: 0.8267 - val_loss: 0.8770 - val_acc: 0.7804

Epoch 00012: val_acc improved from 0.76590 to 0.78040, saving model to /content/saved_models/cifar10_ResNet20v1_model.012.h5
Epoch 13/50
Learning rate:  0.0015
 - 46s - loss: 0.6793 - acc: 0.8313 - val_loss: 0.8006 - val_acc: 0.7898

Epoch 00013: val_acc improved from 0.78040 to 0.78980, saving model to /content/saved_models/cifar10_ResNet20v1_model.013.h5
Epoch 14/50
Learning rate:  0.0015
 - 46s - loss: 0.6711 - acc: 0.8306 - val_loss: 0.7675 - val_acc: 0.8069

Epoch 00014: val_acc improved from 0.78980 to 0.80690, saving model to /content/saved_models/cifar10_ResNet20v1_model.014.h5
Epoch 15/50
Learning rate:  0.0015
 - 47s - loss: 0.6590 - acc: 0.8355 - val_loss: 0.8233 - val_acc: 0.7899

Epoch 00015: val_acc did not improve from 0.80690
Epoch 16/50
Learning rate:  0.0015
 - 47s - loss: 0.6523 - acc: 0.8368 - val_loss: 0.7472 - val_acc: 0.8187

Epoch 00016: val_acc improved from 0.80690 to 0.81870, saving model to /content/saved_models/cifar10_ResNet20v1_model.016.h5
Epoch 17/50
Learning rate:  0.00135
 - 46s - loss: 0.6317 - acc: 0.8428 - val_loss: 0.7976 - val_acc: 0.8058

Epoch 00017: val_acc did not improve from 0.81870
Epoch 18/50
Learning rate:  0.00135
 - 46s - loss: 0.6185 - acc: 0.8479 - val_loss: 0.7274 - val_acc: 0.8180

Epoch 00018: val_acc did not improve from 0.81870
Epoch 19/50
Learning rate:  0.00135
 - 46s - loss: 0.6098 - acc: 0.8502 - val_loss: 0.7483 - val_acc: 0.8173

Epoch 00019: val_acc did not improve from 0.81870
Epoch 20/50
Learning rate:  0.00135
 - 46s - loss: 0.6113 - acc: 0.8500 - val_loss: 0.7749 - val_acc: 0.8100

Epoch 00020: val_acc did not improve from 0.81870
Epoch 21/50
Learning rate:  0.00135
 - 47s - loss: 0.6038 - acc: 0.8522 - val_loss: 0.7493 - val_acc: 0.8065

Epoch 00021: val_acc did not improve from 0.81870
Epoch 22/50
Learning rate:  0.00135
 - 46s - loss: 0.5992 - acc: 0.8523 - val_loss: 0.7452 - val_acc: 0.8132

Epoch 00022: val_acc did not improve from 0.81870
Epoch 23/50
Learning rate:  0.00135
 - 47s - loss: 0.5974 - acc: 0.8543 - val_loss: 0.7699 - val_acc: 0.7976

Epoch 00023: val_acc did not improve from 0.81870
Epoch 24/50
Learning rate:  0.00108
 - 47s - loss: 0.5633 - acc: 0.8646 - val_loss: 0.6634 - val_acc: 0.8292

Epoch 00024: val_acc improved from 0.81870 to 0.82920, saving model to /content/saved_models/cifar10_ResNet20v1_model.024.h5
Epoch 25/50
Learning rate:  0.00108
 - 47s - loss: 0.5535 - acc: 0.8667 - val_loss: 0.7492 - val_acc: 0.8210

Epoch 00025: val_acc did not improve from 0.82920
Epoch 26/50
Learning rate:  0.00108
 - 46s - loss: 0.5487 - acc: 0.8683 - val_loss: 0.8900 - val_acc: 0.7775

Epoch 00026: val_acc did not improve from 0.82920
Epoch 27/50
Learning rate:  0.0008640000000000001
 - 47s - loss: 0.5172 - acc: 0.8766 - val_loss: 0.6810 - val_acc: 0.8381

Epoch 00027: val_acc improved from 0.82920 to 0.83810, saving model to /content/saved_models/cifar10_ResNet20v1_model.027.h5
Epoch 28/50
Learning rate:  0.0008640000000000001
 - 47s - loss: 0.5089 - acc: 0.8770 - val_loss: 0.6430 - val_acc: 0.8483

Epoch 00028: val_acc improved from 0.83810 to 0.84830, saving model to /content/saved_models/cifar10_ResNet20v1_model.028.h5
Epoch 29/50
Learning rate:  0.0008640000000000001
 - 47s - loss: 0.5069 - acc: 0.8768 - val_loss: 0.7115 - val_acc: 0.8263

Epoch 00029: val_acc did not improve from 0.84830
Epoch 30/50
Learning rate:  0.0006048
 - 47s - loss: 0.4703 - acc: 0.8904 - val_loss: 0.5804 - val_acc: 0.8609

Epoch 00030: val_acc improved from 0.84830 to 0.86090, saving model to /content/saved_models/cifar10_ResNet20v1_model.030.h5
Epoch 31/50
Learning rate:  0.0006048
 - 47s - loss: 0.4560 - acc: 0.8930 - val_loss: 0.5545 - val_acc: 0.8657

Epoch 00031: val_acc improved from 0.86090 to 0.86570, saving model to /content/saved_models/cifar10_ResNet20v1_model.031.h5
Epoch 32/50
Learning rate:  0.0006048
 - 47s - loss: 0.4486 - acc: 0.8973 - val_loss: 0.5967 - val_acc: 0.8469

Epoch 00032: val_acc did not improve from 0.86570
Epoch 33/50
Learning rate:  0.0006048
 - 47s - loss: 0.4427 - acc: 0.8953 - val_loss: 0.5563 - val_acc: 0.8649

Epoch 00033: val_acc did not improve from 0.86570
Epoch 34/50
Learning rate:  0.0006048
 - 47s - loss: 0.4413 - acc: 0.8970 - val_loss: 0.6055 - val_acc: 0.8488

Epoch 00034: val_acc did not improve from 0.86570
Epoch 35/50
Learning rate:  0.0006048
 - 47s - loss: 0.4353 - acc: 0.8969 - val_loss: 0.5623 - val_acc: 0.8667

Epoch 00035: val_acc improved from 0.86570 to 0.86670, saving model to /content/saved_models/cifar10_ResNet20v1_model.035.h5
Epoch 36/50
Learning rate:  0.0006048
 - 47s - loss: 0.4330 - acc: 0.8974 - val_loss: 0.5342 - val_acc: 0.8679

Epoch 00036: val_acc improved from 0.86670 to 0.86790, saving model to /content/saved_models/cifar10_ResNet20v1_model.036.h5
Epoch 37/50
Learning rate:  0.00042336
 - 48s - loss: 0.3997 - acc: 0.9083 - val_loss: 0.6254 - val_acc: 0.8481

Epoch 00037: val_acc did not improve from 0.86790
Epoch 38/50
Learning rate:  0.00042336
 - 47s - loss: 0.3947 - acc: 0.9095 - val_loss: 0.6073 - val_acc: 0.8533

Epoch 00038: val_acc did not improve from 0.86790
Epoch 39/50
Learning rate:  0.00042336
 - 48s - loss: 0.3908 - acc: 0.9107 - val_loss: 0.5102 - val_acc: 0.8753

Epoch 00039: val_acc improved from 0.86790 to 0.87530, saving model to /content/saved_models/cifar10_ResNet20v1_model.039.h5
Epoch 40/50
Learning rate:  0.00042336
 - 48s - loss: 0.3852 - acc: 0.9124 - val_loss: 0.5645 - val_acc: 0.8598

Epoch 00040: val_acc did not improve from 0.87530
Epoch 41/50
Learning rate:  0.00042336
 - 49s - loss: 0.3851 - acc: 0.9107 - val_loss: 0.5278 - val_acc: 0.8700

Epoch 00041: val_acc did not improve from 0.87530
Epoch 42/50
Learning rate:  0.000338688
 - 48s - loss: 0.3656 - acc: 0.9169 - val_loss: 0.5644 - val_acc: 0.8611

Epoch 00042: val_acc did not improve from 0.87530
Epoch 43/50
Learning rate:  0.000338688
 - 48s - loss: 0.3639 - acc: 0.9166 - val_loss: 0.5001 - val_acc: 0.8806

Epoch 00043: val_acc improved from 0.87530 to 0.88060, saving model to /content/saved_models/cifar10_ResNet20v1_model.043.h5
Epoch 44/50
Learning rate:  0.000338688
 - 48s - loss: 0.3575 - acc: 0.9185 - val_loss: 0.5437 - val_acc: 0.8725

Epoch 00044: val_acc did not improve from 0.88060
Epoch 45/50
Learning rate:  0.000338688
 - 48s - loss: 0.3514 - acc: 0.9211 - val_loss: 0.5044 - val_acc: 0.8779

Epoch 00045: val_acc did not improve from 0.88060
Epoch 46/50
Learning rate:  0.000338688
 - 48s - loss: 0.3531 - acc: 0.9190 - val_loss: 0.5054 - val_acc: 0.8757

Epoch 00046: val_acc did not improve from 0.88060
Epoch 47/50
Learning rate:  0.000338688
 - 49s - loss: 0.3484 - acc: 0.9198 - val_loss: 0.5423 - val_acc: 0.8693

Epoch 00047: val_acc did not improve from 0.88060
Epoch 48/50
Learning rate:  0.000338688
 - 48s - loss: 0.3432 - acc: 0.9207 - val_loss: 0.5400 - val_acc: 0.8726

Epoch 00048: val_acc did not improve from 0.88060
Epoch 49/50
Learning rate:  0.000338688
 - 49s - loss: 0.3437 - acc: 0.9200 - val_loss: 0.5013 - val_acc: 0.8769

Epoch 00049: val_acc did not improve from 0.88060
Epoch 50/50
Learning rate:  0.000338688
 - 48s - loss: 0.3423 - acc: 0.9207 - val_loss: 0.5368 - val_acc: 0.8686

Epoch 00050: val_acc did not improve from 0.88060
