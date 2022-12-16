# flooding
implementation of Do We Need Zero Training Loss After Achieving Zero Training Error?


### short paper review (Do We Need Zero Training Loss After Achieving Zero Training Error?)
+ https://arxiv.org/abs/2002.08709
+ Overparameterized deep networks have the capacity to memorize training data with zero
training error. Even after memorization, the training loss continues to approach zero
+ existing regularizers do not directly aim to avoid zero training loss
+ propose a direct solution called flooding that intentionally prevents further reduction of the
training loss when it reaches a reasonably small value
