# Environment

  - macOS Mojave version 10.14.2
  - Anaconda 2018.12 For macOS Installer (Python 3.7 version)
  - Anaconda Navigator 1.9.6
  - conda 4.5.12

# Python3 Code

```python
import scipy
import numpy
import matplotlib
import pandas
import sklearn
import pydot
import h5py

import theano
import tensorflow
import keras

print('scipy ' + scipy.__version__)
print('numpy ' + numpy.__version__)
print('matplotlib ' + matplotlib.__version__)
print('pandas ' + pandas.__version__)
print('sklearn ' + sklearn.__version__)
print('pydot ' + pydot.__version__)
print('h5py ' + h5py.__version__)

print('theano ' + theano.__version__)
print('tensorflow ' + tensorflow.__version__)
print('keras ' + keras.__version__)
```

# Error

```python
---------------------------------------------------------------------------
ImportError                               Traceback (most recent call last)
/anaconda3/lib/python3.7/site-packages/theano/gof/lazylinker_c.py in <module>
     80                     version,
---> 81                     actual_version, force_compile, _need_reload))
     82 except ImportError:

ImportError: Version check of the existing lazylinker compiled file. Looking for version 0.211, but found None. Extra debug information: force_compile=False, _need_reload=True

During handling of the above exception, another exception occurred:

ImportError                               Traceback (most recent call last)
/anaconda3/lib/python3.7/site-packages/theano/gof/lazylinker_c.py in <module>
    104                         version,
--> 105                         actual_version, force_compile, _need_reload))
    106         except ImportError:

ImportError: Version check of the existing lazylinker compiled file. Looking for version 0.211, but found None. Extra debug information: force_compile=False, _need_reload=True

During handling of the above exception, another exception occurred:

Exception                                 Traceback (most recent call last)
<ipython-input-2-23812758ed19> in <module>
      7 import h5py
      8 
----> 9 import theano
     10 import tensorflow
     11 import keras

/anaconda3/lib/python3.7/site-packages/theano/__init__.py in <module>
    108     object2, utils)
    109 
--> 110 from theano.compile import (
    111     SymbolicInput, In,
    112     SymbolicOutput, Out,

/anaconda3/lib/python3.7/site-packages/theano/compile/__init__.py in <module>
     10 from theano.compile.function_module import *
     11 
---> 12 from theano.compile.mode import *
     13 
     14 from theano.compile.io import *

/anaconda3/lib/python3.7/site-packages/theano/compile/mode.py in <module>
      9 import theano
     10 from theano import gof
---> 11 import theano.gof.vm
     12 from theano import config
     13 from six import string_types

/anaconda3/lib/python3.7/site-packages/theano/gof/vm.py in <module>
    672     if not theano.config.cxx:
    673         raise theano.gof.cmodule.MissingGXX('lazylinker will not be imported if theano.config.cxx is not set.')
--> 674     from . import lazylinker_c
    675 
    676     class CVM(lazylinker_c.CLazyLinker, VM):

/anaconda3/lib/python3.7/site-packages/theano/gof/lazylinker_c.py in <module>
    138             args = cmodule.GCC_compiler.compile_args()
    139             cmodule.GCC_compiler.compile_str(dirname, code, location=loc,
--> 140                                              preargs=args)
    141             # Save version into the __init__.py file.
    142             init_py = os.path.join(loc, '__init__.py')

/anaconda3/lib/python3.7/site-packages/theano/gof/cmodule.py in compile_str(module_name, src_code, location, include_dirs, lib_dirs, libs, preargs, py_module, hide_symbols)
   2389             # difficult to read.
   2390             raise Exception('Compilation failed (return status=%s): %s' %
-> 2391                             (status, compile_stderr.replace('\n', '. ')))
   2392         elif config.cmodule.compilation_warning and compile_stderr:
   2393             # Print errors just below the command line.

Exception: Compilation failed (return status=1): In file included from /Users/sangwoon_lee/.theano/compiledir_Darwin-18.2.0-x86_64-i386-64bit-i386-3.7.1-64/lazylinker_ext/mod.cpp:1:. In file included from /anaconda3/include/python3.7m/Python.h:25:. /anaconda3/bin/../include/c++/v1/stdio.h:108:15: fatal error: 'stdio.h' file not found. #include_next <stdio.h>.               ^~~~~~~~~. 1 error generated.. 
```
