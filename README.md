# eip_class

Final Validation Accuracy
============================
Accuracy on test data is: 81.90

Model Code
=============

model_1 = Sequential()

model_1.add(SeparableConv2D(filters=32, kernel_size=(3,3), padding='valid', strides = (1,1), depth_multiplier = 2, activation = 'relu', input_shape = (32, 32, 3)))# Output Size: 30,30,32 RF 3
model_1.add(BatchNormalization())
model_1.add(Activation('relu'))
model_1.add(Dropout(0.1))


model_1.add(SeparableConv2D(filters=64, kernel_size=(3,3), use_bias= False, depth_multiplier = 2)) #Output Size: 28,28,63 RF: 5
model_1.add(BatchNormalization())
model_1.add(Activation('relu'))
model_1.add(Dropout(0.1))

model_1.add(SeparableConv2D(filters=128, kernel_size=(3,3), use_bias= False, depth_multiplier = 2)) #Output Size: 26,26,128 RF: 7
model_1.add(Activation('relu'))
model_1.add(BatchNormalization())
model_1.add(Dropout(0.1))


model_1.add(SeparableConv2D(filters=256, kernel_size=(3,3), use_bias= False, depth_multiplier = 1)) #Output Size: 24,24,256 RF: 8
model_1.add(Activation('relu'))
model_1.add(BatchNormalization())
model_1.add(Dropout(0.1))


model_1.add(MaxPooling2D(pool_size=(2, 2))) #Output Size: 12,12,128 RF: 11
model_1.add(Dropout(0.1))


model_1.add(SeparableConv2D(filters=32, kernel_size=(3,3), use_bias= False, depth_multiplier = 1)) #Output Size: 10,10,32 RF: 20
model_1.add(Activation('relu'))
model_1.add(BatchNormalization())
model_1.add(Dropout(0.1))

model_1.add(SeparableConv2D(filters=64, kernel_size=(3,3), use_bias= False, depth_multiplier = 1)) #Output Size: 8,8,64 RF: 28
model_1.add(Activation('relu'))
model_1.add(BatchNormalization())
model_1.add(Dropout(0.1))

model_1.add(SeparableConv2D(128, kernel_size=(3, 3),  depth_multiplier=1))  # Output Size:6,6,32  RF:36

model_1.add(MaxPooling2D(pool_size=(2, 2))) # Output Size:3,3,32    RF 42
model_1.add(Dropout(0.1))
model_1.add(SeparableConv2D( 10,kernel_size=(3, 3)))  # Output Size:1,1,10    RF:50

model_1.add(Flatten())
model_1.add(Dense(num_classes, activation='softmax')) 

model_1.compile(optimizer=Adam(lr=0.001), loss='categorical_crossentropy', metrics=['accuracy'])


50 EPoch Logs
================

Epoch 1/50

Epoch 00001: LearningRateScheduler setting learning rate to 0.004.
390/390 [==============================] - 46s 118ms/step - loss: 1.4005 - acc: 0.4868 - val_loss: 1.7765 - val_acc: 0.4758
Epoch 2/50

Epoch 00002: LearningRateScheduler setting learning rate to 0.0032744503.
390/390 [==============================] - 42s 108ms/step - loss: 1.0037 - acc: 0.6431 - val_loss: 1.1444 - val_acc: 0.6059
Epoch 3/50

Epoch 00003: LearningRateScheduler setting learning rate to 0.0028315018.
390/390 [==============================] - 42s 108ms/step - loss: 0.8729 - acc: 0.6916 - val_loss: 1.0399 - val_acc: 0.6370
Epoch 4/50

Epoch 00004: LearningRateScheduler setting learning rate to 0.0025329586000000003.
390/390 [==============================] - 43s 109ms/step - loss: 0.7850 - acc: 0.7254 - val_loss: 0.8381 - val_acc: 0.7144
Epoch 5/50

Epoch 00005: LearningRateScheduler setting learning rate to 0.0023181019000000002.
390/390 [==============================] - 43s 110ms/step - loss: 0.7244 - acc: 0.7458 - val_loss: 0.9664 - val_acc: 0.6801
Epoch 6/50

Epoch 00006: LearningRateScheduler setting learning rate to 0.0021560694.
390/390 [==============================] - 43s 110ms/step - loss: 0.6780 - acc: 0.7605 - val_loss: 0.8891 - val_acc: 0.6930
Epoch 7/50

Epoch 00007: LearningRateScheduler setting learning rate to 0.0020295127.
390/390 [==============================] - 43s 110ms/step - loss: 0.6410 - acc: 0.7734 - val_loss: 0.7828 - val_acc: 0.7289
Epoch 8/50

Epoch 00008: LearningRateScheduler setting learning rate to 0.0019279307.
390/390 [==============================] - 43s 110ms/step - loss: 0.6080 - acc: 0.7861 - val_loss: 0.9142 - val_acc: 0.6874
Epoch 9/50

Epoch 00009: LearningRateScheduler setting learning rate to 0.0018445946.
390/390 [==============================] - 43s 110ms/step - loss: 0.5836 - acc: 0.7959 - val_loss: 0.7084 - val_acc: 0.7605
Epoch 10/50

Epoch 00010: LearningRateScheduler setting learning rate to 0.0017749935.
390/390 [==============================] - 43s 110ms/step - loss: 0.5609 - acc: 0.8032 - val_loss: 0.8292 - val_acc: 0.7238
Epoch 11/50

Epoch 00011: LearningRateScheduler setting learning rate to 0.0017159904999999999.
390/390 [==============================] - 43s 110ms/step - loss: 0.5431 - acc: 0.8094 - val_loss: 0.7649 - val_acc: 0.7393
Epoch 12/50

Epoch 00012: LearningRateScheduler setting learning rate to 0.001665336.
390/390 [==============================] - 43s 110ms/step - loss: 0.5222 - acc: 0.8171 - val_loss: 0.7155 - val_acc: 0.7565
Epoch 13/50

Epoch 00013: LearningRateScheduler setting learning rate to 0.0016213753.
390/390 [==============================] - 43s 111ms/step - loss: 0.5078 - acc: 0.8214 - val_loss: 0.7560 - val_acc: 0.7413
Epoch 14/50

Epoch 00014: LearningRateScheduler setting learning rate to 0.0015828638000000002.
390/390 [==============================] - 43s 110ms/step - loss: 0.4937 - acc: 0.8280 - val_loss: 0.6983 - val_acc: 0.7670
Epoch 15/50

Epoch 00015: LearningRateScheduler setting learning rate to 0.0015488474.
390/390 [==============================] - 43s 110ms/step - loss: 0.4784 - acc: 0.8331 - val_loss: 0.6803 - val_acc: 0.7645
Epoch 16/50

Epoch 00016: LearningRateScheduler setting learning rate to 0.0015185825.
390/390 [==============================] - 43s 110ms/step - loss: 0.4670 - acc: 0.8361 - val_loss: 0.6222 - val_acc: 0.7925
Epoch 17/50

Epoch 00017: LearningRateScheduler setting learning rate to 0.001491481.
390/390 [==============================] - 43s 111ms/step - loss: 0.4531 - acc: 0.8403 - val_loss: 0.7263 - val_acc: 0.7674
Epoch 18/50

Epoch 00018: LearningRateScheduler setting learning rate to 0.0014670715.
390/390 [==============================] - 43s 110ms/step - loss: 0.4419 - acc: 0.8434 - val_loss: 0.7265 - val_acc: 0.7635
Epoch 19/50

Epoch 00019: LearningRateScheduler setting learning rate to 0.0014449718.
390/390 [==============================] - 43s 110ms/step - loss: 0.4334 - acc: 0.8466 - val_loss: 0.7065 - val_acc: 0.7631
Epoch 20/50

Epoch 00020: LearningRateScheduler setting learning rate to 0.001424869.
390/390 [==============================] - 43s 110ms/step - loss: 0.4243 - acc: 0.8505 - val_loss: 0.6354 - val_acc: 0.7952
Epoch 21/50

Epoch 00021: LearningRateScheduler setting learning rate to 0.0014065041.
390/390 [==============================] - 43s 109ms/step - loss: 0.4163 - acc: 0.8536 - val_loss: 0.6023 - val_acc: 0.8028
Epoch 22/50

Epoch 00022: LearningRateScheduler setting learning rate to 0.001389661.
390/390 [==============================] - 43s 109ms/step - loss: 0.4072 - acc: 0.8555 - val_loss: 0.6967 - val_acc: 0.7697
Epoch 23/50

Epoch 00023: LearningRateScheduler setting learning rate to 0.0013741581.
390/390 [==============================] - 43s 110ms/step - loss: 0.3987 - acc: 0.8588 - val_loss: 0.6443 - val_acc: 0.7907
Epoch 24/50

Epoch 00024: LearningRateScheduler setting learning rate to 0.0013598417.
390/390 [==============================] - 43s 111ms/step - loss: 0.3911 - acc: 0.8610 - val_loss: 0.6203 - val_acc: 0.7983
Epoch 25/50

Epoch 00025: LearningRateScheduler setting learning rate to 0.0013465804000000001.
390/390 [==============================] - 43s 111ms/step - loss: 0.3841 - acc: 0.8630 - val_loss: 0.6167 - val_acc: 0.8020
Epoch 26/50

Epoch 00026: LearningRateScheduler setting learning rate to 0.0013342618.
390/390 [==============================] - 43s 111ms/step - loss: 0.3789 - acc: 0.8648 - val_loss: 0.7264 - val_acc: 0.7655
Epoch 27/50

Epoch 00027: LearningRateScheduler setting learning rate to 0.0013227889.
390/390 [==============================] - 43s 111ms/step - loss: 0.3726 - acc: 0.8659 - val_loss: 0.6645 - val_acc: 0.7782
Epoch 28/50

Epoch 00028: LearningRateScheduler setting learning rate to 0.0013120774.
390/390 [==============================] - 43s 111ms/step - loss: 0.3689 - acc: 0.8682 - val_loss: 0.7193 - val_acc: 0.7815
Epoch 29/50

Epoch 00029: LearningRateScheduler setting learning rate to 0.001302054.
390/390 [==============================] - 43s 111ms/step - loss: 0.3630 - acc: 0.8712 - val_loss: 0.6488 - val_acc: 0.7881
Epoch 30/50

Epoch 00030: LearningRateScheduler setting learning rate to 0.0012926544.
390/390 [==============================] - 43s 110ms/step - loss: 0.3556 - acc: 0.8726 - val_loss: 0.7038 - val_acc: 0.7814
Epoch 31/50

Epoch 00031: LearningRateScheduler setting learning rate to 0.0012838221.
390/390 [==============================] - 43s 111ms/step - loss: 0.3502 - acc: 0.8755 - val_loss: 0.6490 - val_acc: 0.7912
Epoch 32/50

Epoch 00032: LearningRateScheduler setting learning rate to 0.0012755074.
390/390 [==============================] - 43s 111ms/step - loss: 0.3444 - acc: 0.8764 - val_loss: 0.6479 - val_acc: 0.7966
Epoch 33/50

Epoch 00033: LearningRateScheduler setting learning rate to 0.000267666.
390/390 [==============================] - 43s 111ms/step - loss: 0.2977 - acc: 0.8940 - val_loss: 0.6053 - val_acc: 0.8138
Epoch 34/50

Epoch 00034: LearningRateScheduler setting learning rate to 0.0002602585.
390/390 [==============================] - 43s 111ms/step - loss: 0.2774 - acc: 0.9004 - val_loss: 0.6075 - val_acc: 0.8114
Epoch 35/50

Epoch 00035: LearningRateScheduler setting learning rate to 0.00025325.
390/390 [==============================] - 43s 110ms/step - loss: 0.2761 - acc: 0.9003 - val_loss: 0.6029 - val_acc: 0.8165
Epoch 36/50

Epoch 00036: LearningRateScheduler setting learning rate to 0.0002466091.
390/390 [==============================] - 43s 111ms/step - loss: 0.2712 - acc: 0.9031 - val_loss: 0.6101 - val_acc: 0.8161
Epoch 37/50

Epoch 00037: LearningRateScheduler setting learning rate to 0.0002403076.
390/390 [==============================] - 43s 111ms/step - loss: 0.2657 - acc: 0.9059 - val_loss: 0.6191 - val_acc: 0.8147
Epoch 38/50

Epoch 00038: LearningRateScheduler setting learning rate to 0.0002343201.
390/390 [==============================] - 43s 111ms/step - loss: 0.2642 - acc: 0.9039 - val_loss: 0.6218 - val_acc: 0.8124
Epoch 39/50

Epoch 00039: LearningRateScheduler setting learning rate to 0.0002286237.
390/390 [==============================] - 43s 110ms/step - loss: 0.2650 - acc: 0.9066 - val_loss: 0.6082 - val_acc: 0.8200
Epoch 40/50

Epoch 00040: LearningRateScheduler setting learning rate to 0.0002231977.
390/390 [==============================] - 43s 110ms/step - loss: 0.2645 - acc: 0.9047 - val_loss: 0.6191 - val_acc: 0.8155
Epoch 41/50

Epoch 00041: LearningRateScheduler setting learning rate to 0.0002180233.
390/390 [==============================] - 43s 110ms/step - loss: 0.2568 - acc: 0.9071 - val_loss: 0.6095 - val_acc: 0.8197
Epoch 42/50

Epoch 00042: LearningRateScheduler setting learning rate to 0.0002130833.
390/390 [==============================] - 43s 110ms/step - loss: 0.2602 - acc: 0.9053 - val_loss: 0.6080 - val_acc: 0.8166
Epoch 43/50

Epoch 00043: LearningRateScheduler setting learning rate to 0.0002083623.
390/390 [==============================] - 43s 110ms/step - loss: 0.2542 - acc: 0.9099 - val_loss: 0.6070 - val_acc: 0.8176
Epoch 44/50

Epoch 00044: LearningRateScheduler setting learning rate to 0.0002038459.
390/390 [==============================] - 43s 110ms/step - loss: 0.2526 - acc: 0.9097 - val_loss: 0.6132 - val_acc: 0.8211
Epoch 45/50

Epoch 00045: LearningRateScheduler setting learning rate to 0.0001995211.
390/390 [==============================] - 43s 110ms/step - loss: 0.2522 - acc: 0.9094 - val_loss: 0.6195 - val_acc: 0.8178
Epoch 46/50

Epoch 00046: LearningRateScheduler setting learning rate to 0.0001953761.
390/390 [==============================] - 43s 111ms/step - loss: 0.2480 - acc: 0.9113 - val_loss: 0.6282 - val_acc: 0.8160
Epoch 47/50

Epoch 00047: LearningRateScheduler setting learning rate to 0.0001913998.
390/390 [==============================] - 43s 111ms/step - loss: 0.2481 - acc: 0.9101 - val_loss: 0.6158 - val_acc: 0.8177
Epoch 48/50

Epoch 00048: LearningRateScheduler setting learning rate to 0.0001875821.
390/390 [==============================] - 43s 110ms/step - loss: 0.2431 - acc: 0.9130 - val_loss: 0.6339 - val_acc: 0.8158
Epoch 49/50

Epoch 00049: LearningRateScheduler setting learning rate to 0.0001839137.
390/390 [==============================] - 43s 110ms/step - loss: 0.2415 - acc: 0.9137 - val_loss: 0.6359 - val_acc: 0.8174
Epoch 50/50

Epoch 00050: LearningRateScheduler setting learning rate to 0.000180386.
390/390 [==============================] - 43s 110ms/step - loss: 0.2433 - acc: 0.9127 - val_loss: 0.6333 - val_acc: 0.8190
