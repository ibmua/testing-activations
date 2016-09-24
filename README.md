# Testing activations
Testing different activation functions in neural networks. This was my old code, "work-in-progress", I wrote using Caffe. It seemed to prove that you can get much MUCH better results, actually, just awesome results, with 2 consecutive grouped layers with PReLU/ELU activations and can relatively easlily approximate non-convex functions vs what seems to be possible via 2 Maxout layers.

You'll likely need to change some paths to files. This is not intended for too broad an audience, if any. =)

Blue dots are from the underlying function, red dots are from the approximation learnt by NN. Maxout seemed harder to choose hyperparameters for, worked in a narrower range of LR, as far as I recall.

2 Maxout layers. 1 neuron -> Maxout -> Minout -> 1 neuron

![2 maxout layers](2-maxout.png)


PReLU followed by one of [ELU, Softmax, Sigmoid, TanH, etc]. 

1 neuron ->

4xN (N>=1) neurons with PReLU. Split into several groups and fully-connect neurons inside these groups, but not amoung different groups. Same as what happens inside Maxout. Approximating a convex function ->

2xM (M<=N) neurons with [ELU, Softmax, Sigmoid, TanH, etc]. Same kind of connecting done in this layer. Thereby, reversing the convex functions and combining them to achieve a non-convex one ->

1 neuron

![PReLU followed by ELU, or Softmax](bezier-pyramid.png)



PReLU followed by SoftMax architecture was inspired by Bezier curves https://www.jasondavies.com/animated-bezier/ and seemed to perform same as PReLU followed by ELU. I think I did later find some article published by other people who tried something very very similar having different much less exciting inspiration, but can't find it at the moment.

If you'll discover some even better architectures, please, tell. (>‿◠)✌ I think Bezier curves should be a major inspiration for good activation functions.
