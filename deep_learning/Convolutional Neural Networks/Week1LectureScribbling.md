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
  - A 3D image when convolved with a 3D filter gives a 2D ouput. Example: 6 x 6 x 3 conv 3 x 3 x 3 = 4 x 4.
  - The dimensions of input image and filter should be same by convention.
  - We can apply multiple filters at the same time. For example finding vertical, horizontall and diognal edges at the same time. In that case the output of convolution will be a N dimension image. N is the number of filters you used. The output images after convolution will be stacked to form N dimension image. If number of filters used on a image are 2 then the output will be a 2 dimension image.


# Video: Pooling Layers
   - Poolings is done to 
        - reduce number of features so that it is easy on computation side
        - To make the detected features more robust
        - Note: Statement of Andrew NG: But I have to admit, I think the main reason people use max pooling is because it's been found in a lot of experiments to work well, and the intuition I just described, despite it being often cited, I don't know of anyone fully knows if that is the real underlying reason. I don't have anyone knows if that's the real underlying reason that max pooling works well in ConvNets.
        - So basically the idea of making features more robust is just an intuition but its not a solid proof.

   - Max Pooling is done more often that Average Pooling. Average pooling is rarely used and most of the time in deeper layer.
   - Padding can also be used but its almost never used in practice.
   - There are no parameters in Pooling. Only Hyperparameters (f,s,p). So there is nothing for backpropagation to learn.

# Video: Neural Network Example
   - What is called a layer in ConvNet (CNN) 
        - There are two conventions for it. First one which is mostly followed and followed by Andrew NG too is
            - Convolution + pooling combined is 1 layer. The thought process is that generally a layer has parameters to learn but since pooling doesnt have parameters and only hyperparameters it can't be called a layer. So thats why Convolution + pooling combined will be called 1 layer.
        - The second one which is also followed by a lot of people is
            - convolution is a seperate layer and pooling is a seperate layer

   - Typical CNN shape: input -> conv -> pool -> conv -> pool -> flatten -> fully connected (AKA dense) -> fully connected -> Softmax -> Output


# Video: Why Convolution
   - Why Convolution works best for Images. Few reasons
       - this
