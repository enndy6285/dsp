[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> Python code for exercise

    resp = nsfg.ReadFemResp()
    #creating actual PMF
    pmf = thinkstats2.Pmf(resp.numkdhh,label='actual')

    #creating biased PMF
    bias_pmf = pmf.Copy(label='observed')
    for x, p in pmf.Items():
        bias_pmf.Mult(x,x)
    bias_pmf.Normalize()

    #plotting both PMFs
    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf,bias_pmf])
    thinkplot.Show(xlabel='# of children',ylabel='PMF')

![PMF histogram](https://github.com/enndy6285/dsp/blob/master/img/2-01%20exercise.png)
