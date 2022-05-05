Week 1 

Video: Padding
  - We do padding because of two reasons:
    - The pixels at the edges are not convolved equally as compared to the pixels in the middle. Some information might be lost as a result of that or we can say that some important features might be overlooked. So we add padding so that pixels on the edges are also convolved multiple time.
    - The size of the image will decrease after each colvolution operation. So if we have huge network with many convolution layers then after some convolutions image size will get very small. So to make sure that image size is not reduced after convolution we apply padding such that image size before and after convolution remains same.
