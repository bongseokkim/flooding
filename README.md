# flooding
implementation of Do We Need Zero Training Loss After Achieving Zero Training Error?


### short paper review (Do We Need Zero Training Loss After Achieving Zero Training Error?)
+ https://arxiv.org/abs/2002.08709
+ Overparameterized deep networks have the capacity to memorize training data with zero
training error. Even after memorization, the training loss continues to approach zero
+ existing regularizers do not directly aim to avoid zero training loss
+ propose a direct solution called flooding that intentionally prevents further reduction of the
training loss when it reaches a reasonably small value

### flood 
+ Its implementation is extremely simple (additional one line of code) 


<img src="https://github.com/bongseokkim/flooding/blob/main/picture/image_1.PNG"  width="40%">

## Exmperiment 
### Two Gaussainas 
+ Model : a five-hidden-layer NN with 500 units in each hidden layer with the ReLU
+ Optimizer : Adam
+ Epoch : 500
+ Flood level,b : [0,0.01,0.02.. 0.5]
+ Label noise : Low(1%), Middle (5%), High(10%)

<img src="https://github.com/bongseokkim/flooding/blob/main/picture/picutre_1.PNG"  width="60%">
<img src="https://github.com/bongseokkim/flooding/blob/main/picture/picture_3.PNG"  width="60%">


### CIFAR-10 
+ Model :  Resnet 44 from Proper ResNet Implementation for CIFAR10/CIFAR100 in Pytorch (https://github.com/akamaster/pytorch_resnet_cifar10) 
+ Agumentation : random crop , horizontal flip
+ Optimizer : SGD
+ Epoch : 500
+ Learning rate : 0.001, learning rate decay (multiply by 0.1 after 250 400 epoch)
+ Flood level,b : [0,0.01,0.02.. 0.1]

<img src="https://github.com/bongseokkim/flooding/blob/main/picture/picture_2.PNG"  width="60%">

## Improvement (tried)
+ do experiment in Two Gaussainas only 

### Flood with backward way 
<img src="https://github.com/bongseokkim/flooding/blob/main/picture/picture_4.PNG"  width="60%">

### Heuristic search to find flood level 
<img src="https://github.com/bongseokkim/flooding/blob/main/picture/picture_6.PNG"  width="60%">

### result 
<img src="https://github.com/bongseokkim/flooding/blob/main/picture/picture_7.PNG"  width="50%">
