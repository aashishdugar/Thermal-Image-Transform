# Thermal-Image Transform
Tranforming video capture from an FLIR to selective thermal object viewing.

The motivation behind this project was to implement thermal image capture on a drone for solar panel testing.

In the simple sense, it takes the thermal image, and the coordinates with the lowest rgb values, i.e the least intense are converted to an ironblack colormap whereas the remaning are left as is, thereby highlighting a select amount of the hottest object on the frame.

There is a primitive technique used here to enhace the size of the window, called linear scaling. By altering the range of operation for the frame to a larger scale, we are able to get a bigger display. However, this is just pixel resizing and isnt a very high level technique. It was done as the FLIR camera the team implemented had a very low resolution.

### Requirements
* FLIR Thermal Camera(or any thermal camera with similar image output)
* Open-CV 2.x


### To run
Running it is fairly straightforward, the code has been hardcoded with the port that it connected to on my laptop. This has to be altered based on the port it connects to on yours. For example, my port was called "COM5" therefore the following line was fit in that way-
`Serial ser("COM5", 115200, Timeout::simpleTimeout(1000));`

Once changes, simply compile with `g++` and run.
Settings such a the timeout,windowsize etc. have all been hardcoded. They can be changed accordingly. However, this may ruin the resolution if being upscaled to a very high res.

