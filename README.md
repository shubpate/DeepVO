# DeepVO

DeepVO - An RCNN approach to visual odometry 

**Paper implementation** - S. Wang, R. Clark, H. Wen and N. Trigoni, “DeepVO: Towards End-to-End Visual Odometry with Deep
Recurrent Convolutional Neural Networks” - 2017 https://www.cs.ox.ac.uk/files/9026/DeepVO.pdf

**Using KITTI VO Dataset**

![](C:\Users\shubp\Pictures\deepvo1.png)

### CODE IMPLEMENTATION AND DETAILS:

Provided code can be broken in below mentioned sections:

- Include files : pytorch, numpy, glob, os, cv2, time imports are made
- Helper functions for image and pose preprocessing :
- -  Get_image
  -  Load_images
  -  isRotationMatrix
  -  rotationMatrixToEulerAngles
  -  getMatrices
  -  Load_poses
- Helper function for dataload from training and test sequence : VODataLoader
- Dataload for training : X and y lists are created and then converted to tensors size [#batches, batch_size, 6, 384, 1280] and [#batches, batch_size, 6] respectively.
- Model definition: class DeepVONet is defined, implementation details were taken from DeepVO paper by Sen Wang
- Model creation
- Model loss and optimization
- Model training : Training is done at provided number of epochs and provided number of batches
- Dataload for testing: X_test and y_test are loaded from train sequences
- Model testing and accuracy prediction: y_output is computed from the model and saved to disk, and accuracy is calculated.
  All the code modules are created by us, apart from the isRotationMatrix and
  rotationMatrixToEulerAngles functions where referred to from https://www.learnopencv.com/rotation-matrix-to-euler-angles
