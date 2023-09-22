# A/B and How to be
A/B testing is an way to compare multiple variants and see which one perform better. Data engineering may be involved with everything from instrumentation and tracking to analysis. 

Here is few things that should be kept in mind before doing A/B testing:

### Sample size
If the experiment is 50/50, sample sizes should be close to one another. For another split, validate the sample size against the expected weight.

### Start and stop date (with any ramp-up weight)
The experiment should be slowely rolled out in the ladder, from 1%, 5%, 10%, ..... to avoid adverse impact as the experiment may have bug (in design, randomization, etc). 

### User in both groups
If an user is fed with both control group and experiment, the use to be excluded from the experiment. If this take place in wide-spread, the experiment to be redesigned. 

### Context-specific restriction
Depending on the experiment, there might be some restriction to select users on same group.


After making changes in experiment backend process, it's better to run A/A test first to gain some result and test whether the system if working as expected or not. 

