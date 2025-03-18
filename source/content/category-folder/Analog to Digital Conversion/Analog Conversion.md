
# Discretization

Before we can discuss the idea for analog to digital conversion we must first discuss what it means to discretize an amplitude. We have discussed the idea of [[Discretization]] in the past in regards to sampling in the time domain, and many of these ideas still carry over. The ultimate goal is to subdivide a continuous range of values into specific quantities. Thus the act of making something discrete. 

# Classical Methods 

Before jumping into the digital side of systems let's take a look at what ye-oldie engineers used to use for recording data. This is best represented by the traditional, and occasionally still used, [[Strip Charts]]. 
There is still one major problem with this classical system. What happens when your boss askes you to find the amplitude of a signal at 4:45PM on a Friday? You would do what any other engineer would do, grumble and pull out your handy pocket scale. You would measure the height of the signal form some baseline, record this number and multiply it by some known scale factor. In doing this process you have unknowingly committed the arduous task of discretization.
It's important to remember for later that the simple act of taking a measurement forces a infinite value into a finite value, and at the same time introduces an error. In the case of our scale this error is simple to calculate error is half of the smallest increment on our scale.

## The problem
This is all well and good when the boss asks for one value form the strip chart. What happens when you need to look for 3 points, or 30 points, or 300 points? This can result in more than a quick stop to grumble on the way out the door. So what is an engineer to do?
 Well, since we have a verity of transducers that can convert mechanical to electrical signals perhaps we can bring technology to our advantage. It's at this point that the next problem arises, how do we find the discrete value of an electrical signal? 

# The Digital Solution

## Signal Measurements
How do we find the value of an electrical signal? Well first we need to decide the signal characteristic we want to measure. Since most electrical measurement are just some form of voltage measurement in disguise we can start with voltage. Let's assume that we have a simple device that can make a comparison between two voltages; a mystery voltage and a threshold voltage. 

then we know we have at least that many volts, we can then try a higher voltage to compare to and note if we have a success. We can continue this process until we reach a voltage where the mystery voltage is no longer higher than the comparison voltage.   

