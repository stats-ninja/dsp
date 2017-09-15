[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> ```python
import random
import thinkstats2
import thinkplot


def uniform():

    count=0

    random_list=[]

    for number in range(0,1000):
        y=random.random()
        random_list.append(y)
        
    # plotting CDF
    """cdf= thinkstats2.Cdf(random_list, label='random_numbers')

    thinkplot.Cdf(cdf)
    thinkplot.Show(xlabel='random_numbers', ylabel='CDF') """

    # Plotting Pmf
    pmf = thinkstats2.Pmf(random_list, label='random_numbers')
    
    thinkplot.Pmf(pmf)
    thinkplot.Show(xlabel='random_numbers', ylabel='PMF')

    ```
