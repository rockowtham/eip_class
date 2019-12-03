# eip_class

Final Validation Accuracy
============================
Accuracy on test data is: 81.31

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
# model.add(GlobalAveragePooling2D())
model_1.add(Dense(num_classes, activation='softmax')) 

# Compile the model
model_1.compile(optimizer=Adam(lr=0.001), loss='categorical_crossentropy', metrics=['accuracy'])


50 EPoch Logs
================

Epoch 1/50

Epoch 00001: LearningRateScheduler setting learning rate to 0.004.
390/390 [==============================] - 47s 119ms/step - loss: 1.4506 - acc: 0.4637 - val_loss: 2.0256 - val_acc: 0.4496
Epoch 2/50

Epoch 00002: LearningRateScheduler setting learning rate to 0.0032744503.
390/390 [==============================] - 43s 109ms/step - loss: 1.0256 - acc: 0.6328 - val_loss: 1.0707 - val_acc: 0.6237
Epoch 3/50

Epoch 00003: LearningRateScheduler setting learning rate to 0.0028315018.
390/390 [==============================] - 43s 109ms/step - loss: 0.8646 - acc: 0.6951 - val_loss: 1.0022 - val_acc: 0.6614
Epoch 4/50

Epoch 00004: LearningRateScheduler setting learning rate to 0.0025329586000000003.
390/390 [==============================] - 43s 110ms/step - loss: 0.7755 - acc: 0.7265 - val_loss: 0.9419 - val_acc: 0.6839
Epoch 5/50

Epoch 00005: LearningRateScheduler setting learning rate to 0.0023181019000000002.
390/390 [==============================] - 43s 109ms/step - loss: 0.7167 - acc: 0.7496 - val_loss: 0.8853 - val_acc: 0.7030
Epoch 6/50

Epoch 00006: LearningRateScheduler setting learning rate to 0.0021560694.
390/390 [==============================] - 43s 109ms/step - loss: 0.6694 - acc: 0.7654 - val_loss: 0.7796 - val_acc: 0.7337
Epoch 7/50

Epoch 00007: LearningRateScheduler setting learning rate to 0.0020295127.
390/390 [==============================] - 43s 109ms/step - loss: 0.6326 - acc: 0.7784 - val_loss: 0.8154 - val_acc: 0.7394
Epoch 8/50

Epoch 00008: LearningRateScheduler setting learning rate to 0.0019279307.
390/390 [==============================] - 43s 109ms/step - loss: 0.5992 - acc: 0.7901 - val_loss: 0.7718 - val_acc: 0.7408
Epoch 9/50

Epoch 00009: LearningRateScheduler setting learning rate to 0.0018445946.
390/390 [==============================] - 43s 109ms/step - loss: 0.5741 - acc: 0.7993 - val_loss: 0.9237 - val_acc: 0.7097
Epoch 10/50

Epoch 00010: LearningRateScheduler setting learning rate to 0.0017749935.
390/390 [==============================] - 43s 109ms/step - loss: 0.5515 - acc: 0.8071 - val_loss: 0.6906 - val_acc: 0.7668
Epoch 11/50

Epoch 00011: LearningRateScheduler setting learning rate to 0.0017159904999999999.
390/390 [==============================] - 43s 109ms/step - loss: 0.5311 - acc: 0.8138 - val_loss: 0.8887 - val_acc: 0.7158
Epoch 12/50

Epoch 00012: LearningRateScheduler setting learning rate to 0.001665336.
390/390 [==============================] - 43s 109ms/step - loss: 0.5130 - acc: 0.8200 - val_loss: 0.6426 - val_acc: 0.7876
Epoch 13/50

Epoch 00013: LearningRateScheduler setting learning rate to 0.0016213753.
390/390 [==============================] - 43s 109ms/step - loss: 0.4893 - acc: 0.8287 - val_loss: 0.6680 - val_acc: 0.7737
Epoch 14/50

Epoch 00014: LearningRateScheduler setting learning rate to 0.0015828638000000002.
390/390 [==============================] - 42s 109ms/step - loss: 0.4807 - acc: 0.8299 - val_loss: 0.7388 - val_acc: 0.7560
Epoch 15/50

Epoch 00015: LearningRateScheduler setting learning rate to 0.0015488474.
390/390 [==============================] - 43s 109ms/step - loss: 0.4635 - acc: 0.8371 - val_loss: 0.7324 - val_acc: 0.7679
Epoch 16/50

Epoch 00016: LearningRateScheduler setting learning rate to 0.0015185825.
390/390 [==============================] - 43s 109ms/step - loss: 0.4500 - acc: 0.8401 - val_loss: 0.6344 - val_acc: 0.7911
Epoch 17/50

Epoch 00017: LearningRateScheduler setting learning rate to 0.001491481.
390/390 [==============================] - 43s 109ms/step - loss: 0.4394 - acc: 0.8445 - val_loss: 0.6507 - val_acc: 0.7889
Epoch 18/50

Epoch 00018: LearningRateScheduler setting learning rate to 0.0014670715.
390/390 [==============================] - 43s 109ms/step - loss: 0.4314 - acc: 0.8482 - val_loss: 0.6535 - val_acc: 0.7848
Epoch 19/50

Epoch 00019: LearningRateScheduler setting learning rate to 0.0014449718.
390/390 [==============================] - 43s 109ms/step - loss: 0.4151 - acc: 0.8547 - val_loss: 0.6898 - val_acc: 0.7810
Epoch 20/50

Epoch 00020: LearningRateScheduler setting learning rate to 0.001424869.
390/390 [==============================] - 42s 109ms/step - loss: 0.4092 - acc: 0.8549 - val_loss: 0.6710 - val_acc: 0.7833
Epoch 21/50

Epoch 00021: LearningRateScheduler setting learning rate to 0.0014065041.
390/390 [==============================] - 42s 109ms/step - loss: 0.4009 - acc: 0.8575 - val_loss: 0.7179 - val_acc: 0.7858
Epoch 22/50

Epoch 00022: LearningRateScheduler setting learning rate to 0.001389661.
390/390 [==============================] - 42s 109ms/step - loss: 0.3930 - acc: 0.8615 - val_loss: 0.6871 - val_acc: 0.7845
Epoch 23/50

Epoch 00023: LearningRateScheduler setting learning rate to 0.0013741581.
390/390 [==============================] - 42s 109ms/step - loss: 0.3828 - acc: 0.8631 - val_loss: 0.6450 - val_acc: 0.7950
Epoch 24/50

Epoch 00024: LearningRateScheduler setting learning rate to 0.0013598417.
390/390 [==============================] - 43s 109ms/step - loss: 0.3812 - acc: 0.8650 - val_loss: 0.6450 - val_acc: 0.7974
Epoch 25/50

Epoch 00025: LearningRateScheduler setting learning rate to 0.0013465804000000001.
390/390 [==============================] - 42s 109ms/step - loss: 0.3660 - acc: 0.8713 - val_loss: 0.6860 - val_acc: 0.7891
Epoch 26/50

Epoch 00026: LearningRateScheduler setting learning rate to 0.0013342618.
390/390 [==============================] - 42s 109ms/step - loss: 0.3680 - acc: 0.8695 - val_loss: 0.7200 - val_acc: 0.7749
Epoch 27/50

Epoch 00027: LearningRateScheduler setting learning rate to 0.0013227889.
390/390 [==============================] - 43s 109ms/step - loss: 0.3520 - acc: 0.8733 - val_loss: 0.6818 - val_acc: 0.7945
Epoch 28/50

Epoch 00028: LearningRateScheduler setting learning rate to 0.0013120774.
390/390 [==============================] - 43s 111ms/step - loss: 0.3538 - acc: 0.8758 - val_loss: 0.6685 - val_acc: 0.7969
Epoch 29/50

Epoch 00029: LearningRateScheduler setting learning rate to 0.001302054.
390/390 [==============================] - 42s 109ms/step - loss: 0.3459 - acc: 0.8762 - val_loss: 0.7202 - val_acc: 0.7925
Epoch 30/50

Epoch 00030: LearningRateScheduler setting learning rate to 0.0012926544.
390/390 [==============================] - 43s 109ms/step - loss: 0.3418 - acc: 0.8791 - val_loss: 0.7683 - val_acc: 0.7803
Epoch 31/50

Epoch 00031: LearningRateScheduler setting learning rate to 0.0012838221.
390/390 [==============================] - 43s 109ms/step - loss: 0.3332 - acc: 0.8811 - val_loss: 0.6383 - val_acc: 0.8087
Epoch 32/50

Epoch 00032: LearningRateScheduler setting learning rate to 0.0012755074.
390/390 [==============================] - 43s 110ms/step - loss: 0.3380 - acc: 0.8800 - val_loss: 0.6743 - val_acc: 0.7948
Epoch 33/50

Epoch 00033: LearningRateScheduler setting learning rate to 0.000267666.
390/390 [==============================] - 43s 109ms/step - loss: 0.2845 - acc: 0.8979 - val_loss: 0.6454 - val_acc: 0.8069
Epoch 34/50

Epoch 00034: LearningRateScheduler setting learning rate to 0.0002602585.
390/390 [==============================] - 42s 109ms/step - loss: 0.2678 - acc: 0.9045 - val_loss: 0.6513 - val_acc: 0.8109
Epoch 35/50

Epoch 00035: LearningRateScheduler setting learning rate to 0.00025325.
390/390 [==============================] - 43s 109ms/step - loss: 0.2675 - acc: 0.9035 - val_loss: 0.6641 - val_acc: 0.8074
Epoch 36/50

Epoch 00036: LearningRateScheduler setting learning rate to 0.0002466091.
390/390 [==============================] - 43s 109ms/step - loss: 0.2560 - acc: 0.9095 - val_loss: 0.6746 - val_acc: 0.8086
Epoch 37/50

Epoch 00037: LearningRateScheduler setting learning rate to 0.0002403076.
390/390 [==============================] - 42s 109ms/step - loss: 0.2571 - acc: 0.9072 - val_loss: 0.6667 - val_acc: 0.8093
Epoch 38/50

Epoch 00038: LearningRateScheduler setting learning rate to 0.0002343201.
390/390 [==============================] - 43s 109ms/step - loss: 0.2527 - acc: 0.9103 - val_loss: 0.6570 - val_acc: 0.8133
Epoch 39/50

Epoch 00039: LearningRateScheduler setting learning rate to 0.0002286237.
390/390 [==============================] - 43s 109ms/step - loss: 0.2519 - acc: 0.9099 - val_loss: 0.6729 - val_acc: 0.8103
Epoch 40/50

Epoch 00040: LearningRateScheduler setting learning rate to 0.0002231977.
390/390 [==============================] - 43s 109ms/step - loss: 0.2462 - acc: 0.9107 - val_loss: 0.7151 - val_acc: 0.8045
Epoch 41/50

Epoch 00041: LearningRateScheduler setting learning rate to 0.0002180233.
390/390 [==============================] - 43s 110ms/step - loss: 0.2419 - acc: 0.9133 - val_loss: 0.6802 - val_acc: 0.8117
Epoch 42/50

Epoch 00042: LearningRateScheduler setting learning rate to 0.0002130833.
390/390 [==============================] - 43s 110ms/step - loss: 0.2433 - acc: 0.9127 - val_loss: 0.6921 - val_acc: 0.8068
Epoch 43/50

Epoch 00043: LearningRateScheduler setting learning rate to 0.0002083623.
390/390 [==============================] - 43s 110ms/step - loss: 0.2402 - acc: 0.9125 - val_loss: 0.6773 - val_acc: 0.8129
Epoch 44/50

Epoch 00044: LearningRateScheduler setting learning rate to 0.0002038459.
390/390 [==============================] - 43s 110ms/step - loss: 0.2423 - acc: 0.9136 - val_loss: 0.6945 - val_acc: 0.8118
Epoch 45/50

Epoch 00045: LearningRateScheduler setting learning rate to 0.0001995211.
390/390 [==============================] - 43s 110ms/step - loss: 0.2388 - acc: 0.9130 - val_loss: 0.6853 - val_acc: 0.8135
Epoch 46/50

Epoch 00046: LearningRateScheduler setting learning rate to 0.0001953761.
390/390 [==============================] - 43s 110ms/step - loss: 0.2378 - acc: 0.9139 - val_loss: 0.7080 - val_acc: 0.8089
Epoch 47/50

Epoch 00047: LearningRateScheduler setting learning rate to 0.0001913998.
390/390 [==============================] - 43s 109ms/step - loss: 0.2320 - acc: 0.9174 - val_loss: 0.6843 - val_acc: 0.8142
Epoch 48/50

Epoch 00048: LearningRateScheduler setting learning rate to 0.0001875821.
390/390 [==============================] - 43s 110ms/step - loss: 0.2348 - acc: 0.9154 - val_loss: 0.6964 - val_acc: 0.8114
Epoch 49/50

Epoch 00049: LearningRateScheduler setting learning rate to 0.0001839137.
390/390 [==============================] - 43s 109ms/step - loss: 0.2310 - acc: 0.9165 - val_loss: 0.7266 - val_acc: 0.8099
Epoch 50/50

Epoch 00050: LearningRateScheduler setting learning rate to 0.000180386.
390/390 [==============================] - 43s 110ms/step - loss: 0.2284 - acc: 0.9160 - val_loss: 0.7031 - val_acc: 0.8131
