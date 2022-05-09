# Video: Padding

  - By Convention we do padding with 0
  - We do padding because of two reasons:
    - The pixels at the edges are not convolved equally as compared to the pixels in the middle. Some information might be lost as a result of that or we can say that some important features might be overlooked. So we add padding so that pixels on the edges are also convolved multiple time.
    - The size of the image will decrease after each colvolution operation. So if we have huge network with many convolution layers then after some convolutions image size will get very small. So to make sure that image size is not reduced after convolution we apply padding such that image size before and after convolution remains same.
  - Two common types of Convolutions
    - Valid Convolution
      - No padding done
    - Same Convolution
      - Padding is done so that image size before and after padding is same
 - By convention **f** (filter shape. 3cross3 filter mean f=3) is always odd.


# Video: Strided Convolution
  - By Convention Convolution will be done only when filter is fully over the image+padding. If any row/column of filter is beyond the image then dont convolve
  - In mathematics, Convolution operation involves flipping the filter horizontally and vertically before doing dot product. Whereas in Deep Learning literature direct filter is used for dot product, no flipping is done


# Video: Convolution Over Volume
  - A 3D image when convolved with one 3D filter gives a 2D ouput. Example: 6*6*3 conv 3*3*3 = 4*4.
  - The dimensions of input image and filter should be same.
  - We can apply multiple filter at the same time. In that case the output of convolution will be a N dimension image. N is the number of filters you used. The outputs images after convolution will be stacked to form N dimension image. If number of filters used on a image are 2 then the output will be a 2 dimension image.
