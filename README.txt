What's this?
This a HTC Vive program that demonstrates an alternative tracking method using a Vive Tracker. 


Why Tracking with a Tracker?
Normally, you need two base stations to get tracking without blind angle - if there's only one, you'll possibly lose tracking after turning your back on it. If you have a Vive tracker, however, you can get complete tracking with just one base station using the following techniques. 


The Quickest Way to Have a Try:

1.Download this github project and open the folder with Unity 5.3.7 (must be 5.3 because camera tracking was moved to the engine level in Unity 5.4)

2.Connect a tracker to your PC, and then physically attach it to your HMD.

3.Click play and then block the HMD with your clothes. See how the game view moves with the tracker instead of the HMD.


Key Tricks Explained:
1.Turn off "forceFadeOnBadTracking" in steamvr config files, or in this case, using openvr api (you can find how I did it by searching "forceFadeOnBadTracking" in the IDE or refering to the git commit history). This prevents the HMD from going "gray".
2.When the tracking is bad, set the tracker as the camera's parent object, making the camera's movement follow the tracker's.


Improvements to Be Made:
*If you have tried this program, you'll know that the transition is not that smooth. You'll feel that the screen shakes at the transition between the two tracking methods. This is because openvr uses a prediction method which makes it report bad tracking only after the signal has been out for several frames. 
 To solve it, I recommend you to switch tracking methods when the angle between the HMD and the base station passes a threshold that depends on your setup(at this point the player is turning back on the base station), not when the system tells you the tracking is bad. 


Contact Me:
james_xiong@htc.com
