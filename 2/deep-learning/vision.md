# Vision

## Multiple Object Recognition with Visual Attention

> Jimmy, Mnih, 2015

Present an attention-based model for recognizing multiple objects. Model is a deep RNN trained with RL to attend to the most relevant regions of the input image. Evaluate the model on house number sequences from Google street view images. Better accuracy, fewer parameters, and less computation than state-of-the-art convolutional networks.

#### Introduction 

Main **drawbacks of CNN** is poor scalability with increasing input image size.

The proposed system is a deep RNN processes a multi-resolution crop of the input image, called a glimpse.

