---
layout: post
title: "Recurrent Neural Networks Tutorial"
date: "2016-05-18 14:33:14 -0400"
---

# RNN
Recurrent Neural Networks (RNN) are popular models that have shown great promise in many NLP tasks. But despite their current popularity I've only found a limited number of resources that throughly explain how RNN works, and how to implement. That's what this tutorial is about. It's a multi-part series in which I'm planning to cover the following:

1. Introduction to RNNs (this post)
2. Implementing a RNN using Python and Theano
3. Understanding the backpropagation through time (BPTT) algorithm and the vanishing gradient problem


Here is what a typical RNN looks like:
![ffff](/images/2016/05/rnn.jpg "A recurrent neural network and the unfolding in time of the computation involved in its forward computation. Source: Nature")
上图中的每个参数表示的意义如下：

1. $x_t$ is the input at time step $t$. For example, $x_i$ could be a one-hot vector corresponding to the second word of a sentence.
2. $s_t$ is the hidden state at time step $t$. It's the "memory" of the network. $s_t$ is calculated based on the previous hidden state and the input at the current step: $s_t=f(Ux_t+Ws_{t-1})$. The function $f$ usually is a nonlinearity such as $tanh$ or $ReLU$. $s_{-1}$, which is required to calculate the first hidden state, is typically initialized to all zeros.
3. $o_t$ is the output at step $t$. For example, if we wanted to predict the next word in a sentence it would be a vector of probabilities across our vocabulary. $o_t = softmax(Vs_t)$.


> The hidden state $s_t$ is the memory of the network and captures the information about what happened in all the previous time steps. **The output $o_t$ is calculated solely based on the memory at time $t$**.
> Unlike a traditional deep neural network, which uses different parameters at each layer, a RNN shares the same parameters $(U,V,W)$ across all steps.
> The above diagram has outputs at each time step, but depending on the task this may not be necessary. 例如，当我们去判断一个句子的意思时候，我们只关心最后的输出，而不care每一个单词对应的意思。

## RNN可以做什么
RNNs have shown great success in many NLP tasks (自然语言处理任务). 目前最常用的RNN为LSTM(long short-term memory). RNN可以处理的问题有如下几种：
1. Language modeling and generating text (语言建模和产生文档)
2. Machine translation (机器翻译)
3. Speech recognition (语音识别)
4. Generating image descriptions (产生图像说明)[Li Feifei's project webpage](http://cs.stanford.edu/people/karpathy/deepimagesent/)

## Training RNNs
BPTT (backpropagation through time): it is due to the fact that the parameters are dependent not only on the current state but also the previous time steps. So, we should sum up the gradients for all the related steps.

## RNN extensions
To overcome the vanilla RNN model, some type of extensions are developed:

1. Bidirectional RNNs are based on the idea that the output at time t may not only depend on the previous elements in the sequence, but also future elements. For example, to predict a missing word in a sequence you want to look at both the left and the right context. Bidirectional RNNs are quite simple. They are just two RNNs stacked on top of each other. The output is then computed based on the hidden state of both RNNs.
![](/images/2016/05/bidirectional-rnn.png)
2. Deep (Bidirectional) RNNs are similar to Bidirectional RNNs, only that we now have multiple layers per time step. In practice this gives us a higher learning capacity (but we also need a lot of training data).
![ ](/images/2016/05/Screen-Shot-2015-09-16-at-2.21.51-PM-272x300.png)
3. LSTM networks are quite popular these days and we briefly talked about them above. ***LSTMs don’t have a fundamentally different architecture from RNNs, but they use a different function to compute the hidden state.*** The memory in LSTMs are called cells and you can think of them as black boxes that take as input the previous state $h_{t-1}$ and current input $x_t$. Internally these cells  decide what to keep in (and what to erase from) memory. They then combine the previous state, the current memory, and the input. In turns out that these types of units are very efficient at capturing long-term dependencies.


hasdfa

## References
1. 理解RNN的一篇博文：http://colah.github.io/posts/2015-08-Understanding-LSTMs/
2. 介绍RNN强大功能的网页：http://karpathy.github.io/2015/05/21/rnn-effectiveness/
3. Li Feifei学生视频，碉堡https://www.youtube.com/watch?v=qPcCk1V1JO8
