# EIP 4
## Deep learning Course by Inkers Technology Phase 1
## Assignment 1
**Problem Statement**</br>
Change the model in such a way that after executing the code below, your accuracy print out is more than 99.0</br>
score = model.evaluate(X_text, Y_text, verbose=0)</br>
print(score)</br>
**My result of print(score)=99.13%**</br>

- **Convolution** is a layer that filters and simplifies the content of an image into another image of less pixels.
- **Filters/Kernels** looks for a specific feature in an image. More the number of kernels more will be the features to be extracted.
- **Epochs** are the count of the number of cycles the entire dataset is trained by the model.
- **1x1 Convolution** reduces the number of channels of the image so that the model runs smoothly on the RAM.
- **3x3 Convolution** divides the entire image by 3x3 matrices and search features in each one of  and gives an image of reduced pixels.
- **Feature Maps** are the results given by the convolution layers which are the input to the next layer.
- **Activation Function** decides which neurons would be active in the hidden layers
- **Receptive Field** is the part of input image on which the features are checked by the convolution layer.
## Assignment 2
**Problem Statement**</br>
Change the CODE file to achieve 99.4 percent accuracy within 15 k parameters and under 20 Epochs.</br>
Model: "sequential_1"
_________________________________________________________________
	Layer (type)                 Output Shape              Param #   
	conv2d_1 (Conv2D)            (None, 26, 26, 16)        160       
	batch_normalization_1 (Batch (None, 26, 26, 16)        64        
	conv2d_2 (Conv2D)            (None, 24, 24, 32)        4640      
	batch_normalization_2 (Batch (None, 24, 24, 32)        128       
	conv2d_3 (Conv2D)            (None, 24, 24, 16)        528       
	max_pooling2d_1 (MaxPooling2 (None, 12, 12, 16)        0         
	separable_conv2d_1 (Separabl (None, 10, 10, 16)        416       
	batch_normalization_3 (Batch (None, 10, 10, 16)        64        
	conv2d_4 (Conv2D)            (None, 8, 8, 16)          2320      
	separable_conv2d_2 (Separabl (None, 6, 6, 16)          416       
	batch_normalization_4 (Batch (None, 6, 6, 16)          64        
	conv2d_5 (Conv2D)            (None, 4, 4, 16)          2320      
	batch_normalization_5 (Batch (None, 4, 4, 16)          64        
	conv2d_6 (Conv2D)            (None, 1, 1, 10)          2570      
	batch_normalization_6 (Batch (None, 1, 1, 10)          40        
	flatten_1 (Flatten)          (None, 10)                0         
	activation_1 (Activation)    (None, 10)                0  
_________________________________________________________________ </br>
Total params: 13,794</br>
Trainable params: 13,582</br>
Non-trainable params: 212

</br>
from keras.optimizers import SGD
from keras.callbacks import LearningRateScheduler
def scheduler(epoch, lr):
  return round(0.003 * 1/(1 + 0.319 * epoch), 10)

model.compile(loss='categorical_crossentropy', optimizer=Adam(lr=0.003), metrics=['accuracy'])

model.fit(X_train, Y_train, batch_size=64, epochs=20, verbose=1, validation_data=(X_test, Y_test), callbacks=[LearningRateScheduler(scheduler, verbose=1)])
Train on 60000 samples, validate on 10000 samples
Epoch 1/20

Epoch 00001: LearningRateScheduler setting learning rate to 0.003.
60000/60000 [==============================] - 31s 515us/step - loss: 0.2594 - acc: 0.9534 - val_loss: 0.0755 - val_acc: 0.9814
Epoch 2/20

Epoch 00002: LearningRateScheduler setting learning rate to 0.0022744503.
60000/60000 [==============================] - 23s 384us/step - loss: 0.0800 - acc: 0.9823 - val_loss: 0.0463 - val_acc: 0.9877
Epoch 3/20

Epoch 00003: LearningRateScheduler setting learning rate to 0.0018315018.
60000/60000 [==============================] - 23s 386us/step - loss: 0.0582 - acc: 0.9859 - val_loss: 0.0414 - val_acc: 0.9883
Epoch 4/20

Epoch 00004: LearningRateScheduler setting learning rate to 0.0015329586.
60000/60000 [==============================] - 23s 381us/step - loss: 0.0469 - acc: 0.9878 - val_loss: 0.0335 - val_acc: 0.9903
Epoch 5/20

Epoch 00005: LearningRateScheduler setting learning rate to 0.0013181019.
60000/60000 [==============================] - 23s 378us/step - loss: 0.0397 - acc: 0.9898 - val_loss: 0.0423 - val_acc: 0.9875
Epoch 6/20

Epoch 00006: LearningRateScheduler setting learning rate to 0.0011560694.
60000/60000 [==============================] - 23s 377us/step - loss: 0.0329 - acc: 0.9919 - val_loss: 0.0305 - val_acc: 0.9919
Epoch 7/20

Epoch 00007: LearningRateScheduler setting learning rate to 0.0010295127.
60000/60000 [==============================] - 22s 374us/step - loss: 0.0297 - acc: 0.9920 - val_loss: 0.0353 - val_acc: 0.9893
Epoch 8/20

Epoch 00008: LearningRateScheduler setting learning rate to 0.0009279307.
60000/60000 [==============================] - 22s 375us/step - loss: 0.0245 - acc: 0.9935 - val_loss: 0.0286 - val_acc: 0.9920
Epoch 9/20

Epoch 00009: LearningRateScheduler setting learning rate to 0.0008445946.
60000/60000 [==============================] - 22s 375us/step - loss: 0.0219 - acc: 0.9940 - val_loss: 0.0277 - val_acc: 0.9927
Epoch 10/20

Epoch 00010: LearningRateScheduler setting learning rate to 0.0007749935.
60000/60000 [==============================] - 23s 377us/step - loss: 0.0213 - acc: 0.9943 - val_loss: 0.0252 - val_acc: 0.9921
Epoch 11/20

Epoch 00011: LearningRateScheduler setting learning rate to 0.0007159905.
60000/60000 [==============================] - 22s 374us/step - loss: 0.0181 - acc: 0.9954 - val_loss: 0.0273 - val_acc: 0.9914
Epoch 12/20

Epoch 00012: LearningRateScheduler setting learning rate to 0.000665336.
60000/60000 [==============================] - 22s 375us/step - loss: 0.0170 - acc: 0.9956 - val_loss: 0.0248 - val_acc: 0.9926
Epoch 13/20

Epoch 00013: LearningRateScheduler setting learning rate to 0.0006213753.
60000/60000 [==============================] - 23s 376us/step - loss: 0.0153 - acc: 0.9960 - val_loss: 0.0244 - val_acc: 0.9929
Epoch 14/20

Epoch 00014: LearningRateScheduler setting learning rate to 0.0005828638.
60000/60000 [==============================] - 23s 379us/step - loss: 0.0152 - acc: 0.9962 - val_loss: 0.0217 - val_acc: 0.9948
Epoch 15/20

Epoch 00015: LearningRateScheduler setting learning rate to 0.0005488474.
60000/60000 [==============================] - 23s 378us/step - loss: 0.0132 - acc: 0.9967 - val_loss: 0.0231 - val_acc: 0.9925
Epoch 16/20

Epoch 00016: LearningRateScheduler setting learning rate to 0.0005185825.
60000/60000 [==============================] - 22s 374us/step - loss: 0.0117 - acc: 0.9974 - val_loss: 0.0238 - val_acc: 0.9931
Epoch 17/20

Epoch 00017: LearningRateScheduler setting learning rate to 0.000491481.
60000/60000 [==============================] - 22s 375us/step - loss: 0.0107 - acc: 0.9974 - val_loss: 0.0222 - val_acc: 0.9931
Epoch 18/20

Epoch 00018: LearningRateScheduler setting learning rate to 0.0004670715.
60000/60000 [==============================] - 23s 376us/step - loss: 0.0100 - acc: 0.9977 - val_loss: 0.0244 - val_acc: 0.9919
Epoch 19/20

Epoch 00019: LearningRateScheduler setting learning rate to 0.0004449718.
60000/60000 [==============================] - 22s 375us/step - loss: 0.0095 - acc: 0.9979 - val_loss: 0.0217 - val_acc: 0.9928
Epoch 20/20

Epoch 00020: LearningRateScheduler setting learning rate to 0.000424869.
60000/60000 [==============================] - 22s 373us/step - loss: 0.0087 - acc: 0.9979 - val_loss: 0.0217 - val_acc: 0.9942
<keras.callbacks.History at 0x7f5f2b4dfac8>

score = model.evaluate(X_test, Y_test, verbose=0)</br>
print(score)</br>
[0.021678498815186322, 0.9942] </br>
## Strategy
The strategy I used to get 99.42 test accuracy was that I removed all the dropouts since it reduced the non trainable features. Instead of dropouts I used Separable Convolution layers to reduce the parameters.
I didn't reduce the kernel to 10 at the middle of the model since it was being reduced to 10 at the end.
I removed batch normalization from one of the layer because it trained some of the non trainable features which led to overfitting of the model.


