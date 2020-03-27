[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> Python code used for exercise:

    sample = np.random.random(1000)
    pmf = thinkstats2.Pmf(sample)
    thinkplot.Pmf(pmf)
    thinkplot.Show(xlabel='number',ylabel='probability')
    cdf = thinkstats2.Cdf(sample)
    thinkplot.Cdf(cdf)
    thinkplot.Show(xlabel='number',ylabel='CDF')

![PMF histogram plot](https://github.com/enndy6285/dsp/blob/master/img/4-2%20pmf%20hist.png)
![PMF step plot](https://github.com/enndy6285/dsp/blob/master/img/4-2%20pmf%20step.png)
![CDF plot](https://github.com/enndy6285/dsp/blob/master/img/4-2%20cdf.png)

Explanation:
Initially when plotting PMF, the plot appears empty. This likely occurs since there are an infinite amount of value that can be generated between 0 and 1, the frequency of each value in the sample is low (likely 1 for each). Changing the plot to a step function, we can see the distribution looks normal. This is confirmed with the CDF plot which is a straight line.

