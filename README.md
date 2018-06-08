# UHD-sEMG-database

==========

## A Briefly Description of UHD sEMG Database

------
>>**``UHD is a surface electromyogram (sEMG) signals database, including original sEMG signals, the starting points and the termination points of 13 gestures for 10 subjects. ``**
The predefined 13 subtle finger gestures in 3 different positions are derived from a completely new version of Chinese sign language(CSL), 
which can represent Chinese characters in the form of phonology and radical coded. 
**``These 3 positions are vertical upward, horizontal and vertical, abbreviated as U, H, D, respectively. ``**
For the details of this version CSL, you can refer to the Juan Cheng’s article, named “A novel phonology- and radical coded Chinese sign language recognition framework using accelerometer and surface electromyography sensors”.
[Cheng J, Chen X, Liu A, et al. A Novel Phonology- and Radical-Coded Chinese Sign Language Recognition Framework Using Accelerometer and Surface Electromyography Sensors[J]. Sensors, 2015, 15(9):23303-23324.]

>>``Ten healthy right-handed subjects (7 males and 3 females, with the age of 21.4±1.58 years old) participated in the data acquisition, corresponding to the file S01-S10,``  and each of them signed aninformed consent form. 
**``The sEMG signals of 13 gestures towards 3 positions were collected in 6 days. ``** 
Thus, there are six files E1-E6 and three sub files U, H,D, for each subject, corresponding to six days and three positions for each one. 
At the same time, each sub file has 13 signal data sets, in the form of .mat, representing 13 hand gestures.
![](https://github.com/Fulin-Wei/UHD-sEMG-database/blob/master/picture/handshape.jpg)
![](https://github.com/Fulin-Wei/UHD-sEMG-database/blob/master/picture/gesture.jpg)
These are the predefined 13 gestures and 3 positions.

## Data Acquisition and Preprocessing

==========

>###The Device of Data acquisition and procedure

>>Delsys Trigno Lab Wireless System (Delsys Inc, Boston, USA) was employed to acquire sEMG signals with ``a sampling rate of 1927 Hz.`` According to the neuromuscular control
system, 6 electrode locations were chosen. When collecting 13 hand gestures data for each time, each subject was instructed to perform each gesture (with their palm inward) within each position in the way of “relaxation-contraction-relaxation".
Each gesture execution was lasting about 4 seconds, called a trial, and it took about 80% of the maximum voluntary contraction (MVC) with respect to the hand grasp gesture. For each type of gesture, six trials were collected. 
This procedure was repeated six times during six different days for each subject.
![](https://github.com/Fulin-Wei/UHD-sEMG-database/blob/master/picture/electrode_placement.pdf)
This is an illustration of electrode_placement.

>###Preprocessing

>>For preprocessing and segmentation, ``a seven-order Butterworth band-pass filter, with the band-pass frequency from 20 Hz to 600 Hz,`` was firstly designed to remove the irrelevant external noise and artifacts. 
Then sliding averaging algorithm was used to determine the starting and the ending points of an active segment. In this study, both the onset and the offset thresholds were the same and set as 3 % of the corresponding average energy value, 
which is based on MVC when performing the hand grasp. ``The length of the overlapping sliding window was set as 128
points,`` and the sliding window moved forward one point by one point.
