Reason why unlocking frames above 30 is causing problems is caused by engine's assumption that framerate is constant. (Tickrate is 20Hz, so each frame is 50ms long.) So when you unlock framerate, then everything which is using this assumption is accelerated. 

List:
* `m_FrameCounter` inside `cAudioManager`


***

### User reported things
niobium93  
The water splashes behind boats, splashes when driving through puddles and smoke coming off of damaged cars renders wrong without the frame limiter. Smoke also disappears when driving fast and I swear once I couldn't even see the flames before my car exploded, though I can't reproduce that.  
[Video with giant water splash effects behind boats](https://www.youtube.com/watch?v=V5NLizJ7YLw)  
[Video with a smoking car](https://www.youtube.com/watch?v=_rzZE5W-LwI)