# EIP 4
**Deep learning Course by Inkers Technology Phase 1**
**Problem Statement**
*Change the model in such a way that after executing the code below, your accuracy print out is more than 99.0
score = model.evaluate(X_text, Y_text, verbose=0)
print(score)*
**My result of print(score)=99.13%**

- Convolution is a layer that filters and simplifies the content of an image into another image of less pixels.
- Filters/Kernels looks for a specific feature in an image. More the number of kernels more will be the features to be extracted.
- Epochs are the count of the number of cycles the entire dataset is trained by the model.
- 1x1 Convolution reduces the number of channels of the image so that the model runs smoothly on the RAM.
- 3x3 Convolution divides the entire image by 3x3 matrices and search features in each one of  and gives an image of reduced pixels.
- Feature Maps are the results given by the convolution layers which are the input to the next layer.
- Activation Function decides which neurons would be active in the hidden layers
- Receptive Field is the part of input image on which the features are checked by the convolution layer.
