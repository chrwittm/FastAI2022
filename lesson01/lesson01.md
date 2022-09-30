# Lesson 1 of Fast.AI 2022 Edition

The first lesson is very much about "playing the whole game" (insert link): Without going into any details, we are creating a computer vision classifier - isn't that cool!

## My learning approach

After watching the [video](https://www.youtube.com/watch?v=8SF_h3xF3cE),

* My first exercise was to play with Jeremy'a notebook "[Is it a bird?](https://www.kaggle.com/code/jhoward/is-it-a-bird-creating-a-model-from-your-own-data)". After running it on the Kaggle platform, I also ran it on my local computer, here is the resulting [notebook](/lesson01/bird_or_not/is-it-a-bird.ipynb)
* To go beyond the "Is it a bird?"-notebook, I decided to build a model which can identify if a picture shows a cat or a dog. Somehow I felt, that is a mandatory exercise for a ML student ;). Here is the resulting notebook: "[Is it a cat or a dog?](/lesson01/cat_or_dog/cat_or_dog.ipynb)".

Anything beyond that, I postponed to later, knowing that the course will dig deeper in the next lessons anyway.

## Lessons learned

The actual implementation in analogy was not too hard, but there were some challenges on the way. Here are some of my learnings:

* "Cat or Dog" is more difficult than "Bird or Forest": I had to experiment a bit with the dataset until it really produced good results, i.e. to get the test images to be classified with enough confidence.
* Using my local machine for development and training is a challenge of its own. No wonder that Jeremy had discouraged students from working locally in the previous version of the course. <br> While doing the "Is it a bird?-exercise, somehow I had the idea that I needed to update pytorch, which I seem to have messed up big time (not knowing exactly why...). Anyway, after a bit of trial and error, I decided to re-install my python installation. Sounds difficult? <br> Actually not! The [Live Coding Video 1](https://youtu.be/56sIyFjihEc), the [forum notes](https://forums.fast.ai/t/live-coding-1/96649), and [FastSetup](https://github.com/fastai/fastsetup) made this really easy. Since I had watched the video before, I was up and running again less than 30 minutes.
* I work with WSL, but the git repos still reside in Windows on OneDrive. This has so far proven to be very useful
  * I like to write markdown in VS Code, because it also has a spellchecker.
  * When my WSL instance was in trouble, I never worried about the git repos.
