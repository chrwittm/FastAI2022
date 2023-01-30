# Lesson 4

Re-working [Fast.AI lesson 4](https://forums.fast.ai/t/lesson-4-official-topic/96441), I transferred the approach from Jeremy's notebook "[Getting started with NLP for absolute beginners](https://www.kaggle.com/code/jhoward/getting-started-with-nlp-for-absolute-beginners)" to the Kaggle competition "[Natural Language Processing with Disaster Tweets](https://www.kaggle.com/competitions/nlp-getting-started)".

When I started this project, I did not expect it to become such an extended endeavor. It introduced me to many different aspects of natural language processing in particular and machine learning in general. To share what I learned with the community, I recorded my approach and the key learnings [in this blog post](https://chrwittm.github.io/posts/2023-01-17-nlp-with-disaster-tweets/).

In the spirit of producing results quickly and training models early in the development process:

* I started by creating a [baseline-notebook](https://www.kaggle.com/code/christianwittmann/nlp-with-disaster-tweets-baseline) in which I used the same approach as presented in the lecture, porting it pretty much 1:1.
* In the [final iteration](https://www.kaggle.com/code/christianwittmann/nlp-with-disaster-tweets-january-2023) (so far), I have incorporated quite a few "upgrades". Which resulted in a score of 0.84676 and out me almost at the top of the leaderboard.

The key learnings:

* Cleaning the data helps, both syntactically and semantically.
* Upon cleaning the data, keep a close eye on what is noise and what is signal.
* Helping the model understand the data helps by using special tokens.
* Using bigger models helps. However, for training large models on Kaggle, you need to apply some tricks not to run out of memory.
* Small batch sizes help.
* Showing the model more data then just the initial training set helps.

More details are [in my blog post](https://chrwittm.github.io/posts/2023-01-17-nlp-with-disaster-tweets/).

Just when I thought I was done with disaster tweets, I realized I forgot a topic I wanted to cover. In [a new notebook version](https://www.kaggle.com/code/christianwittmann/nlp-with-disaster-tweets-january-2023), I implemented a confusion matrix to find tweets which are incorrectly labeled in the training set - basically the same approach as looking for top losses (for example in lesson 2).

I was indeed successful in finding quite a few incorrectly labeled tweets, but (surprisingly) this did not result in a better overall competition result - from my understanding this is a limitation of the dataset. I summarized the full story and my learnings [in this blog post](https://chrwittm.github.io/posts/2023-01-27-disaster-tweet-dataset-limitations/).

Summing it all up, I also write this [kaggle discussion forum post](https://www.kaggle.com/competitions/nlp-getting-started/discussion/382236).