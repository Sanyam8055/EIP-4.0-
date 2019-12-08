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
## Assignment 3
**Problem Statement**</br>
Run the network (base network) for 50 epochs, report Validation Accuracy after 50 epochs. </br>
Add new cells at the bottom of the code, and write your own network such that:</br>
it uses depthwise separable convolution ONLY (no Conv2D)</br>
it uses BatchNormalization </br>
has less than 100,000 parameters</br>
it uses proper dropout values</br>
you've mentioned the output size for each layer</br>
you've mentioned the receptive field for each layer</br>
runs for 50 epochs</br>
beats the validation score within 50 epochs</br>
## Accuracy of the base model was 82.93
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:2: UserWarning: Update your `SeparableConv2D` call to the Keras 2 API: `SeparableConv2D(48, (3, 3), input_shape=(32, 32, 3...)`
  
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:5: UserWarning: Update your `SeparableConv2D` call to the Keras 2 API: `SeparableConv2D(48, (3, 3))`
  """
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:10: UserWarning: Update your `SeparableConv2D` call to the Keras 2 API: `SeparableConv2D(96, (3, 3), padding="same")`
 
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:13: UserWarning: Update your `SeparableConv2D` call to the Keras 2 API: `SeparableConv2D(96, (3, 3))`
  del sys.path[0]
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:18: UserWarning: Update your `SeparableConv2D` call to the Keras 2 API: `SeparableConv2D(192, (3, 3), padding="same")`
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:21: UserWarning: Update your `SeparableConv2D` call to the Keras 2 API: `SeparableConv2D(192, (3, 3))`
Model: "sequential_40"
_________________________________________________________________
	Layer (type)                 Output Shape              Param #   
	separable_conv2d_236 (Separa (None, 30, 30, 48)        219       
	batch_normalization_37 (Batc (None, 30, 30, 48)        192       
	activation_253 (Activation)  (None, 30, 30, 48)        0         
	separable_conv2d_237 (Separa (None, 28, 28, 48)        2784      
	batch_normalization_38 (Batc (None, 28, 28, 48)        192       
	activation_254 (Activation)  (None, 28, 28, 48)        0         
	max_pooling2d_113 (MaxPoolin (None, 14, 14, 48)        0         
	dropout_119 (Dropout)        (None, 14, 14, 48)        0         
	separable_conv2d_238 (Separa (None, 14, 14, 96)        5136      
	batch_normalization_39 (Batc (None, 14, 14, 96)        384       
	activation_255 (Activation)  (None, 14, 14, 96)        0         
	separable_conv2d_239 (Separa (None, 12, 12, 96)        10176     
	batch_normalization_40 (Batc (None, 12, 12, 96)        384       
	activation_256 (Activation)  (None, 12, 12, 96)        0         
	max_pooling2d_114 (MaxPoolin (None, 6, 6, 96)          0         
	dropout_120 (Dropout)        (None, 6, 6, 96)          0         
	separable_conv2d_240 (Separa (None, 6, 6, 192)         19488     
	batch_normalization_41 (Batc (None, 6, 6, 192)         768       
	activation_257 (Activation)  (None, 6, 6, 192)         0         
	separable_conv2d_241 (Separa (None, 4, 4, 192)         38784     
	batch_normalization_42 (Batc (None, 4, 4, 192)         768       
	activation_258 (Activation)  (None, 4, 4, 192)         0         
	max_pooling2d_115 (MaxPoolin (None, 2, 2, 192)         0         
	dropout_121 (Dropout)        (None, 2, 2, 192)         0         
	separable_conv2d_242 (Separa (None, 1, 1, 10)          2698      
	flatten_34 (Flatten)         (None, 10)                0         
	activation_259 (Activation)  (None, 10)                0       
_________________________________________________________________
Total params: 81,973</br>
Trainable params: 80,629</br>
Non-trainable params: 1,344</br>

/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:16: UserWarning: The semantics of the Keras 2 argument `steps_per_epoch` is not the same as the Keras 1 argument `samples_per_epoch`. `steps_per_epoch` is the number of batches to draw from the generator at each epoch. Basically steps_per_epoch = samples_per_epoch/batch_size. Similarly `nb_val_samples`->`validation_steps` and `val_samples`->`steps` arguments have changed. Update your method calls accordingly.
  app.launch_new_instance()
/usr/local/lib/python3.6/dist-packages/ipykernel_launcher.py:16: UserWarning: Update your `fit_generator` call to the Keras 2 API: `fit_generator(<keras_pre..., validation_data=(array([[[..., verbose=1, callbacks=[<keras.ca..., steps_per_epoch=390, epochs=50)`
  app.launch_new_instance()
Epoch 1/50
390/390 [==============================] - 37s 95ms/step - loss: 1.3742 - acc: 0.5014 - val_loss: 1.3988 - val_acc: 0.5484
Epoch 2/50
390/390 [==============================] - 28s 71ms/step - loss: 1.0189 - acc: 0.6352 - val_loss: 1.0049 - val_acc: 0.6564
Epoch 3/50
390/390 [==============================] - 28s 71ms/step - loss: 0.8870 - acc: 0.6841 - val_loss: 0.9708 - val_acc: 0.6715
Epoch 4/50
390/390 [==============================] - 28s 71ms/step - loss: 0.8030 - acc: 0.7172 - val_loss: 0.7382 - val_acc: 0.7411
Epoch 5/50
390/390 [==============================] - 28s 71ms/step - loss: 0.7512 - acc: 0.7372 - val_loss: 0.7794 - val_acc: 0.7339
Epoch 6/50
390/390 [==============================] - 28s 72ms/step - loss: 0.7100 - acc: 0.7498 - val_loss: 0.6611 - val_acc: 0.7721
Epoch 7/50
390/390 [==============================] - 28s 71ms/step - loss: 0.6811 - acc: 0.7613 - val_loss: 0.6688 - val_acc: 0.7681
Epoch 8/50
390/390 [==============================] - 28s 71ms/step - loss: 0.6554 - acc: 0.7693 - val_loss: 0.6246 - val_acc: 0.7828
Epoch 9/50
390/390 [==============================] - 28s 71ms/step - loss: 0.6346 - acc: 0.7767 - val_loss: 0.6536 - val_acc: 0.7733
Epoch 10/50
390/390 [==============================] - 28s 71ms/step - loss: 0.6146 - acc: 0.7847 - val_loss: 0.6117 - val_acc: 0.7893
Epoch 11/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5993 - acc: 0.7900 - val_loss: 0.6117 - val_acc: 0.7917
Epoch 12/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5869 - acc: 0.7963 - val_loss: 0.6609 - val_acc: 0.7733
Epoch 13/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5737 - acc: 0.7977 - val_loss: 0.6122 - val_acc: 0.7910
Epoch 14/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5614 - acc: 0.8036 - val_loss: 0.5749 - val_acc: 0.8034
Epoch 15/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5564 - acc: 0.8051 - val_loss: 0.5811 - val_acc: 0.8017
Epoch 16/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5428 - acc: 0.8090 - val_loss: 0.6066 - val_acc: 0.7936
Epoch 17/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5350 - acc: 0.8123 - val_loss: 0.5911 - val_acc: 0.8003
Epoch 18/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5282 - acc: 0.8154 - val_loss: 0.5835 - val_acc: 0.8018
Epoch 19/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5220 - acc: 0.8183 - val_loss: 0.5507 - val_acc: 0.8134
Epoch 20/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5188 - acc: 0.8180 - val_loss: 0.5389 - val_acc: 0.8157
Epoch 21/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5082 - acc: 0.8220 - val_loss: 0.5393 - val_acc: 0.8175
Epoch 22/50
390/390 [==============================] - 28s 71ms/step - loss: 0.5057 - acc: 0.8232 - val_loss: 0.5337 - val_acc: 0.8194
Epoch 23/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4997 - acc: 0.8252 - val_loss: 0.5378 - val_acc: 0.8194
Epoch 24/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4949 - acc: 0.8271 - val_loss: 0.5372 - val_acc: 0.8167
Epoch 25/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4923 - acc: 0.8270 - val_loss: 0.5364 - val_acc: 0.8172
Epoch 26/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4874 - acc: 0.8295 - val_loss: 0.5335 - val_acc: 0.8220
Epoch 27/50
390/390 [==============================] - 28s 72ms/step - loss: 0.4803 - acc: 0.8317 - val_loss: 0.5476 - val_acc: 0.8167
Epoch 28/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4789 - acc: 0.8309 - val_loss: 0.5294 - val_acc: 0.8200
Epoch 29/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4696 - acc: 0.8356 - val_loss: 0.5303 - val_acc: 0.8207
Epoch 30/50
390/390 [==============================] - 28s 72ms/step - loss: 0.4757 - acc: 0.8317 - val_loss: 0.5212 - val_acc: 0.8233
Epoch 31/50
390/390 [==============================] - 28s 72ms/step - loss: 0.4622 - acc: 0.8373 - val_loss: 0.5233 - val_acc: 0.8237
Epoch 32/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4666 - acc: 0.8350 - val_loss: 0.5086 - val_acc: 0.8278
Epoch 33/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4609 - acc: 0.8381 - val_loss: 0.5294 - val_acc: 0.8211
Epoch 34/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4654 - acc: 0.8360 - val_loss: 0.5205 - val_acc: 0.8250
Epoch 35/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4588 - acc: 0.8376 - val_loss: 0.5180 - val_acc: 0.8275
Epoch 36/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4512 - acc: 0.8407 - val_loss: 0.5183 - val_acc: 0.8253
Epoch 37/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4511 - acc: 0.8402 - val_loss: 0.5256 - val_acc: 0.8237
Epoch 38/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4443 - acc: 0.8433 - val_loss: 0.5101 - val_acc: 0.8287
Epoch 39/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4497 - acc: 0.8418 - val_loss: 0.5136 - val_acc: 0.8288
Epoch 40/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4415 - acc: 0.8436 - val_loss: 0.5098 - val_acc: 0.8299
Epoch 41/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4398 - acc: 0.8445 - val_loss: 0.5224 - val_acc: 0.8260
Epoch 42/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4441 - acc: 0.8431 - val_loss: 0.5151 - val_acc: 0.8290
Epoch 43/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4389 - acc: 0.8442 - val_loss: 0.5060 - val_acc: 0.8312
Epoch 44/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4337 - acc: 0.8464 - val_loss: 0.5074 - val_acc: 0.8309
Epoch 45/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4351 - acc: 0.8445 - val_loss: 0.5061 - val_acc: 0.8319
Epoch 46/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4305 - acc: 0.8471 - val_loss: 0.5131 - val_acc: 0.8305
Epoch 47/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4300 - acc: 0.8463 - val_loss: 0.5107 - val_acc: 0.8300
Epoch 48/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4278 - acc: 0.8482 - val_loss: 0.5038 - val_acc: 0.8330
Epoch 49/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4258 - acc: 0.8483 - val_loss: 0.5137 - val_acc: 0.8277
Epoch 50/50
390/390 [==============================] - 28s 71ms/step - loss: 0.4212 - acc: 0.8498 - val_loss: 0.5016 - val_acc: 0.8350
Model took 1398.99 seconds to train

### Accuracy on test data is: 83.50
## Assignment 4b
**Problem Statement**</br>
To create ResNet18 Network </br>
Train on CIFAR10 data.</br>  
Run for 50 Epochs and cross 88% Validation Accuracy</br>
Show GradCam results for 10 images.</br> 
### I got an Accuracy of 88.06% within 50 epochs.
