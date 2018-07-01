[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> Using the variable `totalwgt_lb`, investigate whether first babies are lighter or heavier than others. 

Compute Cohen’s effect size to quantify the difference between the groups.  How does it compare to the difference in pregnancy length?

# Solution goes here
firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()
#-0.12
#statement: on average first babies are lighter than the average for others

# Solution goes here
print(CohenEffectSize(firsts, others).totalwgt_lb)
print(CohenEffectSize(firsts, others).prglngth)

For the next few exercises, we'll load the respondent file:

resp = nsfg.ReadFemResp()
#print(resp['totincr'])

Make a histogram of <tt>totincr</tt> the total income for the respondent's family.  To interpret the codes see the [codebook](http://www.icpsr.umich.edu/nsfg6/Controller?displayPage=labelDetails&fileCode=FEM&section=R&subSec=7876&srtLabel=607543).

# Solution goes here
hist = thinkstats2.Hist(resp.totincr, label='total income')
thinkplot.Hist(hist)
thinkplot.Config(xlabel='dollars', ylabel='Count')

Make a histogram of <tt>age_r</tt>, the respondent's age at the time of interview.

# Solution goes here
hist = thinkstats2.Hist(resp.age_r, label='age')
thinkplot.Hist(hist)
thinkplot.Config(xlabel='years old', ylabel='Count')

Make a histogram of <tt>numfmhh</tt>, the number of people in the respondent's household.

# Solution goes here
hist = thinkstats2.Hist(resp.numfmhh, label='household size')
thinkplot.Hist(hist)
thinkplot.Config(xlabel='persons', ylabel='Count')

Make a histogram of <tt>parity</tt>, the number of children borne by the respondent.  How would you describe this distribution?

# Solution goes here
hist = thinkstats2.Hist(resp.parity, label='num of birth children')
thinkplot.Hist(hist)
thinkplot.Config(xlabel='children', ylabel='Count')
#i would describe this dist as skewed towards the right

Use Hist.Largest to find the largest values of <tt>parity</tt>.

# Solution goes here
#import dictionary
#highest = []
for kids, freq in hist.Largest(10):
    print(kids, freq)

Let's investigate whether people with higher income have higher parity.  Keep in mind that in this study, we are observing different people at different times during their lives, so this data is not the best choice for answering this question.  But for now let's take it at face value.

Use <tt>totincr</tt> to select the respondents with the highest income (level 14).  Plot the histogram of <tt>parity</tt> for just the high income respondents.

# Solution goes here
#print(resp.totincr)
#highest = []
#for x in range(0, len(resp.totincr)):
    #print(resp.totincr[x])
#    if resp.totincr[x] == 14:
#        highest.append(x)

highest = resp[resp.totincr == 14]

#print(highest)

hist = thinkstats2.Hist(highest.parity, label='num of birth children')
thinkplot.Hist(hist)
thinkplot.Config(xlabel='children', ylabel='Count')


Find the largest parities for high income respondents.

# Solution goes here
for kids, freq in hist.Largest(10):
    print(kids, freq)

Compare the mean <tt>parity</tt> for high income respondents and others.

# Solution goes here
not_rich = resp[resp.totincr < 14]
print(highest.parity.mean() - not_rich.parity.mean())
#print(resp)

Compute the Cohen effect size for this difference.  How does it compare with the difference in pregnancy length for first babies and others?

# Solution goes here
highest = resp[resp.totincr == 14]
#print(highest)
#print(resp)
print(CohenEffectSize(highest, not_rich).parity)
#-0.12511855314660611 is a stronger difference than the difference in preg len for first v others
