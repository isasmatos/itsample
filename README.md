# inverse-transform-sample v1.0
 
inverse-transform-sample is a simple Python implementation of a technique that allows for sampling from arbitrary probability density functions.
 
## Installation
 
To install, do

	git clone https://www.github.com/peterewills/itsample /path/to/itsample
 
## Usage

To use the package, you must add its location to your Python path. This can be done within the interpreter as follows

	>> import sys
	>> sys.path.append('/path/to/itsample')
	
The sampler can the be used as follows:

	>> import numpy as np
	>> pdf = lambda x: np.exp(-x**2/2) # unit Gaussian, not normalized
	>> from itsample import sample
	>> samples = sample(pdf,1000) # generate 1000 samples from pdf
	
For more details, see `example.ipynb`.

## Notes

Inverse transform sampling is slow; the example above takes ~3 ms per sample, or ~3 seconds to generate 1000 samples. Computational simplicity is emphasized here; although more computationally efficient approaches to inverting the CDF exist, we opt for the one that is the simplest to code. If one wishes to generate over 100,000 samples, then this library will be prohibitively slow (although adaptations to parallelize the functionality would be quite simple to implement).
 
## Contributing
 
1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :+1:
 
## Credits
 
Author: Peter Wills (peter@pwills.com)
 
## License
 
The MIT License (MIT)

Copyright (c) 2017 Peter Wills

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
