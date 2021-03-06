# py-rbm

This is a small Python library that contains code for using and training
Restricted Boltzmann Machines (RBMs), the basic building blocks for many types
of deep belief networks. Variations available include the "standard" RBM (with
optional sparsity-based hidden layer learning); the temporal net introduced by
[Taylor, Hinton & Roweis][]; and convolutional nets with probabilistic
max-pooling described by [Lee, Grosse, Ranganath & Ng][].

Mostly the code is being used for research in our lab. Hopefully others will
find it instructive, and maybe even useful !

[Taylor, Hinton & Roweis]: http://www.cs.nyu.edu/~gwtaylor/publications/nips2006mhmublv/
[Lee, Grosse, Ranganath & Ng]: http://cacm.acm.org/magazines/2011/10/131415-unsupervised-learning-of-hierarchical-representations-with-convolutional-deep-belief-networks/fulltext

## Installation

Just install using the included setup script :

    python setup.py install

Or you can install the package from the internets using pip :

    pip install lmj.rbm

## Testing

This library is definitely very alpha; so far I just have one main test that
encodes image data. To try things out, first install glumpy :

    pip install glumpy

Then run the test :

    python test/images.py /path/to/my/images*.jpg

If you're feeling overconfident, go ahead and try out the gaussian visible
units :

    python test/images.py \
      --batch-size 257 \
      --l2 0.0001 \
      --learning-rate 0.2 \
      --momentum 0.5 \
      --sparsity 0.01 \
      --gaussian /path/to/my/images*.jpg

The learning parameters are squirrely, but if things go right you should see a
number of images show up on your screen that represent the "basis functions"
that the network has learned when trying to auto-encode the images you are
feeding it.

Please fork and contribute if you find this code at all useful !

[glumpy]: http://code.google.com/p/glumpy/

## License

(The MIT License)

Copyright (c) 2011 Leif Johnson <leif@leifjohnson.net>

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the 'Software'), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
