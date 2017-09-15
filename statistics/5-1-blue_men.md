[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 
```python
from __future__ import print_function, division

import math
import sys
import pandas
import numpy as np
import scipy

import thinkstats2
import thinkplot




def percentile():
    mean = 178 
    stdev = 7.7

    low_cm = 30.48* 5+ 2.54 * 10
    high_cm = 30.48* 6+ 2.54 * 1
    
    low_z = scipy.stats.norm.cdf(low_cm-mean- (stdev))
    high_z = scipy.stats.norm.cdf(high_cm-mean- (stdev))

    print(" Percentage of men in the required bluemen height range:", high_z-low_z)

```
