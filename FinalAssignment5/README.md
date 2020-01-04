## FINAL ASSIGNMENT
The assignment requires you to:</br>
implement multi class classification(you must download the data and link your own Google Drive Link).</br>
Run it for as long as you'd like to</br>
Use any model of your choice</br>
Use any augmentation of your choice</br>
You cannot use transfer learning and train your model from scratch</br>
Since this is a blind assignment, we do not know the final achievable accuracy. </br>
Marks would be allotted percentile-wise.</br>
Your final accuracy matters the most. </br>
## Result
val_gender_output_acc: 0.7828 - val_image_quality_output_acc: 0.5599 - val_age_output_acc: 0.3797 - val_weight_output_acc: 0.6391 - val_bag_output_acc: 0.5969 - val_footwear_output_acc: 0.6453 - val_pose_output_acc: 0.7453 - val_emotion_output_acc: 0.6849
## Model RESNET50V2
    Layer (type)                    Output Shape         Param #     Connected to                     
    input_3 (InputLayer)            (None, 224, 224, 3)  0                                       
    conv1_pad (ZeroPadding2D)       (None, 230, 230, 3)  0           input_3[0][0]              
    conv1_conv (Conv2D)             (None, 112, 112, 64) 9472        conv1_pad[0][0]            
    pool1_pad (ZeroPadding2D)       (None, 114, 114, 64) 0           conv1_conv[0][0]        
    pool1_pool (MaxPooling2D)       (None, 56, 56, 64)   0           pool1_pad[0][0]           
    conv2_block1_preact_bn (BatchNo (None, 56, 56, 64)   256         pool1_pool[0][0]          
    conv2_block1_preact_relu (Activ (None, 56, 56, 64)   0           conv2_block1_preact_bn[0][0] 
    conv2_block1_1_conv (Conv2D)    (None, 56, 56, 64)   4096        conv2_block1_preact_relu[0][0] 
    conv2_block1_1_bn (BatchNormali (None, 56, 56, 64)   256         conv2_block1_1_conv[0][0]   
    conv2_block1_1_relu (Activation (None, 56, 56, 64)   0           conv2_block1_1_bn[0][0]     
    conv2_block1_2_pad (ZeroPadding (None, 58, 58, 64)   0           conv2_block1_1_relu[0][0]   
    conv2_block1_2_conv (Conv2D)    (None, 56, 56, 64)   36864       conv2_block1_2_pad[0][0]    
    conv2_block1_2_bn (BatchNormali (None, 56, 56, 64)   256         conv2_block1_2_conv[0][0]   
    conv2_block1_2_relu (Activation (None, 56, 56, 64)   0           conv2_block1_2_bn[0][0]    
    conv2_block1_0_conv (Conv2D)    (None, 56, 56, 256)  16640       conv2_block1_preact_relu[0][0] 
    conv2_block1_3_conv (Conv2D)    (None, 56, 56, 256)  16640       conv2_block1_2_relu[0][0]   
    conv2_block1_out (Add)          (None, 56, 56, 256)  0           conv2_block1_0_conv[0][0]        
                                                                 conv2_block1_3_conv[0][0]    
    conv2_block2_preact_bn (BatchNo (None, 56, 56, 256)  1024        conv2_block1_out[0][0]     
    conv2_block2_preact_relu (Activ (None, 56, 56, 256)  0           conv2_block2_preact_bn[0][0]  
    conv2_block2_1_conv (Conv2D)    (None, 56, 56, 64)   16384       conv2_block2_preact_relu[0][0]  
    conv2_block2_1_bn (BatchNormali (None, 56, 56, 64)   256         conv2_block2_1_conv[0][0]   
    conv2_block2_1_relu (Activation (None, 56, 56, 64)   0           conv2_block2_1_bn[0][0]    
    conv2_block2_2_pad (ZeroPadding (None, 58, 58, 64)   0           conv2_block2_1_relu[0][0]   
    conv2_block2_2_conv (Conv2D)    (None, 56, 56, 64)   36864       conv2_block2_2_pad[0][0]   
    conv2_block2_2_bn (BatchNormali (None, 56, 56, 64)   256         conv2_block2_2_conv[0][0]   
    conv2_block2_2_relu (Activation (None, 56, 56, 64)   0           conv2_block2_2_bn[0][0]    
    conv2_block2_3_conv (Conv2D)    (None, 56, 56, 256)  16640       conv2_block2_2_relu[0][0]   
    conv2_block2_out (Add)          (None, 56, 56, 256)  0           conv2_block1_out[0][0]           
                                                                 conv2_block2_3_conv[0][0]        
    conv2_block3_preact_bn (BatchNo (None, 56, 56, 256)  1024        conv2_block2_out[0][0]      
    conv2_block3_preact_relu (Activ (None, 56, 56, 256)  0           conv2_block3_preact_bn[0][0] 
    conv2_block3_1_conv (Conv2D)    (None, 56, 56, 64)   16384       conv2_block3_preact_relu[0][0] 
    conv2_block3_1_bn (BatchNormali (None, 56, 56, 64)   256         conv2_block3_1_conv[0][0]   
    conv2_block3_1_relu (Activation (None, 56, 56, 64)   0           conv2_block3_1_bn[0][0]     
    conv2_block3_2_pad (ZeroPadding (None, 58, 58, 64)   0           conv2_block3_1_relu[0][0]    
    conv2_block3_2_conv (Conv2D)    (None, 28, 28, 64)   36864       conv2_block3_2_pad[0][0]    
    conv2_block3_2_bn (BatchNormali (None, 28, 28, 64)   256         conv2_block3_2_conv[0][0]    
    conv2_block3_2_relu (Activation (None, 28, 28, 64)   0           conv2_block3_2_bn[0][0]       
    max_pooling2d_7 (MaxPooling2D)  (None, 28, 28, 256)  0           conv2_block2_out[0][0]        
    conv2_block3_3_conv (Conv2D)    (None, 28, 28, 256)  16640       conv2_block3_2_relu[0][0]    
    conv2_block3_out (Add)          (None, 28, 28, 256)  0           max_pooling2d_7[0][0]            
                                                                 conv2_block3_3_conv[0][0]        
    conv3_block1_preact_bn (BatchNo (None, 28, 28, 256)  1024        conv2_block3_out[0][0]      
    conv3_block1_preact_relu (Activ (None, 28, 28, 256)  0           conv3_block1_preact_bn[0][0]  
    conv3_block1_1_conv (Conv2D)    (None, 28, 28, 128)  32768       conv3_block1_preact_relu[0][0]   
    conv3_block1_1_bn (BatchNormali (None, 28, 28, 128)  512         conv3_block1_1_conv[0][0]      
    conv3_block1_1_relu (Activation (None, 28, 28, 128)  0           conv3_block1_1_bn[0][0]     
    conv3_block1_2_pad (ZeroPadding (None, 30, 30, 128)  0           conv3_block1_1_relu[0][0]    
    conv3_block1_2_conv (Conv2D)    (None, 28, 28, 128)  147456      conv3_block1_2_pad[0][0]    
    conv3_block1_2_bn (BatchNormali (None, 28, 28, 128)  512         conv3_block1_2_conv[0][0]    
    conv3_block1_2_relu (Activation (None, 28, 28, 128)  0           conv3_block1_2_bn[0][0]     
    conv3_block1_0_conv (Conv2D)    (None, 28, 28, 512)  131584      conv3_block1_preact_relu[0][0] 
    conv3_block1_3_conv (Conv2D)    (None, 28, 28, 512)  66048       conv3_block1_2_relu[0][0]   
    conv3_block1_out (Add)          (None, 28, 28, 512)  0           conv3_block1_0_conv[0][0]        
                                                                 conv3_block1_3_conv[0][0]       
    conv3_block2_preact_bn (BatchNo (None, 28, 28, 512)  2048        conv3_block1_out[0][0]      
    conv3_block2_preact_relu (Activ (None, 28, 28, 512)  0           conv3_block2_preact_bn[0][0] 
    conv3_block2_1_conv (Conv2D)    (None, 28, 28, 128)  65536       conv3_block2_preact_relu[0][0]  
    conv3_block2_1_bn (BatchNormali (None, 28, 28, 128)  512         conv3_block2_1_conv[0][0]    
    conv3_block2_1_relu (Activation (None, 28, 28, 128)  0           conv3_block2_1_bn[0][0]      
    conv3_block2_2_pad (ZeroPadding (None, 30, 30, 128)  0           conv3_block2_1_relu[0][0]   
    conv3_block2_2_conv (Conv2D)    (None, 28, 28, 128)  147456      conv3_block2_2_pad[0][0]     
    conv3_block2_2_bn (BatchNormali (None, 28, 28, 128)  512         conv3_block2_2_conv[0][0]    
    conv3_block2_2_relu (Activation (None, 28, 28, 128)  0           conv3_block2_2_bn[0][0]      
    conv3_block2_3_conv (Conv2D)    (None, 28, 28, 512)  66048       conv3_block2_2_relu[0][0]    
    conv3_block2_out (Add)          (None, 28, 28, 512)  0           conv3_block1_out[0][0]           
                                                                 conv3_block2_3_conv[0][0]        
    conv3_block3_preact_bn (BatchNo (None, 28, 28, 512)  2048        conv3_block2_out[0][0]         
    conv3_block3_preact_relu (Activ (None, 28, 28, 512)  0           conv3_block3_preact_bn[0][0]  
    conv3_block3_1_conv (Conv2D)    (None, 28, 28, 128)  65536       conv3_block3_preact_relu[0][0]
    conv3_block3_1_bn (BatchNormali (None, 28, 28, 128)  512         conv3_block3_1_conv[0][0]      
    conv3_block3_1_relu (Activation (None, 28, 28, 128)  0           conv3_block3_1_bn[0][0]        
    conv3_block3_2_pad (ZeroPadding (None, 30, 30, 128)  0           conv3_block3_1_relu[0][0]      
    conv3_block3_2_conv (Conv2D)    (None, 28, 28, 128)  147456      conv3_block3_2_pad[0][0]    
    conv3_block3_2_bn (BatchNormali (None, 28, 28, 128)  512         conv3_block3_2_conv[0][0]     
    conv3_block3_2_relu (Activation (None, 28, 28, 128)  0           conv3_block3_2_bn[0][0]       
    conv3_block3_3_conv (Conv2D)    (None, 28, 28, 512)  66048       conv3_block3_2_relu[0][0]     
    conv3_block3_out (Add)          (None, 28, 28, 512)  0           conv3_block2_out[0][0]           
                                                                 conv3_block3_3_conv[0][0]        
    conv3_block4_preact_bn (BatchNo (None, 28, 28, 512)  2048        conv3_block3_out[0][0]       
    conv3_block4_preact_relu (Activ (None, 28, 28, 512)  0           conv3_block4_preact_bn[0][0]  
    conv3_block4_1_conv (Conv2D)    (None, 28, 28, 128)  65536       conv3_block4_preact_relu[0][0] 
    conv3_block4_1_bn (BatchNormali (None, 28, 28, 128)  512         conv3_block4_1_conv[0][0]      
    conv3_block4_1_relu (Activation (None, 28, 28, 128)  0           conv3_block4_1_bn[0][0]       
    conv3_block4_2_pad (ZeroPadding (None, 30, 30, 128)  0           conv3_block4_1_relu[0][0]     
    conv3_block4_2_conv (Conv2D)    (None, 14, 14, 128)  147456      conv3_block4_2_pad[0][0]    
    conv3_block4_2_bn (BatchNormali (None, 14, 14, 128)  512         conv3_block4_2_conv[0][0]  
    conv3_block4_2_relu (Activation (None, 14, 14, 128)  0           conv3_block4_2_bn[0][0]    
    max_pooling2d_8 (MaxPooling2D)  (None, 14, 14, 512)  0           conv3_block3_out[0][0]     
    conv3_block4_3_conv (Conv2D)    (None, 14, 14, 512)  66048       conv3_block4_2_relu[0][0]    
    conv3_block4_out (Add)          (None, 14, 14, 512)  0           max_pooling2d_8[0][0]            
                                                                 conv3_block4_3_conv[0][0]       
    conv4_block1_preact_bn (BatchNo (None, 14, 14, 512)  2048        conv3_block4_out[0][0]     
    conv4_block1_preact_relu (Activ (None, 14, 14, 512)  0           conv4_block1_preact_bn[0][0]   
    conv4_block1_1_conv (Conv2D)    (None, 14, 14, 256)  131072      conv4_block1_preact_relu[0][0]   
    conv4_block1_1_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block1_1_conv[0][0]  
    conv4_block1_1_relu (Activation (None, 14, 14, 256)  0           conv4_block1_1_bn[0][0]      
    conv4_block1_2_pad (ZeroPadding (None, 16, 16, 256)  0           conv4_block1_1_relu[0][0]   
    conv4_block1_2_conv (Conv2D)    (None, 14, 14, 256)  589824      conv4_block1_2_pad[0][0]     
    conv4_block1_2_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block1_2_conv[0][0]     
    conv4_block1_2_relu (Activation (None, 14, 14, 256)  0           conv4_block1_2_bn[0][0]       
    conv4_block1_0_conv (Conv2D)    (None, 14, 14, 1024) 525312      conv4_block1_preact_relu[0][0]  
    conv4_block1_3_conv (Conv2D)    (None, 14, 14, 1024) 263168      conv4_block1_2_relu[0][0]    
    conv4_block1_out (Add)          (None, 14, 14, 1024) 0           conv4_block1_0_conv[0][0]        
                                                                 conv4_block1_3_conv[0][0]        
    conv4_block2_preact_bn (BatchNo (None, 14, 14, 1024) 4096        conv4_block1_out[0][0]           
    conv4_block2_preact_relu (Activ (None, 14, 14, 1024) 0           conv4_block2_preact_bn[0][0] 
    conv4_block2_1_conv (Conv2D)    (None, 14, 14, 256)  262144      conv4_block2_preact_relu[0][0] 
    conv4_block2_1_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block2_1_conv[0][0]     
    conv4_block2_1_relu (Activation (None, 14, 14, 256)  0           conv4_block2_1_bn[0][0]        
    conv4_block2_2_pad (ZeroPadding (None, 16, 16, 256)  0           conv4_block2_1_relu[0][0]      
    conv4_block2_2_conv (Conv2D)    (None, 14, 14, 256)  589824      conv4_block2_2_pad[0][0]     
    conv4_block2_2_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block2_2_conv[0][0]    
    conv4_block2_2_relu (Activation (None, 14, 14, 256)  0           conv4_block2_2_bn[0][0]      
    conv4_block2_3_conv (Conv2D)    (None, 14, 14, 1024) 263168      conv4_block2_2_relu[0][0]   
    conv4_block2_out (Add)          (None, 14, 14, 1024) 0           conv4_block1_out[0][0]           
                                                                 conv4_block2_3_conv[0][0]        
    conv4_block3_preact_bn (BatchNo (None, 14, 14, 1024) 4096        conv4_block2_out[0][0]          
    conv4_block3_preact_relu (Activ (None, 14, 14, 1024) 0           conv4_block3_preact_bn[0][0]   
    conv4_block3_1_conv (Conv2D)    (None, 14, 14, 256)  262144      conv4_block3_preact_relu[0][0] 
    conv4_block3_1_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block3_1_conv[0][0]    
    conv4_block3_1_relu (Activation (None, 14, 14, 256)  0           conv4_block3_1_bn[0][0]      
    conv4_block3_2_pad (ZeroPadding (None, 16, 16, 256)  0           conv4_block3_1_relu[0][0]    
    conv4_block3_2_conv (Conv2D)    (None, 14, 14, 256)  589824      conv4_block3_2_pad[0][0]    
    conv4_block3_2_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block3_2_conv[0][0]   
    conv4_block3_2_relu (Activation (None, 14, 14, 256)  0           conv4_block3_2_bn[0][0]     
    conv4_block3_3_conv (Conv2D)    (None, 14, 14, 1024) 263168      conv4_block3_2_relu[0][0]   
    conv4_block3_out (Add)          (None, 14, 14, 1024) 0           conv4_block2_out[0][0]           
                                                                 conv4_block3_3_conv[0][0]    
    conv4_block4_preact_bn (BatchNo (None, 14, 14, 1024) 4096        conv4_block3_out[0][0]    
    conv4_block4_preact_relu (Activ (None, 14, 14, 1024) 0           conv4_block4_preact_bn[0][0] 
    conv4_block4_1_conv (Conv2D)    (None, 14, 14, 256)  262144      conv4_block4_preact_relu[0][0] 
    conv4_block4_1_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block4_1_conv[0][0]
    conv4_block4_1_relu (Activation (None, 14, 14, 256)  0           conv4_block4_1_bn[0][0] 
    conv4_block4_2_pad (ZeroPadding (None, 16, 16, 256)  0           conv4_block4_1_relu[0][0]   
    conv4_block4_2_conv (Conv2D)    (None, 14, 14, 256)  589824      conv4_block4_2_pad[0][0]   
    conv4_block4_2_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block4_2_conv[0][0] 
    conv4_block4_2_relu (Activation (None, 14, 14, 256)  0           conv4_block4_2_bn[0][0]     
    conv4_block4_3_conv (Conv2D)    (None, 14, 14, 1024) 263168      conv4_block4_2_relu[0][0]    
    conv4_block4_out (Add)          (None, 14, 14, 1024) 0           conv4_block3_out[0][0]           
                                                                 conv4_block4_3_conv[0][0]        
    conv4_block5_preact_bn (BatchNo (None, 14, 14, 1024) 4096        conv4_block4_out[0][0]      
    conv4_block5_preact_relu (Activ (None, 14, 14, 1024) 0           conv4_block5_preact_bn[0][0]  
    conv4_block5_1_conv (Conv2D)    (None, 14, 14, 256)  262144      conv4_block5_preact_relu[0][0] 
    conv4_block5_1_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block5_1_conv[0][0]    
    conv4_block5_1_relu (Activation (None, 14, 14, 256)  0           conv4_block5_1_bn[0][0]       
    conv4_block5_2_pad (ZeroPadding (None, 16, 16, 256)  0           conv4_block5_1_relu[0][0] 
    conv4_block5_2_conv (Conv2D)    (None, 14, 14, 256)  589824      conv4_block5_2_pad[0][0] 
    conv4_block5_2_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block5_2_conv[0][0]   
    conv4_block5_2_relu (Activation (None, 14, 14, 256)  0           conv4_block5_2_bn[0][0]     
    conv4_block5_3_conv (Conv2D)    (None, 14, 14, 1024) 263168      conv4_block5_2_relu[0][0]   
    conv4_block5_out (Add)          (None, 14, 14, 1024) 0           conv4_block4_out[0][0]           
                                                                 conv4_block5_3_conv[0][0]     
    conv4_block6_preact_bn (BatchNo (None, 14, 14, 1024) 4096        conv4_block5_out[0][0]     
    conv4_block6_preact_relu (Activ (None, 14, 14, 1024) 0           conv4_block6_preact_bn[0][0]
    conv4_block6_1_conv (Conv2D)    (None, 14, 14, 256)  262144      conv4_block6_preact_relu[0][0] 
    conv4_block6_1_bn (BatchNormali (None, 14, 14, 256)  1024        conv4_block6_1_conv[0][0]  
    conv4_block6_1_relu (Activation (None, 14, 14, 256)  0           conv4_block6_1_bn[0][0]    
    conv4_block6_2_pad (ZeroPadding (None, 16, 16, 256)  0           conv4_block6_1_relu[0][0]  
    conv4_block6_2_conv (Conv2D)    (None, 7, 7, 256)    589824      conv4_block6_2_pad[0][0]   
    conv4_block6_2_bn (BatchNormali (None, 7, 7, 256)    1024        conv4_block6_2_conv[0][0] 
    conv4_block6_2_relu (Activation (None, 7, 7, 256)    0           conv4_block6_2_bn[0][0]   
    max_pooling2d_9 (MaxPooling2D)  (None, 7, 7, 1024)   0           conv4_block5_out[0][0]     
    conv4_block6_3_conv (Conv2D)    (None, 7, 7, 1024)   263168      conv4_block6_2_relu[0][0]   
    conv4_block6_out (Add)          (None, 7, 7, 1024)   0           max_pooling2d_9[0][0]            
                                                                 conv4_block6_3_conv[0][0]      
    conv5_block1_preact_bn (BatchNo (None, 7, 7, 1024)   4096        conv4_block6_out[0][0]     
    conv5_block1_preact_relu (Activ (None, 7, 7, 1024)   0           conv5_block1_preact_bn[0][0] 
    conv5_block1_1_conv (Conv2D)    (None, 7, 7, 512)    524288      conv5_block1_preact_relu[0][0]  
    conv5_block1_1_bn (BatchNormali (None, 7, 7, 512)    2048        conv5_block1_1_conv[0][0]   
    conv5_block1_1_relu (Activation (None, 7, 7, 512)    0           conv5_block1_1_bn[0][0]    
    conv5_block1_2_pad (ZeroPadding (None, 9, 9, 512)    0           conv5_block1_1_relu[0][0]  
    conv5_block1_2_conv (Conv2D)    (None, 7, 7, 512)    2359296     conv5_block1_2_pad[0][0]   
    conv5_block1_2_bn (BatchNormali (None, 7, 7, 512)    2048        conv5_block1_2_conv[0][0]   
    conv5_block1_2_relu (Activation (None, 7, 7, 512)    0           conv5_block1_2_bn[0][0]      
    conv5_block1_0_conv (Conv2D)    (None, 7, 7, 2048)   2099200     conv5_block1_preact_relu[0][0]  
    conv5_block1_3_conv (Conv2D)    (None, 7, 7, 2048)   1050624     conv5_block1_2_relu[0][0]      
    conv5_block1_out (Add)          (None, 7, 7, 2048)   0           conv5_block1_0_conv[0][0]        
                                                                 conv5_block1_3_conv[0][0]        
    conv5_block2_preact_bn (BatchNo (None, 7, 7, 2048)   8192        conv5_block1_out[0][0]      
    conv5_block2_preact_relu (Activ (None, 7, 7, 2048)   0           conv5_block2_preact_bn[0][0]  
    conv5_block2_1_conv (Conv2D)    (None, 7, 7, 512)    1048576     conv5_block2_preact_relu[0][0] 
    conv5_block2_1_bn (BatchNormali (None, 7, 7, 512)    2048        conv5_block2_1_conv[0][0]  
    conv5_block2_1_relu (Activation (None, 7, 7, 512)    0           conv5_block2_1_bn[0][0]     
    conv5_block2_2_pad (ZeroPadding (None, 9, 9, 512)    0           conv5_block2_1_relu[0][0]  
    conv5_block2_2_conv (Conv2D)    (None, 7, 7, 512)    2359296     conv5_block2_2_pad[0][0]     
    conv5_block2_2_bn (BatchNormali (None, 7, 7, 512)    2048        conv5_block2_2_conv[0][0]    
    conv5_block2_2_relu (Activation (None, 7, 7, 512)    0           conv5_block2_2_bn[0][0]      
    conv5_block2_3_conv (Conv2D)    (None, 7, 7, 2048)   1050624     conv5_block2_2_relu[0][0]   
    conv5_block2_out (Add)          (None, 7, 7, 2048)   0           conv5_block1_out[0][0]           
                                                                 conv5_block2_3_conv[0][0]        
    conv5_block3_preact_bn (BatchNo (None, 7, 7, 2048)   8192        conv5_block2_out[0][0]       
    conv5_block3_preact_relu (Activ (None, 7, 7, 2048)   0           conv5_block3_preact_bn[0][0]  
    conv5_block3_1_conv (Conv2D)    (None, 7, 7, 512)    1048576     conv5_block3_preact_relu[0][0]
    conv5_block3_1_bn (BatchNormali (None, 7, 7, 512)    2048        conv5_block3_1_conv[0][0]  
    conv5_block3_1_relu (Activation (None, 7, 7, 512)    0           conv5_block3_1_bn[0][0]     
    conv5_block3_2_pad (ZeroPadding (None, 9, 9, 512)    0           conv5_block3_1_relu[0][0]   
    conv5_block3_2_conv (Conv2D)    (None, 7, 7, 512)    2359296     conv5_block3_2_pad[0][0]   
    conv5_block3_2_bn (BatchNormali (None, 7, 7, 512)    2048        conv5_block3_2_conv[0][0]   
    conv5_block3_2_relu (Activation (None, 7, 7, 512)    0           conv5_block3_2_bn[0][0]   
    conv5_block3_3_conv (Conv2D)    (None, 7, 7, 2048)   1050624     conv5_block3_2_relu[0][0]  
    conv5_block3_out (Add)          (None, 7, 7, 2048)   0           conv5_block2_out[0][0]           
                                                                 conv5_block3_3_conv[0][0]      
    post_bn (BatchNormalization)    (None, 7, 7, 2048)   8192        conv5_block3_out[0][0]     
    post_relu (Activation)          (None, 7, 7, 2048)   0           post_bn[0][0]             
    avg_pool (GlobalAveragePooling2 (None, 2048)         0           post_relu[0][0]            
    probs (Dense)                   (None, 1000)         2049000     avg_pool[0][0]             
    dropout_34 (Dropout)            (None, 1000)         0           probs[0][0]                 
    dropout_36 (Dropout)            (None, 1000)         0           probs[0][0]               
    dropout_38 (Dropout)            (None, 1000)         0           probs[0][0]                
    dropout_40 (Dropout)            (None, 1000)         0           probs[0][0]                      
    dropout_42 (Dropout)            (None, 1000)         0           probs[0][0]                
    dropout_44 (Dropout)            (None, 1000)         0           probs[0][0]                
    dropout_48 (Dropout)            (None, 1000)         0           probs[0][0]                
    dropout_46 (Dropout)            (None, 1000)         0           probs[0][0]               
    dense_34 (Dense)                (None, 128)          128128      dropout_34[0][0]          
    dense_36 (Dense)                (None, 128)          128128      dropout_36[0][0]          
    dense_38 (Dense)                (None, 128)          128128      dropout_38[0][0]           
    dense_40 (Dense)                (None, 128)          128128      dropout_40[0][0]           
    dense_42 (Dense)                (None, 128)          128128      dropout_42[0][0]         
    dense_44 (Dense)                (None, 128)          128128      dropout_44[0][0]           
    dense_48 (Dense)                (None, 128)          128128      dropout_48[0][0]          
    dense_46 (Dense)                (None, 128)          128128      dropout_46[0][0]          
    gender_output (Dense)           (None, 2)            258         dense_34[0][0]          
    image_quality_output (Dense)    (None, 3)            387         dense_36[0][0]         
    age_output (Dense)              (None, 5)            645         dense_38[0][0]          
    weight_output (Dense)           (None, 4)            516         dense_40[0][0]         
    bag_output (Dense)              (None, 3)            387         dense_42[0][0]       
    footwear_output (Dense)         (None, 3)            387         dense_44[0][0]     
    pose_output (Dense)             (None, 3)            387         dense_48[0][0]         
    emotion_output (Dense)          (None, 4)            516         dense_46[0][0]                   
==================================================================================================
Total params: 26,642,307</br>
Trainable params: 26,596,867</br>
Non-trainable params: 45,440</br>
## LOGS
/usr/local/lib/python3.6/dist-packages/keras_preprocessing/image/image_data_generator.py:336: UserWarning: This ImageDataGenerator specifies `zca_whitening`, which overrides setting of `featurewise_center`.
  warnings.warn('This ImageDataGenerator specifies '
Epoch 1/25
  2/312 [..............................] - ETA: 35:14 - loss: 9.4664 - gender_output_loss: 0.6932 - image_quality_output_loss: 1.0994 - age_output_loss: 1.6091 - weight_output_loss: 1.3859 - bag_output_loss: 1.0987 - footwear_output_loss: 1.0977 - pose_output_loss: 1.0976 - emotion_output_loss: 1.3848 - gender_output_acc: 0.4062 - image_quality_output_acc: 0.1406 - age_output_acc: 0.3281 - weight_output_acc: 0.2812 - bag_output_acc: 0.2500 - footwear_output_acc: 0.5156 - pose_output_acc: 0.6094 - emotion_output_acc: 0.7031  /usr/local/lib/python3.6/dist-packages/keras/callbacks.py:95: RuntimeWarning: Method (on_train_batch_end) is slow compared to the batch update (0.484488). Check your callbacks.
  % (hook_name, delta_t_median), RuntimeWarning)
312/312 [==============================] - 173s 556ms/step - loss: 8.4368 - gender_output_loss: 0.6860 - image_quality_output_loss: 1.0190 - age_output_loss: 1.5011 - weight_output_loss: 1.1359 - bag_output_loss: 0.9800 - footwear_output_loss: 1.0562 - pose_output_loss: 0.9818 - emotion_output_loss: 1.0767 - gender_output_acc: 0.5673 - image_quality_output_acc: 0.5452 - age_output_acc: 0.4065 - weight_output_acc: 0.6185 - bag_output_acc: 0.5538 - footwear_output_acc: 0.4462 - pose_output_acc: 0.6187 - emotion_output_acc: 0.7159 - val_loss: 8.0088 - val_gender_output_loss: 0.6849 - val_image_quality_output_loss: 0.9928 - val_age_output_loss: 1.4529 - val_weight_output_loss: 0.9850 - val_bag_output_loss: 0.9444 - val_footwear_output_loss: 1.0468 - val_pose_output_loss: 0.9233 - val_emotion_output_loss: 0.9787 - val_gender_output_acc: 0.5641 - val_image_quality_output_acc: 0.5536 - val_age_output_acc: 0.3667 - val_weight_output_acc: 0.6443 - val_bag_output_acc: 0.5464 - val_footwear_output_acc: 0.3719 - val_pose_output_acc: 0.6188 - val_emotion_output_acc: 0.6807

Epoch 00001: val_loss improved from inf to 8.00876, saving model to /content/drive/My Drive/Colab Notebooks/weights.01-8.01.hdf5
Epoch 2/25
312/312 [==============================] - 158s 507ms/step - loss: 7.8436 - gender_output_loss: 0.6874 - image_quality_output_loss: 0.9857 - age_output_loss: 1.4247 - weight_output_loss: 0.9786 - bag_output_loss: 0.9097 - footwear_output_loss: 1.0265 - pose_output_loss: 0.9332 - emotion_output_loss: 0.8977 - gender_output_acc: 0.5584 - image_quality_output_acc: 0.5490 - age_output_acc: 0.4044 - weight_output_acc: 0.6374 - bag_output_acc: 0.5688 - footwear_output_acc: 0.4753 - pose_output_acc: 0.6152 - emotion_output_acc: 0.7181 - val_loss: 8.0015 - val_gender_output_loss: 0.6860 - val_image_quality_output_loss: 0.9849 - val_age_output_loss: 1.4436 - val_weight_output_loss: 0.9889 - val_bag_output_loss: 0.9425 - val_footwear_output_loss: 1.0653 - val_pose_output_loss: 0.9318 - val_emotion_output_loss: 0.9584 - val_gender_output_acc: 0.5604 - val_image_quality_output_acc: 0.5547 - val_age_output_acc: 0.3682 - val_weight_output_acc: 0.6380 - val_bag_output_acc: 0.5432 - val_footwear_output_acc: 0.3693 - val_pose_output_acc: 0.6109 - val_emotion_output_acc: 0.6875

Epoch 00002: val_loss improved from 8.00876 to 8.00146, saving model to /content/drive/My Drive/Colab Notebooks/weights.02-8.00.hdf5
Epoch 3/25
312/312 [==============================] - 158s 507ms/step - loss: 7.8437 - gender_output_loss: 0.6866 - image_quality_output_loss: 0.9861 - age_output_loss: 1.4350 - weight_output_loss: 0.9882 - bag_output_loss: 0.9163 - footwear_output_loss: 0.9985 - pose_output_loss: 0.9323 - emotion_output_loss: 0.9007 - gender_output_acc: 0.5635 - image_quality_output_acc: 0.5523 - age_output_acc: 0.3985 - weight_output_acc: 0.6344 - bag_output_acc: 0.5691 - footwear_output_acc: 0.5198 - pose_output_acc: 0.6165 - emotion_output_acc: 0.7165 - val_loss: 8.5366 - val_gender_output_loss: 0.6860 - val_image_quality_output_loss: 0.9869 - val_age_output_loss: 1.4561 - val_weight_output_loss: 1.0056 - val_bag_output_loss: 0.9272 - val_footwear_output_loss: 1.5801 - val_pose_output_loss: 0.9316 - val_emotion_output_loss: 0.9631 - val_gender_output_acc: 0.5672 - val_image_quality_output_acc: 0.5557 - val_age_output_acc: 0.3641 - val_weight_output_acc: 0.6391 - val_bag_output_acc: 0.5547 - val_footwear_output_acc: 0.3672 - val_pose_output_acc: 0.6125 - val_emotion_output_acc: 0.6870

Epoch 00003: val_loss did not improve from 8.00146
Epoch 4/25
312/312 [==============================] - 159s 511ms/step - loss: 7.8432 - gender_output_loss: 0.6871 - image_quality_output_loss: 0.9803 - age_output_loss: 1.4252 - weight_output_loss: 0.9977 - bag_output_loss: 0.9193 - footwear_output_loss: 1.0022 - pose_output_loss: 0.9222 - emotion_output_loss: 0.9091 - gender_output_acc: 0.5566 - image_quality_output_acc: 0.5574 - age_output_acc: 0.4068 - weight_output_acc: 0.6314 - bag_output_acc: 0.5617 - footwear_output_acc: 0.5188 - pose_output_acc: 0.6241 - emotion_output_acc: 0.7131 - val_loss: 7.9505 - val_gender_output_loss: 0.6861 - val_image_quality_output_loss: 0.9872 - val_age_output_loss: 1.4446 - val_weight_output_loss: 0.9796 - val_bag_output_loss: 0.9355 - val_footwear_output_loss: 1.0050 - val_pose_output_loss: 0.9296 - val_emotion_output_loss: 0.9829 - val_gender_output_acc: 0.5594 - val_image_quality_output_acc: 0.5495 - val_age_output_acc: 0.3724 - val_weight_output_acc: 0.6443 - val_bag_output_acc: 0.5469 - val_footwear_output_acc: 0.5224 - val_pose_output_acc: 0.6156 - val_emotion_output_acc: 0.6875

Epoch 00004: val_loss improved from 8.00146 to 7.95048, saving model to /content/drive/My Drive/Colab Notebooks/weights.04-7.95.hdf5
Epoch 5/25
311/312 [============================>.] - ETA: 0s - loss: 7.8300 - gender_output_loss: 0.6816 - image_quality_output_loss: 0.9820 - age_output_loss: 1.4267 - weight_output_loss: 0.9834 - bag_output_loss: 0.9211 - footwear_output_loss: 0.9986 - pose_output_loss: 0.9349 - emotion_output_loss: 0.9015 - gender_output_acc: 0.5670 - image_quality_output_acc: 0.5547 - age_output_acc: 0.4002 - weight_output_acc: 0.6330 - bag_output_acc: 0.5631 - footwear_output_acc: 0.5194 - pose_output_acc: 0.6144 - emotion_output_acc: 0.7160
Epoch 00004: val_loss improved from 8.00146 to 7.95048, saving model to /content/drive/My Drive/Colab Notebooks/weights.04-7.95.hdf5
312/312 [==============================] - 159s 508ms/step - loss: 7.8301 - gender_output_loss: 0.6816 - image_quality_output_loss: 0.9820 - age_output_loss: 1.4266 - weight_output_loss: 0.9831 - bag_output_loss: 0.9213 - footwear_output_loss: 0.9990 - pose_output_loss: 0.9352 - emotion_output_loss: 0.9013 - gender_output_acc: 0.5668 - image_quality_output_acc: 0.5549 - age_output_acc: 0.4002 - weight_output_acc: 0.6333 - bag_output_acc: 0.5624 - footwear_output_acc: 0.5192 - pose_output_acc: 0.6142 - emotion_output_acc: 0.7160 - val_loss: 8.0195 - val_gender_output_loss: 0.6887 - val_image_quality_output_loss: 0.9855 - val_age_output_loss: 1.4504 - val_weight_output_loss: 0.9739 - val_bag_output_loss: 0.9430 - val_footwear_output_loss: 1.0611 - val_pose_output_loss: 0.9289 - val_emotion_output_loss: 0.9879 - val_gender_output_acc: 0.5823 - val_image_quality_output_acc: 0.5521 - val_age_output_acc: 0.3708 - val_weight_output_acc: 0.6432 - val_bag_output_acc: 0.5479 - val_footwear_output_acc: 0.4651 - val_pose_output_acc: 0.6141 - val_emotion_output_acc: 0.6844

Epoch 00005: val_loss did not improve from 7.95048
Epoch 6/25
311/312 [============================>.] - ETA: 0s - loss: 7.7770 - gender_output_loss: 0.6731 - image_quality_output_loss: 0.9867 - age_output_loss: 1.4201 - weight_output_loss: 0.9830 - bag_output_loss: 0.9088 - footwear_output_loss: 0.9792 - pose_output_loss: 0.9288 - emotion_output_loss: 0.8972 - gender_output_acc: 0.5817 - image_quality_output_acc: 0.5476 - age_output_acc: 0.4067 - weight_output_acc: 0.6360 - bag_output_acc: 0.5696 - footwear_output_acc: 0.5367 - pose_output_acc: 0.6196 - emotion_output_acc: 0.7191
Epoch 00005: val_loss did not improve from 7.95048
Epoch 6/25
312/312 [==============================] - 159s 510ms/step - loss: 7.7759 - gender_output_loss: 0.6731 - image_quality_output_loss: 0.9864 - age_output_loss: 1.4193 - weight_output_loss: 0.9829 - bag_output_loss: 0.9093 - footwear_output_loss: 0.9786 - pose_output_loss: 0.9286 - emotion_output_loss: 0.8976 - gender_output_acc: 0.5818 - image_quality_output_acc: 0.5480 - age_output_acc: 0.4077 - weight_output_acc: 0.6360 - bag_output_acc: 0.5691 - footwear_output_acc: 0.5372 - pose_output_acc: 0.6198 - emotion_output_acc: 0.7190 - val_loss: 7.9217 - val_gender_output_loss: 0.6614 - val_image_quality_output_loss: 0.9791 - val_age_output_loss: 1.4549 - val_weight_output_loss: 0.9903 - val_bag_output_loss: 0.9301 - val_footwear_output_loss: 0.9979 - val_pose_output_loss: 0.9432 - val_emotion_output_loss: 0.9647 - val_gender_output_acc: 0.6141 - val_image_quality_output_acc: 0.5589 - val_age_output_acc: 0.3688 - val_weight_output_acc: 0.6396 - val_bag_output_acc: 0.5458 - val_footwear_output_acc: 0.5198 - val_pose_output_acc: 0.6135 - val_emotion_output_acc: 0.6854

Epoch 00006: val_loss improved from 7.95048 to 7.92167, saving model to /content/drive/My Drive/Colab Notebooks/weights.06-7.92.hdf5
Epoch 7/25
311/312 [============================>.] - ETA: 0s - loss: 7.6831 - gender_output_loss: 0.6517 - image_quality_output_loss: 0.9815 - age_output_loss: 1.4077 - weight_output_loss: 0.9837 - bag_output_loss: 0.9056 - footwear_output_loss: 0.9220 - pose_output_loss: 0.9239 - emotion_output_loss: 0.9070 - gender_output_acc: 0.6098 - image_quality_output_acc: 0.5566 - age_output_acc: 0.4056 - weight_output_acc: 0.6360 - bag_output_acc: 0.5630 - footwear_output_acc: 0.5815 - pose_output_acc: 0.6194 - emotion_output_acc: 0.7136
Epoch 00006: val_loss improved from 7.95048 to 7.92167, saving model to /content/drive/My Drive/Colab Notebooks/weights.06-7.92.hdf5
312/312 [==============================] - 159s 509ms/step - loss: 7.6818 - gender_output_loss: 0.6519 - image_quality_output_loss: 0.9810 - age_output_loss: 1.4073 - weight_output_loss: 0.9834 - bag_output_loss: 0.9054 - footwear_output_loss: 0.9216 - pose_output_loss: 0.9238 - emotion_output_loss: 0.9074 - gender_output_acc: 0.6094 - image_quality_output_acc: 0.5572 - age_output_acc: 0.4058 - weight_output_acc: 0.6361 - bag_output_acc: 0.5635 - footwear_output_acc: 0.5819 - pose_output_acc: 0.6194 - emotion_output_acc: 0.7134 - val_loss: 8.3084 - val_gender_output_loss: 0.6905 - val_image_quality_output_loss: 0.9873 - val_age_output_loss: 1.4381 - val_weight_output_loss: 0.9819 - val_bag_output_loss: 0.9297 - val_footwear_output_loss: 1.3691 - val_pose_output_loss: 0.9431 - val_emotion_output_loss: 0.9687 - val_gender_output_acc: 0.5667 - val_image_quality_output_acc: 0.5542 - val_age_output_acc: 0.3693 - val_weight_output_acc: 0.6406 - val_bag_output_acc: 0.5417 - val_footwear_output_acc: 0.4698 - val_pose_output_acc: 0.6099 - val_emotion_output_acc: 0.6839

Epoch 00007: val_loss did not improve from 7.92167
Epoch 8/25
312/312 [==============================] - 159s 510ms/step - loss: 7.5736 - gender_output_loss: 0.6274 - image_quality_output_loss: 0.9801 - age_output_loss: 1.4079 - weight_output_loss: 0.9789 - bag_output_loss: 0.8931 - footwear_output_loss: 0.8746 - pose_output_loss: 0.9164 - emotion_output_loss: 0.8951 - gender_output_acc: 0.6435 - image_quality_output_acc: 0.5502 - age_output_acc: 0.4023 - weight_output_acc: 0.6350 - bag_output_acc: 0.5715 - footwear_output_acc: 0.6141 - pose_output_acc: 0.6168 - emotion_output_acc: 0.7171 - val_loss: 7.9320 - val_gender_output_loss: 0.6259 - val_image_quality_output_loss: 0.9829 - val_age_output_loss: 1.4255 - val_weight_output_loss: 0.9803 - val_bag_output_loss: 0.9202 - val_footwear_output_loss: 1.0755 - val_pose_output_loss: 0.9448 - val_emotion_output_loss: 0.9770 - val_gender_output_acc: 0.6552 - val_image_quality_output_acc: 0.5536 - val_age_output_acc: 0.3708 - val_weight_output_acc: 0.6438 - val_bag_output_acc: 0.5349 - val_footwear_output_acc: 0.5068 - val_pose_output_acc: 0.6177 - val_emotion_output_acc: 0.6849

Epoch 00008: val_loss did not improve from 7.92167
Epoch 9/25
311/312 [============================>.] - ETA: 0s - loss: 7.4855 - gender_output_loss: 0.6062 - image_quality_output_loss: 0.9754 - age_output_loss: 1.4003 - weight_output_loss: 0.9755 - bag_output_loss: 0.8828 - footwear_output_loss: 0.8440 - pose_output_loss: 0.9080 - emotion_output_loss: 0.8933 - gender_output_acc: 0.6733 - image_quality_output_acc: 0.5535 - age_output_acc: 0.4027 - weight_output_acc: 0.6309 - bag_output_acc: 0.5816 - footwear_output_acc: 0.6309 - pose_output_acc: 0.6178 - emotion_output_acc: 0.7157
Epoch 00008: val_loss did not improve from 7.92167
Epoch 9/25
312/312 [==============================] - 160s 512ms/step - loss: 7.4849 - gender_output_loss: 0.6062 - image_quality_output_loss: 0.9754 - age_output_loss: 1.4005 - weight_output_loss: 0.9760 - bag_output_loss: 0.8826 - footwear_output_loss: 0.8437 - pose_output_loss: 0.9080 - emotion_output_loss: 0.8926 - gender_output_acc: 0.6737 - image_quality_output_acc: 0.5536 - age_output_acc: 0.4024 - weight_output_acc: 0.6303 - bag_output_acc: 0.5813 - footwear_output_acc: 0.6313 - pose_output_acc: 0.6180 - emotion_output_acc: 0.7160 - val_loss: 7.6259 - val_gender_output_loss: 0.5907 - val_image_quality_output_loss: 0.9729 - val_age_output_loss: 1.4169 - val_weight_output_loss: 0.9723 - val_bag_output_loss: 0.9135 - val_footwear_output_loss: 0.8998 - val_pose_output_loss: 0.9087 - val_emotion_output_loss: 0.9510 - val_gender_output_acc: 0.6771 - val_image_quality_output_acc: 0.5557 - val_age_output_acc: 0.3776 - val_weight_output_acc: 0.6396 - val_bag_output_acc: 0.5411 - val_footwear_output_acc: 0.6036 - val_pose_output_acc: 0.6115 - val_emotion_output_acc: 0.6885

Epoch 00009: val_loss improved from 7.92167 to 7.62586, saving model to /content/drive/My Drive/Colab Notebooks/weights.09-7.63.hdf5
Epoch 10/25
311/312 [============================>.] - ETA: 0s - loss: 7.4222 - gender_output_loss: 0.5768 - image_quality_output_loss: 0.9706 - age_output_loss: 1.3969 - weight_output_loss: 0.9672 - bag_output_loss: 0.8804 - footwear_output_loss: 0.8372 - pose_output_loss: 0.9017 - emotion_output_loss: 0.8914 - gender_output_acc: 0.6946 - image_quality_output_acc: 0.5556 - age_output_acc: 0.4010 - weight_output_acc: 0.6383 - bag_output_acc: 0.5851 - footwear_output_acc: 0.6326 - pose_output_acc: 0.6192 - emotion_output_acc: 0.7164
Epoch 00009: val_loss improved from 7.92167 to 7.62586, saving model to /content/drive/My Drive/Colab Notebooks/weights.09-7.63.hdf5
312/312 [==============================] - 159s 510ms/step - loss: 7.4225 - gender_output_loss: 0.5772 - image_quality_output_loss: 0.9707 - age_output_loss: 1.3967 - weight_output_loss: 0.9667 - bag_output_loss: 0.8809 - footwear_output_loss: 0.8373 - pose_output_loss: 0.9018 - emotion_output_loss: 0.8913 - gender_output_acc: 0.6944 - image_quality_output_acc: 0.5552 - age_output_acc: 0.4012 - weight_output_acc: 0.6385 - bag_output_acc: 0.5846 - footwear_output_acc: 0.6325 - pose_output_acc: 0.6192 - emotion_output_acc: 0.7164 - val_loss: 7.6236 - val_gender_output_loss: 0.6125 - val_image_quality_output_loss: 0.9784 - val_age_output_loss: 1.4249 - val_weight_output_loss: 0.9633 - val_bag_output_loss: 0.9160 - val_footwear_output_loss: 0.8587 - val_pose_output_loss: 0.8994 - val_emotion_output_loss: 0.9705 - val_gender_output_acc: 0.6682 - val_image_quality_output_acc: 0.5365 - val_age_output_acc: 0.3682 - val_weight_output_acc: 0.6438 - val_bag_output_acc: 0.5411 - val_footwear_output_acc: 0.6172 - val_pose_output_acc: 0.6156 - val_emotion_output_acc: 0.6839

Epoch 00010: val_loss improved from 7.62586 to 7.62361, saving model to /content/drive/My Drive/Colab Notebooks/weights.10-7.62.hdf5
Epoch 11/25
311/312 [============================>.] - ETA: 0s - loss: 7.3530 - gender_output_loss: 0.5616 - image_quality_output_loss: 0.9785 - age_output_loss: 1.3896 - weight_output_loss: 0.9727 - bag_output_loss: 0.8633 - footwear_output_loss: 0.8013 - pose_output_loss: 0.8911 - emotion_output_loss: 0.8949 - gender_output_acc: 0.7074 - image_quality_output_acc: 0.5512 - age_output_acc: 0.4067 - weight_output_acc: 0.6316 - bag_output_acc: 0.5988 - footwear_output_acc: 0.6490 - pose_output_acc: 0.6150 - emotion_output_acc: 0.7136
312/312 [==============================] - 158s 508ms/step - loss: 7.3540 - gender_output_loss: 0.5625 - image_quality_output_loss: 0.9788 - age_output_loss: 1.3899 - weight_output_loss: 0.9724 - bag_output_loss: 0.8635 - footwear_output_loss: 0.8011 - pose_output_loss: 0.8909 - emotion_output_loss: 0.8948 - gender_output_acc: 0.7070 - image_quality_output_acc: 0.5511 - age_output_acc: 0.4067 - weight_output_acc: 0.6318 - bag_output_acc: 0.5986 - footwear_output_acc: 0.6491 - pose_output_acc: 0.6152 - emotion_output_acc: 0.7136 - val_loss: 7.5632 - val_gender_output_loss: 0.5851 - val_image_quality_output_loss: 0.9734 - val_age_output_loss: 1.4315 - val_weight_output_loss: 0.9720 - val_bag_output_loss: 0.9014 - val_footwear_output_loss: 0.8737 - val_pose_output_loss: 0.8710 - val_emotion_output_loss: 0.9551 - val_gender_output_acc: 0.7005 - val_image_quality_output_acc: 0.5563 - val_age_output_acc: 0.3672 - val_weight_output_acc: 0.6396 - val_bag_output_acc: 0.5818 - val_footwear_output_acc: 0.6177 - val_pose_output_acc: 0.6172 - val_emotion_output_acc: 0.6849

Epoch 00011: val_loss improved from 7.62361 to 7.56320, saving model to /content/drive/My Drive/Colab Notebooks/weights.11-7.56.hdf5
Epoch 12/25

312/312 [==============================] - 158s 508ms/step - loss: 7.2859 - gender_output_loss: 0.5351 - image_quality_output_loss: 0.9700 - age_output_loss: 1.3905 - weight_output_loss: 0.9620 - bag_output_loss: 0.8626 - footwear_output_loss: 0.8112 - pose_output_loss: 0.8688 - emotion_output_loss: 0.8857 - gender_output_acc: 0.7266 - image_quality_output_acc: 0.5538 - age_output_acc: 0.4008 - weight_output_acc: 0.6374 - bag_output_acc: 0.6045 - footwear_output_acc: 0.6424 - pose_output_acc: 0.6225 - emotion_output_acc: 0.7167 - val_loss: 7.4884 - val_gender_output_loss: 0.5823 - val_image_quality_output_loss: 0.9701 - val_age_output_loss: 1.4198 - val_weight_output_loss: 0.9704 - val_bag_output_loss: 0.8926 - val_footwear_output_loss: 0.8331 - val_pose_output_loss: 0.8684 - val_emotion_output_loss: 0.9517 - val_gender_output_acc: 0.6880 - val_image_quality_output_acc: 0.5578 - val_age_output_acc: 0.3714 - val_weight_output_acc: 0.6401 - val_bag_output_acc: 0.5776 - val_footwear_output_acc: 0.6276 - val_pose_output_acc: 0.6141 - val_emotion_output_acc: 0.6870

Epoch 00012: val_loss improved from 7.56320 to 7.48836, saving model to /content/drive/My Drive/Colab Notebooks/weights.12-7.49.hdf5
Epoch 13/25
312/312 [==============================] - 159s 509ms/step - loss: 7.2070 - gender_output_loss: 0.5248 - image_quality_output_loss: 0.9733 - age_output_loss: 1.3748 - weight_output_loss: 0.9582 - bag_output_loss: 0.8580 - footwear_output_loss: 0.7799 - pose_output_loss: 0.8617 - emotion_output_loss: 0.8763 - gender_output_acc: 0.7346 - image_quality_output_acc: 0.5484 - age_output_acc: 0.4128 - weight_output_acc: 0.6347 - bag_output_acc: 0.6032 - footwear_output_acc: 0.6607 - pose_output_acc: 0.6151 - emotion_output_acc: 0.7190 - val_loss: 7.4406 - val_gender_output_loss: 0.5491 - val_image_quality_output_loss: 0.9677 - val_age_output_loss: 1.4168 - val_weight_output_loss: 0.9759 - val_bag_output_loss: 0.8856 - val_footwear_output_loss: 0.8364 - val_pose_output_loss: 0.8640 - val_emotion_output_loss: 0.9451 - val_gender_output_acc: 0.7109 - val_image_quality_output_acc: 0.5604 - val_age_output_acc: 0.3677 - val_weight_output_acc: 0.6375 - val_bag_output_acc: 0.5781 - val_footwear_output_acc: 0.6276 - val_pose_output_acc: 0.6078 - val_emotion_output_acc: 0.6875

Epoch 00013: val_loss improved from 7.48836 to 7.44056, saving model to /content/drive/My Drive/Colab Notebooks/weights.13-7.44.hdf5
Epoch 14/25
311/312 [============================>.] - ETA: 0s - loss: 7.2025 - gender_output_loss: 0.5191 - image_quality_output_loss: 0.9654 - age_output_loss: 1.3901 - weight_output_loss: 0.9680 - bag_output_loss: 0.8457 - footwear_output_loss: 0.7824 - pose_output_loss: 0.8449 - emotion_output_loss: 0.8871 - gender_output_acc: 0.7409 - image_quality_output_acc: 0.5580 - age_output_acc: 0.4040 - weight_output_acc: 0.6313 - bag_output_acc: 0.6198 - footwear_output_acc: 0.6611 - pose_output_acc: 0.6255 - emotion_output_acc: 0.7147
Epoch 00013: val_loss improved from 7.48836 to 7.44056, saving model to /content/drive/My Drive/Colab Notebooks/weights.13-7.44.hdf5
312/312 [==============================] - 159s 508ms/step - loss: 7.2026 - gender_output_loss: 0.5189 - image_quality_output_loss: 0.9655 - age_output_loss: 1.3904 - weight_output_loss: 0.9680 - bag_output_loss: 0.8462 - footwear_output_loss: 0.7822 - pose_output_loss: 0.8448 - emotion_output_loss: 0.8867 - gender_output_acc: 0.7408 - image_quality_output_acc: 0.5578 - age_output_acc: 0.4035 - weight_output_acc: 0.6316 - bag_output_acc: 0.6198 - footwear_output_acc: 0.6609 - pose_output_acc: 0.6255 - emotion_output_acc: 0.7148 - val_loss: 7.6145 - val_gender_output_loss: 0.5580 - val_image_quality_output_loss: 0.9804 - val_age_output_loss: 1.4211 - val_weight_output_loss: 0.9651 - val_bag_output_loss: 0.9000 - val_footwear_output_loss: 0.9878 - val_pose_output_loss: 0.8534 - val_emotion_output_loss: 0.9487 - val_gender_output_acc: 0.7063 - val_image_quality_output_acc: 0.5490 - val_age_output_acc: 0.3688 - val_weight_output_acc: 0.6438 - val_bag_output_acc: 0.5792 - val_footwear_output_acc: 0.5615 - val_pose_output_acc: 0.6276 - val_emotion_output_acc: 0.6854

Epoch 00014: val_loss did not improve from 7.44056
Epoch 15/25
311/312 [============================>.] - ETA: 0s - loss: 7.2264 - gender_output_loss: 0.5223 - image_quality_output_loss: 0.9699 - age_output_loss: 1.3807 - weight_output_loss: 0.9588 - bag_output_loss: 0.8649 - footwear_output_loss: 0.7912 - pose_output_loss: 0.8533 - emotion_output_loss: 0.8854 - gender_output_acc: 0.7364 - image_quality_output_acc: 0.5547 - age_output_acc: 0.4066 - weight_output_acc: 0.6362 - bag_output_acc: 0.6028 - footwear_output_acc: 0.6529 - pose_output_acc: 0.6283 - emotion_output_acc: 0.7155
Epoch 00014: val_loss did not improve from 7.44056
Epoch 15/25
312/312 [==============================] - 159s 510ms/step - loss: 7.2250 - gender_output_loss: 0.5220 - image_quality_output_loss: 0.9700 - age_output_loss: 1.3810 - weight_output_loss: 0.9582 - bag_output_loss: 0.8647 - footwear_output_loss: 0.7911 - pose_output_loss: 0.8532 - emotion_output_loss: 0.8849 - gender_output_acc: 0.7369 - image_quality_output_acc: 0.5547 - age_output_acc: 0.4064 - weight_output_acc: 0.6366 - bag_output_acc: 0.6030 - footwear_output_acc: 0.6530 - pose_output_acc: 0.6287 - emotion_output_acc: 0.7157 - val_loss: 7.7084 - val_gender_output_loss: 0.5596 - val_image_quality_output_loss: 0.9777 - val_age_output_loss: 1.4125 - val_weight_output_loss: 0.9709 - val_bag_output_loss: 0.8903 - val_footwear_output_loss: 1.0941 - val_pose_output_loss: 0.8568 - val_emotion_output_loss: 0.9464 - val_gender_output_acc: 0.7052 - val_image_quality_output_acc: 0.5578 - val_age_output_acc: 0.3667 - val_weight_output_acc: 0.6417 - val_bag_output_acc: 0.5786 - val_footwear_output_acc: 0.5125 - val_pose_output_acc: 0.6391 - val_emotion_output_acc: 0.6854

Epoch 00015: val_loss did not improve from 7.44056
Epoch 16/25
311/312 [============================>.] - ETA: 0s - loss: 7.2174 - gender_output_loss: 0.5301 - image_quality_output_loss: 0.9695 - age_output_loss: 1.3857 - weight_output_loss: 0.9635 - bag_output_loss: 0.8588 - footwear_output_loss: 0.7928 - pose_output_loss: 0.8358 - emotion_output_loss: 0.8812 - gender_output_acc: 0.7330 - image_quality_output_acc: 0.5560 - age_output_acc: 0.4079 - weight_output_acc: 0.6358 - bag_output_acc: 0.6093 - footwear_output_acc: 0.6516 - pose_output_acc: 0.6365 - emotion_output_acc: 0.7169
Epoch 00015: val_loss did not improve from 7.44056
Epoch 16/25
312/312 [==============================] - 158s 507ms/step - loss: 7.2185 - gender_output_loss: 0.5302 - image_quality_output_loss: 0.9699 - age_output_loss: 1.3857 - weight_output_loss: 0.9634 - bag_output_loss: 0.8586 - footwear_output_loss: 0.7932 - pose_output_loss: 0.8359 - emotion_output_loss: 0.8816 - gender_output_acc: 0.7330 - image_quality_output_acc: 0.5558 - age_output_acc: 0.4080 - weight_output_acc: 0.6358 - bag_output_acc: 0.6093 - footwear_output_acc: 0.6513 - pose_output_acc: 0.6360 - emotion_output_acc: 0.7168 - val_loss: 7.4096 - val_gender_output_loss: 0.5519 - val_image_quality_output_loss: 0.9699 - val_age_output_loss: 1.4092 - val_weight_output_loss: 0.9702 - val_bag_output_loss: 0.9046 - val_footwear_output_loss: 0.8330 - val_pose_output_loss: 0.8327 - val_emotion_output_loss: 0.9381 - val_gender_output_acc: 0.7219 - val_image_quality_output_acc: 0.5578 - val_age_output_acc: 0.3703 - val_weight_output_acc: 0.6375 - val_bag_output_acc: 0.5740 - val_footwear_output_acc: 0.6276 - val_pose_output_acc: 0.6443 - val_emotion_output_acc: 0.6906

Epoch 00016: val_loss improved from 7.44056 to 7.40959, saving model to /content/drive/My Drive/Colab Notebooks/weights.16-7.41.hdf5
Epoch 17/25
311/312 [============================>.] - ETA: 0s - loss: 7.2440 - gender_output_loss: 0.5344 - image_quality_output_loss: 0.9782 - age_output_loss: 1.3834 - weight_output_loss: 0.9585 - bag_output_loss: 0.8698 - footwear_output_loss: 0.8072 - pose_output_loss: 0.8249 - emotion_output_loss: 0.8876 - gender_output_acc: 0.7308 - image_quality_output_acc: 0.5485 - age_output_acc: 0.4123 - weight_output_acc: 0.6389 - bag_output_acc: 0.5991 - footwear_output_acc: 0.6447 - pose_output_acc: 0.6493 - emotion_output_acc: 0.7145
Epoch 00016: val_loss improved from 7.44056 to 7.40959, saving model to /content/drive/My Drive/Colab Notebooks/weights.16-7.41.hdf5
312/312 [==============================] - 158s 508ms/step - loss: 7.2426 - gender_output_loss: 0.5344 - image_quality_output_loss: 0.9782 - age_output_loss: 1.3825 - weight_output_loss: 0.9586 - bag_output_loss: 0.8697 - footwear_output_loss: 0.8072 - pose_output_loss: 0.8246 - emotion_output_loss: 0.8875 - gender_output_acc: 0.7309 - image_quality_output_acc: 0.5486 - age_output_acc: 0.4132 - weight_output_acc: 0.6388 - bag_output_acc: 0.5990 - footwear_output_acc: 0.6446 - pose_output_acc: 0.6494 - emotion_output_acc: 0.7145 - val_loss: 7.4550 - val_gender_output_loss: 0.5716 - val_image_quality_output_loss: 0.9734 - val_age_output_loss: 1.4262 - val_weight_output_loss: 0.9685 - val_bag_output_loss: 0.9027 - val_footwear_output_loss: 0.8150 - val_pose_output_loss: 0.8390 - val_emotion_output_loss: 0.9585 - val_gender_output_acc: 0.6964 - val_image_quality_output_acc: 0.5563 - val_age_output_acc: 0.3755 - val_weight_output_acc: 0.6484 - val_bag_output_acc: 0.5667 - val_footwear_output_acc: 0.6375 - val_pose_output_acc: 0.6500 - val_emotion_output_acc: 0.6870

Epoch 00017: val_loss did not improve from 7.40959
Epoch 18/25
312/312 [==============================] - 158s 508ms/step - loss: 7.2181 - gender_output_loss: 0.5255 - image_quality_output_loss: 0.9679 - age_output_loss: 1.3961 - weight_output_loss: 0.9725 - bag_output_loss: 0.8641 - footwear_output_loss: 0.8023 - pose_output_loss: 0.8058 - emotion_output_loss: 0.8839 - gender_output_acc: 0.7353 - image_quality_output_acc: 0.5560 - age_output_acc: 0.4001 - weight_output_acc: 0.6325 - bag_output_acc: 0.5970 - footwear_output_acc: 0.6504 - pose_output_acc: 0.6529 - emotion_output_acc: 0.7157 - val_loss: 7.6323 - val_gender_output_loss: 0.5962 - val_image_quality_output_loss: 0.9749 - val_age_output_loss: 1.4287 - val_weight_output_loss: 0.9770 - val_bag_output_loss: 0.9064 - val_footwear_output_loss: 0.8814 - val_pose_output_loss: 0.9061 - val_emotion_output_loss: 0.9616 - val_gender_output_acc: 0.6875 - val_image_quality_output_acc: 0.5531 - val_age_output_acc: 0.3688 - val_weight_output_acc: 0.6401 - val_bag_output_acc: 0.5573 - val_footwear_output_acc: 0.6010 - val_pose_output_acc: 0.5839 - val_emotion_output_acc: 0.6859

Epoch 00018: val_loss did not improve from 7.40959
Epoch 19/25
312/312 [==============================] - 159s 510ms/step - loss: 7.2043 - gender_output_loss: 0.5348 - image_quality_output_loss: 0.9752 - age_output_loss: 1.3909 - weight_output_loss: 0.9704 - bag_output_loss: 0.8714 - footwear_output_loss: 0.8095 - pose_output_loss: 0.7783 - emotion_output_loss: 0.8737 - gender_output_acc: 0.7269 - image_quality_output_acc: 0.5501 - age_output_acc: 0.4085 - weight_output_acc: 0.6327 - bag_output_acc: 0.6023 - footwear_output_acc: 0.6446 - pose_output_acc: 0.6720 - emotion_output_acc: 0.7219 - val_loss: 7.7675 - val_gender_output_loss: 0.6032 - val_image_quality_output_loss: 0.9832 - val_age_output_loss: 1.4277 - val_weight_output_loss: 0.9869 - val_bag_output_loss: 0.9127 - val_footwear_output_loss: 0.8674 - val_pose_output_loss: 0.9844 - val_emotion_output_loss: 1.0020 - val_gender_output_acc: 0.6818 - val_image_quality_output_acc: 0.5505 - val_age_output_acc: 0.3682 - val_weight_output_acc: 0.6427 - val_bag_output_acc: 0.5719 - val_footwear_output_acc: 0.6099 - val_pose_output_acc: 0.5193 - val_emotion_output_acc: 0.6859

Epoch 00019: val_loss did not improve from 7.40959
Epoch 20/25
311/312 [============================>.] - ETA: 0s - loss: 7.1374 - gender_output_loss: 0.5214 - image_quality_output_loss: 0.9650 - age_output_loss: 1.3901 - weight_output_loss: 0.9677 - bag_output_loss: 0.8626 - footwear_output_loss: 0.8036 - pose_output_loss: 0.7419 - emotion_output_loss: 0.8851 - gender_output_acc: 0.7380 - image_quality_output_acc: 0.5627 - age_output_acc: 0.4045 - weight_output_acc: 0.6307 - bag_output_acc: 0.6029 - footwear_output_acc: 0.6456 - pose_output_acc: 0.6828 - emotion_output_acc: 0.7121
Epoch 00019: val_loss did not improve from 7.40959
Epoch 20/25
312/312 [==============================] - 159s 509ms/step - loss: 7.1352 - gender_output_loss: 0.5209 - image_quality_output_loss: 0.9653 - age_output_loss: 1.3899 - weight_output_loss: 0.9677 - bag_output_loss: 0.8622 - footwear_output_loss: 0.8032 - pose_output_loss: 0.7413 - emotion_output_loss: 0.8847 - gender_output_acc: 0.7386 - image_quality_output_acc: 0.5627 - age_output_acc: 0.4042 - weight_output_acc: 0.6308 - bag_output_acc: 0.6035 - footwear_output_acc: 0.6459 - pose_output_acc: 0.6832 - emotion_output_acc: 0.7123 - val_loss: 8.4888 - val_gender_output_loss: 0.8186 - val_image_quality_output_loss: 0.9829 - val_age_output_loss: 1.4605 - val_weight_output_loss: 1.0059 - val_bag_output_loss: 1.0485 - val_footwear_output_loss: 1.3143 - val_pose_output_loss: 0.8694 - val_emotion_output_loss: 0.9887 - val_gender_output_acc: 0.6349 - val_image_quality_output_acc: 0.5542 - val_age_output_acc: 0.3641 - val_weight_output_acc: 0.6182 - val_bag_output_acc: 0.5469 - val_footwear_output_acc: 0.5146 - val_pose_output_acc: 0.6208 - val_emotion_output_acc: 0.6802

Epoch 00020: val_loss did not improve from 7.40959
Epoch 21/25
312/312 [==============================] - 159s 509ms/step - loss: 7.0405 - gender_output_loss: 0.4987 - image_quality_output_loss: 0.9754 - age_output_loss: 1.3814 - weight_output_loss: 0.9581 - bag_output_loss: 0.8560 - footwear_output_loss: 0.7892 - pose_output_loss: 0.7013 - emotion_output_loss: 0.8803 - gender_output_acc: 0.7606 - image_quality_output_acc: 0.5463 - age_output_acc: 0.4088 - weight_output_acc: 0.6363 - bag_output_acc: 0.6069 - footwear_output_acc: 0.6579 - pose_output_acc: 0.7059 - emotion_output_acc: 0.7122 - val_loss: 7.6742 - val_gender_output_loss: 0.5531 - val_image_quality_output_loss: 0.9820 - val_age_output_loss: 1.4118 - val_weight_output_loss: 0.9627 - val_bag_output_loss: 0.9046 - val_footwear_output_loss: 1.1716 - val_pose_output_loss: 0.7520 - val_emotion_output_loss: 0.9366 - val_gender_output_acc: 0.7156 - val_image_quality_output_acc: 0.5505 - val_age_output_acc: 0.3854 - val_weight_output_acc: 0.6469 - val_bag_output_acc: 0.5729 - val_footwear_output_acc: 0.4646 - val_pose_output_acc: 0.6745 - val_emotion_output_acc: 0.6865

Epoch 00021: val_loss did not improve from 7.40959
Epoch 22/25
312/312 [==============================] - 159s 509ms/step - loss: 6.8771 - gender_output_loss: 0.4583 - image_quality_output_loss: 0.9715 - age_output_loss: 1.3704 - weight_output_loss: 0.9539 - bag_output_loss: 0.8467 - footwear_output_loss: 0.7750 - pose_output_loss: 0.6359 - emotion_output_loss: 0.8654 - gender_output_acc: 0.7825 - image_quality_output_acc: 0.5507 - age_output_acc: 0.4079 - weight_output_acc: 0.6343 - bag_output_acc: 0.6172 - footwear_output_acc: 0.6679 - pose_output_acc: 0.7330 - emotion_output_acc: 0.7188 - val_loss: 7.2026 - val_gender_output_loss: 0.5064 - val_image_quality_output_loss: 0.9685 - val_age_output_loss: 1.4050 - val_weight_output_loss: 0.9497 - val_bag_output_loss: 0.8977 - val_footwear_output_loss: 0.8378 - val_pose_output_loss: 0.7090 - val_emotion_output_loss: 0.9285 - val_gender_output_acc: 0.7568 - val_image_quality_output_acc: 0.5536 - val_age_output_acc: 0.3703 - val_weight_output_acc: 0.6427 - val_bag_output_acc: 0.5875 - val_footwear_output_acc: 0.6078 - val_pose_output_acc: 0.7073 - val_emotion_output_acc: 0.6859

Epoch 00022: val_loss improved from 7.40959 to 7.20257, saving model to /content/drive/My Drive/Colab Notebooks/weights.22-7.20.hdf5
Epoch 23/25

312/312 [==============================] - 158s 506ms/step - loss: 6.7370 - gender_output_loss: 0.4243 - image_quality_output_loss: 0.9633 - age_output_loss: 1.3573 - weight_output_loss: 0.9464 - bag_output_loss: 0.8380 - footwear_output_loss: 0.7529 - pose_output_loss: 0.5922 - emotion_output_loss: 0.8625 - gender_output_acc: 0.8043 - image_quality_output_acc: 0.5589 - age_output_acc: 0.4102 - weight_output_acc: 0.6345 - bag_output_acc: 0.6305 - footwear_output_acc: 0.6733 - pose_output_acc: 0.7583 - emotion_output_acc: 0.7159 - val_loss: 7.1648 - val_gender_output_loss: 0.5447 - val_image_quality_output_loss: 0.9669 - val_age_output_loss: 1.4133 - val_weight_output_loss: 0.9434 - val_bag_output_loss: 0.8864 - val_footwear_output_loss: 0.8158 - val_pose_output_loss: 0.6709 - val_emotion_output_loss: 0.9235 - val_gender_output_acc: 0.7349 - val_image_quality_output_acc: 0.5578 - val_age_output_acc: 0.3792 - val_weight_output_acc: 0.6474 - val_bag_output_acc: 0.5776 - val_footwear_output_acc: 0.6339 - val_pose_output_acc: 0.7250 - val_emotion_output_acc: 0.6865

Epoch 00023: val_loss improved from 7.20257 to 7.16478, saving model to /content/drive/My Drive/Colab Notebooks/weights.23-7.16.hdf5
Epoch 24/25
312/312 [==============================] - 159s 509ms/step - loss: 6.6003 - gender_output_loss: 0.3796 - image_quality_output_loss: 0.9662 - age_output_loss: 1.3550 - weight_output_loss: 0.9374 - bag_output_loss: 0.8256 - footwear_output_loss: 0.7375 - pose_output_loss: 0.5430 - emotion_output_loss: 0.8561 - gender_output_acc: 0.8291 - image_quality_output_acc: 0.5531 - age_output_acc: 0.4125 - weight_output_acc: 0.6339 - bag_output_acc: 0.6366 - footwear_output_acc: 0.6857 - pose_output_acc: 0.7775 - emotion_output_acc: 0.7157 - val_loss: 8.7415 - val_gender_output_loss: 0.7896 - val_image_quality_output_loss: 0.9844 - val_age_output_loss: 1.4296 - val_weight_output_loss: 0.9710 - val_bag_output_loss: 0.9039 - val_footwear_output_loss: 1.9501 - val_pose_output_loss: 0.7639 - val_emotion_output_loss: 0.9489 - val_gender_output_acc: 0.5938 - val_image_quality_output_acc: 0.5474 - val_age_output_acc: 0.3708 - val_weight_output_acc: 0.6438 - val_bag_output_acc: 0.5776 - val_footwear_output_acc: 0.3745 - val_pose_output_acc: 0.6583 - val_emotion_output_acc: 0.6833

Epoch 00024: val_loss did not improve from 7.16478
Epoch 25/25
312/312 [==============================] - 159s 509ms/step - loss: 6.4576 - gender_output_loss: 0.3426 - image_quality_output_loss: 0.9540 - age_output_loss: 1.3504 - weight_output_loss: 0.9327 - bag_output_loss: 0.8124 - footwear_output_loss: 0.7302 - pose_output_loss: 0.4908 - emotion_output_loss: 0.8445 - gender_output_acc: 0.8482 - image_quality_output_acc: 0.5619 - age_output_acc: 0.4127 - weight_output_acc: 0.6335 - bag_output_acc: 0.6437 - footwear_output_acc: 0.6909 - pose_output_acc: 0.8029 - emotion_output_acc: 0.7184 - val_loss: 7.0398 - val_gender_output_loss: 0.4836 - val_image_quality_output_loss: 0.9615 - val_age_output_loss: 1.4043 - val_weight_output_loss: 0.9513 - val_bag_output_loss: 0.8777 - val_footwear_output_loss: 0.8012 - val_pose_output_loss: 0.6379 - val_emotion_output_loss: 0.9221 - val_gender_output_acc: 0.7828 - val_image_quality_output_acc: 0.5599 - val_age_output_acc: 0.3797 - val_weight_output_acc: 0.6391 - val_bag_output_acc: 0.5969 - val_footwear_output_acc: 0.6453 - val_pose_output_acc: 0.7453 - val_emotion_output_acc: 0.6849

Epoch 00025: val_loss improved from 7.16478 to 7.03976, saving model to /content/drive/My Drive/Colab Notebooks/weights.25-7.04.hdf5
