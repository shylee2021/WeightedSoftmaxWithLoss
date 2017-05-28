# WeightedSoftmaxWithLoss
Weighted Softmax With Loss for [Caffe](https://github.com/BVLC/caffe)

## How to Install

Copy `caffe.proto` to `$YOUR_CAFFE_HOME/src/caffe/proto`.

Copy `weighted_softmax_loss_layer.hpp` to `$YOUR_CAFFE_HOME/include/caffe/layers`.

Copy `weighted_softmax_loss_layer.cpp` to `$YOUR_CAFFE_HOME/src/caffe/layers`.

Build Caffe.

## How to Use
The example of prototxt of weighted softmax loss is following:
~~~
layer {
  name: "loss"
  type: "WeightedSoftmaxWithLoss"
  bottom: "bottom"
  bottom: "label"
  top: "loss"
  weighted_softmax_param {
    positions: "0,2"
    weights: "3,5"
  }
}
~~~

Write the positions that you want to assign weights in `positions`.

Write the weights corresponding to the position you wrote in `weights`.

1 will be automatically assigned to omitted positions.


## Notice
GPU version(.cu) is not supported yet.
