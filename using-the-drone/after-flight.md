# After-Flight

## 1. Download Images

1. Start by pressing "Download Drone images" on Groundstation Laptop
2. Enter dronename
3. Leave cam prefix empty
4. Two windows should appear - each for one camera / pi in the plane

![](../.gitbook/assets/image%20%288%29.png)

## 2. Image analysis

* While image download is running, start analysis of the images while they get downloaded
* There are different algorithms available to analyse the images 
  * Classify Images: Shows whether a image includes a boat but not where it is
    * EfficientNet
  * Detect Boats: Shows where in the image a boat is located
    * FRCNN
    * RetinaNet

{% hint style="info" %}
Be aware that only one analysis run / algorithm can run at a time - please close all open old analysis runs!
{% endhint %}

### Start analysis

1. Start analysis by clicking the corresponding desktop icon
2. Choose the currently downloaded images of the plane according to planename and timestamp from _/home/searchwing/flightdata/_
3. Press "OK"
4. All current and live added images to the folder will now be processed
5. Current progress and left over time can be observed

![](../.gitbook/assets/image%20%2816%29.png)

![](../.gitbook/assets/image%20%2812%29.png)

### Suggestion on how to process on new flight data \(Best practice!\)

1. Start "Image Classification" as it is the fastest 
2. Wait until Download and classification is finished and close "Image Classification" 

   window

3. Start "Detect Boats \(Retina\)" as its more accurate than classification but takes longer

## 3. Observe images

1. Start GUI via desktop icon - The browser should open
2. Select / click the currently downloaded image data
3. Read "Help" to get more usability info

   1. Use Arrowkeys to browse images
   2. Sort images using "DateTime" or "Algorithm"
   3. Press "Shift"-Key to temporarily hide Analysis Run Boxes
   4. Press "Enter"-Key to mark image as viewed and go to next image
   5. Press "Space"-Key to mark image as interesting / that there is REALLY a boat
   6. Current GPS Position is shown in the top bar
   7. Press "&lt;back" to choose a different flight dataset

![](../.gitbook/assets/image%20%287%29.png)

![](../.gitbook/assets/image%20%289%29.png)

![](../.gitbook/assets/image%20%2814%29.png)

{% hint style="info" %}
If the GUI is already running and you try to open it up again a message will appear wheather you want to open the GUI at another port. Dont press "Y" but instead open the browser and open the GUI via typing in "localhost:3000".
{% endhint %}

## 4. Recharge Battery

* Plug in charging cable
* Use predefined setting for the drone

## \(optional\) Download log file

* Download the log file via scp

## 5. Turn off systems

* UAV / drone
* Remote control
* QGC / tablet

## 6. Documentation

* Get flight log / book
* Is goal reached
* Not problems

## \(optional\) Cleaning the drone

{% hint style="info" %}
If drone is not used anymore within the next hours cleaning is needed!
{% endhint %}

### Clean motor using sweetwater

