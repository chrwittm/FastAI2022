# Lesson 3 of Fast.AI 2022 Edition

[Lesson 3](https://www.youtube.com/watch?v=hBBOjCiFcuo) took me a while to rework, because it churned out quite a few interesting projects:

* [Visualizing Gradient Descent in 3D](https://chrwittm.github.io/posts/2022-10-13-visualizing-gradient-descent-in-3d/)
* Working on the Kaggle [Titanic Competition](https://chrwittm.github.io/posts/2022-11-05-kaggle-titanic/)
* Implementing a model for recognizing digits of the [MNIST-dataset](https://chrwittm.github.io/posts/2022-11-26-mnist/)

Alongside these 3 main activities, I also started [a blog on my machine learning journey](https://chrwittm.github.io/), which is [based on Quarto](https://chrwittm.github.io/posts/2022-10-21-how-i-created-this-blog/).

Let me summarize what I have done and learned.

## Gradient Descent

The main focus of [lesson 3](https://www.youtube.com/watch?v=hBBOjCiFcuo&t=1416s) for me was/is [gradient descent](https://en.wikipedia.org/wiki/Gradient_descent), which I found pretty easy to understand on a high level:

* Calculate the predictions and the loss (forward-pass)
* Calculate the derivatives of the parameters (i.e. how does changing the parameters change the loss) (backward-pass)
* Update the parameters (via the learning rate)
* Don't forget to [initialize the gradients](https://twitter.com/karpathy/status/1013244313327681536?lang=en)
* Restart

However, in the actual implementation and its simplicity, there is a lot of magic, which I tried to unpack for myself. Working through Jeremy's notebook "[How does a neural net really work?](https://www.kaggle.com/code/jhoward/how-does-a-neural-net-really-work/)", I tried to not only think through the concept, but also to visualize it. The result is available as

* a [blog post](https://chrwittm.github.io/posts/2022-10-13-visualizing-gradient-descent-in-3d/)
* a [forum post](https://forums.fast.ai/t/visualizing-gradient-descent-in-3d/101084)
* a [Kaggle notebook](https://www.kaggle.com/code/christianwittmann/visualizing-gradient-descent-in-3d) in which you can easily also play with the visualizations interactively (by copying and running the notebook)
* a [GitHub notebook](https://github.com/chrwittm/FastAI2022/blob/main/lesson03/visualizing-gradient-descent-in-3d.ipynb)

I was excited and honored to read that [Ben](https://forums.fast.ai/u/benkarr), a fellow Fast.AI student, created even [better visualizations](https://ben-karr.github.io/react-3d-gradients/) building on my work. I highly recommend playing with it and also checking out [his other projects](https://ben-karr.github.io/).

While I truly love the Fast.AI content, I also need to mention the great video "[The spelled-out intro to neural networks and backpropagation: building micrograd](https://www.youtube.com/watch?v=VMj-3S1tku0)" from [Andrej Karpathy](https://karpathy.ai/), which dives at least one level deeper. If there is one key takeaway from this video, it is this one: "A single gradient tells us the effect changing a parameter has on the loss". This insight is powerful, and somehow it tends to get lost from my point of view, because you either have a very complex model with many, many parameters so that this is difficult to grasp, or you have a seemingly simple model in which you mix up the slope of the quadratic with a gradient. Implementing the visualization of gradient descent was also about building the intuition of what is actually going on under to hood.

## The Titanic Competition

Inspired by the [Excel-based version](https://www.youtube.com/watch?v=hBBOjCiFcuo&list=PLfYUBJiXbdtSvpQjSnJJ_PmDQB_VyT5iU&index=3&t=3862s) of the [Titanic Competition](https://www.kaggle.com/c/titanic), I decided to enter the kaggle competition. As with many good project, this resulted in a few other mini-projects:

* The logistics on how a kaggle competition actually works, which included [installing kaggle](https://chrwittm.github.io/posts/2022-11-05-kaggle-titanic/#installing-kaggle) on my local machine. The [Live-Coding Sessions](https://forums.fast.ai/t/live-coding-aka-walk-thrus/96617) of the 2022 Fast.AI course are probably quite underrated (at least looking at the number of views they get on Youtube). I find them a great addition to the official lessons because the tackle side problems like installing kaggle (in [Live-Coding Session 7](https://youtu.be/cagqUrHMDJ0) and the related [official topic in the forums](https://forums.fast.ai/t/live-coding-7/96811)) which otherwise would set you back some hours (or more). A big shout-out for these sessions!
* Revisiting [matrix multiplication](https://chrwittm.github.io/posts/2022-10-28-matrix-multiplication/). Apart from the math, this also was about some python basics for me. While the result of [implementing matrix multiplication from scratch](https://chrwittm.github.io/posts/2022-10-28-matrix-multiplication/#exercise-implement-matrix-multiplication-with-tensors) has probably been done a million times, it still taught me some valuable lessons.

In the actual [Titanic Competition](https://chrwittm.github.io/posts/2022-11-05-kaggle-titanic/), I did not focus too much on submitting a perfect result, but I rather aimed at re-visiting/solidifying the topic of gradient descent by replicating the actual lesson content. I built for following 2 notebooks

* The first one uses a [Fast.AI tabular learner](https://github.com/chrwittm/FastAI2022/blob/main/lesson03/titanic/titanic1/titanic1.ipynb) to create a baseline while getting the know the data.
* Next, I re-implemented the Excel-based version from the video in python [in this notebook](https://github.com/chrwittm/FastAI2022/blob/main/lesson03/titanic/titanic3/titanic3.ipynb).

While my final high score of 77.2% is far away from perfect, I decided to come back to this competition another time, focusing more on the content, not just on gradient descent (like this time).

## MNIST, the 'Hello World' of Computer Vision

As Jeremy points out [at the end of lesson 3](https://youtu.be/hBBOjCiFcuo?t=4882), this lesson corresponds to [chapter 4](https://github.com/fastai/fastbook/blob/master/04_mnist_basics.ipynb) of the book. Indeed, it covers very similar topics, but the example used is the light version of the MNIST dataset (which only contains 3s and 7s). Following the recommendation for further research, I [implemented a model for the complete MNIST dataset](https://chrwittm.github.io/posts/2022-11-26-mnist/). As predicted: _"This was a significant project and took you quite a bit of time to complete! I needed to do some of my own research to figure out how to overcome some obstacles on the way"._

After all the previous activities around gradient descent, the actual mechanics of what needed to be done were not too difficult. Nonetheless, I found the competition to be hard, because of the actual technicalities of the python implementation. Put differently, I think I could have easily written a good specification on how to solve the MNIST competition, but actually doing it yourself is a different thing.

Seemingly simple tasks like [converting the csv-files to images](https://github.com/chrwittm/FastAI2022/blob/main/lesson03/mnist/mnist2-kaggle/mnist02-download-and-convert.ipynb), converting a [PIL image to a Fast.AI PIL image](https://github.com/chrwittm/FastAI2022/blob/main/lesson03/mnist/mnist2-kaggle/mnist04-predict-on-csv-file.ipynb), or getting the tensors in the right shape took me some time to implement in python. I am still struggling with python as a language but I am seeing good progress, and the only way to improve is to keep coding.

## Wrapping-up Lesson 3

While I could improve the results of my projects, both for Titanic and MNIST, it feels like it would be some way over-optimizing. I did not enter the competitions to win, but to learn about gradient descent. Having spent the last 8 weeks with my lesson 3-projects (and allowing myself to get somewhat side-tracked), I feel it is time to move on to the next lesson. I am looking forward to the next challenging projects!
