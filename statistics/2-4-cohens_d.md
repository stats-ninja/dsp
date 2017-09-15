[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)
>>
```python
from __future__ import print_function

import math
import numpy as np

import nsfg
import thinkstats2
import thinkplot



def CohenD():
    """Explore the difference in weight between first babies and others.
    live: DataFrame of all live births
    firsts: DataFrame of first babies
    others: DataFrame of others
    """
    preg = nsfg.ReadFemPreg()

    live = preg[preg.outcome == 1]
    firsts = live[live.birthord == 1]
    others = live[live.birthord != 1]

    assert len(live) == 9148
    assert len(firsts) == 4413
    assert len(others) == 4735


    preg = nsfg.ReadFemPreg()
	
    live = preg[preg.outcome == 1]
    firsts = live[live.birthord == 1]
    others = live[live.birthord != 1]

    assert len(live) == 9148
    assert len(firsts) == 4413
    assert len(others) == 4735
    
 #   mean0 = live.totalwgt_lb.mean()
    mean1 = firsts.totalwgt_lb.mean()
    mean2 = others.totalwgt_lb.mean()

    var1 = firsts.totalwgt_lb.var()
    var2 = others.totalwgt_lb.var()

    print('Mean')
    print('First babies', mean1)
    print('Others', mean2)

    print('Variance')
    print('First babies', var1)
    print('Others', var2)

    n1, n2 = len(firsts.totalwgt_lb) ,len(others.totalwgt_lb)

    
    pooled_var=(n1* var1 + n2* var2)/ (n1 + n2)

    print("Cohen's D", (mean1 - mean2) / math.sqrt(pooled_var))

    

    
    ```
