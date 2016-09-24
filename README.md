# Testing activations
Testing different activation functions in neural networks. This was my old code, "work-in-progress", I wrote using Caffe. It seemed to prove that you can get much MUCH better results, actually, just awesome results, with 2 consecutive grouped layers with PReLU/ELU activations and can relatively easlily approximate non-convex functions vs what seems to be possible via 2 Maxout layers.

You'll likely need to change some paths to files. This is not intended for too broad an audience, if any. =)

2 Maxout layers. 1 neuron -> Maxout -> Minout -> 1 neuron

![2 maxout layers](2-maxout.png)


PReLU followed by one of [ELU, Softmax, Sigmoid, TanH, etc]. 1 neuron -> Wide with PReLU -> Narrower with [ELU, Softmax, Sigmoid, TanH, etc] -> 1 neuron

![PReLU followed by ELU, or Softmax](bezier-pyramid.png)



PReLU followed by SoftMax architecture was inspired by Bezier curves https://www.jasondavies.com/animated-bezier/ and seemed to perform same as PReLU followed by ELU. I think I did later find some article published by other people who tried something very very similar having different much less exciting inspiration, but can't find it at the moment.

If you'll discover some even better architectures, please, tell. (>‿◠)✌
