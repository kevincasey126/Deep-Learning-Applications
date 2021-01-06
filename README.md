# Deep-Learning-Applications
Examples of a few deep learning applications such as an image classifier without using simplified libraries, utilizing specific hardware for these calculations and finding Jacobian values.

This python notebook was created in Google Colaboratory and can be run there without the need for any downloads of software. Within the notebook that is viewable within the browser, it contains the output from each cell.

#Explanations
For the image classifier I recreated the model used in the keras example using the direct tf.reshape, tf.nn.relu, tf.nn.dropout and tf.nn.softmax functions rather than the keras specified ones. The epochs are broken down into batches of size 128 and each run through the model. Once the model is run through, there is a sparse softmax cross entropy loss function to obtain the loss to use to get the gradients of the weights and biases. These gradients alter the weights and biases to train the model. The training goes at a much slower rate than the keras training and often runs into a local minima that prevents further training. To run 50 epochs, it took roughly 666 seconds and about 1.57 loss which is much higher than the keras training of a 0.0075 loss.

The use of tensorflow 2.0 GPU is required for this cell as it uses the GPU at much faster speeds speeds than the CPU. Tensorflow offers a quick switch between devices by simply stating the name of the device (which is given by tensorflow). It can be determined which device is being used by calling the tensor, which says which device it has been run on. The times can also be an indicator as the GPU runs at a significantly faster pace as it can use its cuda cores in parallel much quicker than a CPU could with its few cores.

The Jacobian value can be found by using multiple equations in a 2x2 matrix and finding their derivatives. Once their derivatives are found, the values can be input into the needed positions and solve for the determinant.  
