[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Python code adapted from "Think Stats",
by Allen B. Downey, available from greenteapress.com

Copyright 2014 Allen B. Downey
License: GNU GPLv3 http://www.gnu.org/licenses/gpl.html
"""

    from __future__ import print_function

    import sys
    from operator import itemgetter

    import first
    import thinkstats2
    import math

    def CohenEffectSize(group1, group2):
        diff = group1.mean() - group2.mean()
        var1 = group1.var()
        var2 = group2.var()
        n1, n2 = len(group1), len(group2)

        pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
        d = diff / math.sqrt(pooled_var)
        return d

    def WeightDifferences(live, firsts, others):
        """Explores the differences in birth weight between first babies and others"""
    
        mean_diff = firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()
        cohen = CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
    
        return mean_diff, cohen

    def main(script):
        """Tests the functions in this module.

        script: string script name
        """
        live, firsts, others = first.MakeFrames()
        hist = thinkstats2.Hist(live.prglngth)
    
        print('Difference in mean weight: ', WeightDifferences(live,firsts,others)[0])
        print('Cohen D: ', WeightDifferences(live,firsts,others)[1])
    
        print('%s: All tests passed.' % script)


    if __name__ == '__main__':
        main(*sys.argv)

