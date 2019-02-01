# Installing NeuroNER requirements on Mac OS X

NeuroNER requires Python 3.6 or later. You may choose to handle a package like Anaconda to help manage dependencies.

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

To install BRAT (optional, you just need it if you want to easily create, change or view the annotations):

```
mkdir brat
cd brat
wget http://weaver.nlplab.org/~brat/releases/brat-v1.3_Crunchy_Frog.tar.gz
tar xzf brat-v1.3_Crunchy_Frog.tar.gz
cd brat-v1.3_Crunchy_Frog
./install.sh -u

# To run BRAT (requires Python 2.5, 2.6 or 2.7):
python standalone.py
```

BRAT should now be accessible through the web browser at [http://127.0.0.1:8001](http://127.0.0.1:8001).

You can now run NeuroNER.
