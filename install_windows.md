# Installing NeuroNER requirements on Microsoft Windows

NeuroNER requires Python 3.6 or later. You may choose to handle a package like Anaconda to help manage dependencies. These instructions are tested on Windows 7 SP1 64-bit.

## Table of Contents

<!-- toc -->

- [Python, TensorFlow, and several other Python packages](#python-35-and-tensorflow)
- [Perl](#perl)
- [TensorBoard](#tensorboard)

<!-- tocstop -->

## Python, TensorFlow, and several other Python packages
First, install Python 64-bit and TensorFlow following these instructions: [How to install TensorFlow on Windows?](http://stackoverflow.com/a/39902815/395857)

Then, from the command prompt (make sure `pip` is connected to Python 3. You can verify it by running `pip -V`):

To install NeuroNER:

```
# For CPU support (no GPU support):
pip3 install neuroner[cpu]

# For GPU support:
pip3 install neuroner[gpu]
```

Note that for GPU support, [GPU requirements for Tensorflow](https://www.tensorflow.org/install/) must be satisfied.

You will also need to download the English language module for Spacy:

```
# Load the Spacy English module
python -m spacy download en
```

## Perl

You also need to install Perl, because the official CoNLL-2003 evaluation script is written in this language: http://strawberryperl.com

Make sure the `perl.exe` binary is in your `Path` system environment variable:

![](http://neuroner.com/perl2.png "")

<!---

To add perl in your `Path` system environment variable:

![](http://neuroner.com/perl.png "")

!-->

## BRAT (optional)

Installing BRAT is optional: it is only needed to easily create, change or view the annotations. BRAT does not run natively on Microsoft Windows, however it runs smoothly on [Cygwin](https://www.cygwin.com). After installing Cygwin, run `Cygwin.bat` (by default located on `C:\cygwin64\` if you used the 64-bit installation for Cygwin). Then, in the terminal that just opened, run:

```
mkdir brat
cd brat
wget http://weaver.nlplab.org/~brat/releases/brat-v1.3_Crunchy_Frog.tar.gz
tar xzf brat-v1.3_Crunchy_Frog.tar.gz
cd brat-v1.3_Crunchy_Frog
./install.sh -u
python standalone.py
```

BRAT should now be accessible through the web browser at [http://127.0.0.1:8001](http://127.0.0.1:8001).

## TensorBoard (optional)

The `tensorboard.exe` binary should also be in your `Path` system environment variable, if you plan to use TensorBoard (optional).

You can now run NeuroNER.