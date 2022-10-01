# Lesson 2 of Fast.AI 2022 Edition

Lesson 2 focused on publishing the model (putting things in production).

[Forum Official Topic](https://forums.fast.ai/t/lesson-2-official-topic/96033/1)

## Re-publishing the Bear Detector

After watching the [video](https://www.youtube.com/watch?v=F4tvM4Vb3A0), I worked on my old [bear detector](https://github.com/chrwittm/Bear-Detector) which I created about a year ago (on the previous version of the course / based on the book): Since I have kind of done the training before (i.e. last year), instead of re-visiting that, I first wanted to publish my old model using HuggingFace spaces, because I still remember quite vividly that is was quite difficult to publish last year, failing with Voila, finally doing it Heroku. Additionally, the Heroku free services will also be retired later this year.

### Jumping ahead: The final result

So here it is, the [New Bear Detector](https://huggingface.co/spaces/chrwittm/bear-detector) on HuggingFaces.

All the files are located in the `bear_detector` subfolder, most notably, the [notebook](/lesson02/bear_detector/app.ipynb) which I used to generate the content which I uploaded to HuggingFace.

### How I Re-published the Bear Detector

So I restarted the video at the point where we [publish on HuggingFace](https://www.youtube.com/watch?v=F4tvM4Vb3A0&t=1638s), jumping in the [Gradio + HuggingFace Spaces Tutorial](https://tmabraham.github.io/blog/gradio_hf_spaces_tutorial).

In addition to the video lecture, the following things turned out to be important.

### Learning 1: Installation

The installation of the following packages was necessary on my local machine:

* gradio: `pip install gradio`
* nbdev: `mamba install -c fastchan nbdev`

### Learning 2: Gradio

This piece of code produces warnings:

```python
image = gr.inputs.Image(shape=(192,192))
label = gr.outputs.Label()
```

Instead, the image and the label needs to be instantiated like this:

```python
image = gr.components.Image(shape=(192,192))
label = gr.components.Label()
```

### Learning 3: Exporting the app.py file

The way to export the app.py file does not work anymore the same way it is shown in the video.

This piece of code does not work anymore:

```python
import notebook2script from nbdev.export
notebook2script('app.ipynb')
```

Instead, this is the way to export the code:

```python
from nbdev import nbdev_export
nbdev_export('app.ipynb')
print('Export successful')
```

> Note: Additonally the export only works it the notebook is in a folder called `nbs`.

### Learning 4: Adding requirements.txt

You also need to create a requirements.txt file with the following content:

```python
fastai
scikit-image
```

### Learning 5: Uploading binaries to GitHub

First I cloned my repo:

```bash
git clone https://huggingface.co/spaces/chrwittm/bear-detector
```

The first attempt to upload my `pkl`-file was not successful, because it is a binary:

```
remote: -------------------------------------------------------------------------
remote: Your push was rejected because it contains binary files.
remote: Please use https://git-lfs.github.com/ to store binary files.
remote: See also: https://hf.co/docs/hub/repositories-getting-started#terminal
remote: -------------------------------------------------------------------------
remote: Offending files:
remote:  - export.pkl (ref: refs/heads/main)
```

This kind of upload needs to be done with Git Large File Storage ([LFS](https://git-lfs.github.com/)). To install it in Ubuntu, the following steps are necessary as described [here](https://efrecon.github.io/git-lfs-on-ubuntu/):

```bash
curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | sudo bash
```

```bash
sudo apt-get install git-lfs
```

```bash
git lfs install
```

Afterwards, the files can be added and pushed to git:

```bash
git lfs track "*.pkl"
git add .gitattributes
git add export.pkl
git add app.py
git add blackbear.jpg
git add teddybear.jpg
git add grizzly.jpg
git commit -m "uploaded app"
git push
```

### The final result on HuggingFace

So here it is, the [New Bear Detector](https://huggingface.co/spaces/chrwittm/bear-detector) on HuggingFaces.
