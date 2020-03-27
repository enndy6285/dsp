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

    def main(script):
        """Tests the functions in this module.

        script: string script name
        """
        live, firsts, others = first.MakeFrames()
        hist = thinkstats2.Hist(live.prglngth)
        
        print('Difference in mean birth weight: ', firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean())
        print("Cohen's d: ", CohenEffectSize(firsts.totalwgt_lb,others.totalwgt_lb))
    
        print('Difference in mean pregnancy length: ', firsts.prglngth.mean() - others.prglngth.mean())
        print("Cohen's d: ", CohenEffectSize(firsts.prglngth,others.prglngth))
     
        print('%s: All tests passed.' % script)


    if __name__ == '__main__':
        main(*sys.argv)

Explanation:
Running the code above, the difference in mean birth weight between first babies and others is -0.125 lbs. The Cohen's d is -0.089. This is an opposite relationship compared to differences in pregnancy length. The Cohen's d for birth weight is also larger than the Cohen's d for pregnancy lenght, suggesting a greater effect size.
