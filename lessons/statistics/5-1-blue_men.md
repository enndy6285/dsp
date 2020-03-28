[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> Python code

    import scipy.stats
     
    #create normal distribution
    mu = 178
    sigma = 7.7
    dist = scipy.stats.norm(loc=mu, scale=sigma)

    # Calculate amount of people between height 5'10" and 6'1"
    max_height_cm = (6*12 + 1) * 2.54
    min_height_cm = (5*12 + 10) * 2.54
    dist.cdf(max_height_cm) - dist.cdf(min_height_cm)
    
Answer: about 34% of the US population falls within the required height range

Explanation: We can estimate the answer by finding the difference in CDF between the upper and lower height parameters
