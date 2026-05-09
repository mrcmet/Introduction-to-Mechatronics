## Calibration
Calibration is the act of quantifying both the source of erroneous information and the contribution of those errors on a system or measurement. Specifically we compare a measurement to a known standard and determine the uncertainty in the measurement. 

## Goal of calibration
The goal of calibration falls into one of two categories:
1) An attempt to quantify the error(s) in a measurement or measurement system.
2) An attempt to eliminate noise or interference from a measurement system.

Generally we do the first in order to build a model of the error(s) in a system so that we can do the second. Ultimately the goal is to reduce the errors that make into our measurements and control systems.  

## How we calibrate
The method of calibration differs based on on our goal. In all methods of calibration we compare the measured value to a known standard. We call this a standard value, a reference value, or true value. For analog measurements we often rely on a *calibration standard* or an item that has a true known value, for this we look to standards organizations like NIST.  Unfortunately with discrete measurement we rarely know the true value and instead assume that there is negligible uncertainty in or calibration standard. This often comes in the form of the limit of our measurement systems resolution, or rounding error. 


> [!NOTE] 
> We compare a measurement to a known value, unfortunately we rarely know the actual value. We discount this uncertainty as  negligible. 

### Static calibration
This type of calibration is reserved for independent measurements. Or the measurement of values that don't change with extraneous variables. This includes lengths, temperatures, static forces, masses, etc.. Depending on what we want to measure we can use three different methods

+ Random : This is the act of randomly applying one or more different amplitudes of stimuli and observing an effect for each amplitude.
+ Upscale (sequential): Increasing the amplitude of the stimuli continuously without relief. 
+ Downscale (sequential): We start at the upper limit of stimulus and decrease amplitude with each measurement without relief.
+ Repeated: This is the act of repeating a test at a specific amplitude of stimulus and observing a statistical effect.

### Dynamic calibration
This is the act of calibration for systems where a change in the observed effect is not continuous across one or more codomains. This means the measurement changes with time, temperature, frequency, or other variable. Examples include transients, frequency response measurements, creep. Methods for obtaining these measurements changes based on the quantity to be calibrated, some examples include:

+ Impulse: We expose a system to sudden near instantaneous input and measure the response over a period of time.
+ Frequency sweep: We begin with a low frequency stimuli and increase the frequency to the maximum frequency for which we want to measure a response. (This is often done with equal power over the test frequencies)
+ Time displacement: We provide a constant stimuli over a predefined period of time and measure the response, usually displacement, over the test interval. 

