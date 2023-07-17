# Aarav Jain - Image Recognition with Raspberry Pi
Welcome to my image recognition project! Using the OpenCV library, I've created a system achieving three milestones. In my initial breakthrough, I used a a simple OpenCV cascade classifier for image detection. The second milestone truly showcases the wonders of OpenCV, as it identifies objects placed in front of the camera and outlines and labels them precisely. However, my most complex and greatest achievement lies in the third milestone, where the camera, upon detecting a person, sends me an email with a personalized message and an attached picture of the identified individual.


| **Name** | **School** | **Field** | **Grade** |
|:--:|:--:|:--:|:--:|
| Aarav J | Amador Valley High School | Electrical Engineering and Computer Science | Incoming Junior

**Replace the BlueStamp logo below with an image of yourself and your competed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone : Simple Image Detection Using OpenCV

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>                                                                  

**-------------------------------------------------------------------------------------------------------------------------------------------------------**


First, I assembled my Raspberry Pi into its case, wired up its fan, and connected the ArduCam. Then I opened the terminal and expanded the necessary libraries for image recognition. The two most significant libraries were Tensorflow Lite and OpenCV. TensorFlow is open-source software for machine learning and artificial intelligence, but I installed TensorFlow Lite as it was more compatible with smaller Edge devices such as my Raspberry Pi 4B. After installing everything, I could complete a simple image detection using OpenCV. However, I ran into some problems. Though OpenCV was installed completely ad successfully, when I tried to import the library into my code. I redownloaded OpenCV multiple times with multiple different versions of it, but the error was persistent. After a few days, I installed OpenCV on another computer, and importing OpenCV also worked. Then, I wrote code that used a Cascade Classifier object from OpenCV to complete an image detection for faces.

![Headstone Image](faces.png)

# First milestone code : Image detection with OpenCV
This preliminary code uses the libraries OpenCV(import cv2) and matplotlib, specifically pyplot(from matplotlib import pyplot as plt), to detect faces within a frame. The code first uses OpenCV to read an image, then converts the image to a grayscale and then an RGB format. It then creates a Cascade Classifier, a model trained on data consisting of positives(where the target is detected) and negatives(without the target). Once this Cascade Classifier finds a face, the code uses OpenCV to create a rectangle around the face that was identified. Then pyplot is used to display the image with completed detection. I also modified the Cascade classifier to detect stop signs in an image, which was also successful.

```c++
import cv2
from matplotlib import pyplot as plt
img = cv2.imread("street_with_people.jpg")
img_gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
stop_data = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
found = stop_data.detectMultiScale(img_gray,minSize =(20, 20))
amount_found = len(found)
if amount_found != 0:
	for (x, y, width, height) in found:
		cv2.rectangle(img_rgb, (x, y),(x + height, y + width),(0, 255, 0), 5)
plt.subplot(1, 1, 1)
plt.imshow(img_rgb)
plt.show()

```
# Second milestone code
goober.

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```
# Third milestone code
goober.
```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

# What you need:
All you need for an image recognition project like this is a computer compatible with Python 3.6 or later(for OpenCV), which should have a working camera. A cheap option for this would be a Raspberry Pi 4 B, which can handle a library like OpenCV.

| **Part** | **What the item is used for** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Raspberry Pi 4B Kit | Main computer that runs all code along with its peripherals | $129.99 | <a href="https://www.amazon.com/CanaKit-Raspberry-Pi-Starter-Kit/dp/B07V2B4W63/ref=sr_1_6?crid=2JJGD2DHT0K12&keywords=canakit+raspberry+pi+4&qid=1689089184&sprefix=canakit%2Caps%2C696&sr=8-6"> Link </a> |
| Arducam 5MP camera for Raspberry Pi | Vision System for main computer | $9.99 | <a href="https://amazon.com/Arducam-Megapixels-Sensor-OV5647-Raspberry/dp/B012V1HEP4/ref=sr_1_4?crid=1JGGZIPZ3VMI&keywords=arducam+5mp+camera+for+raspberry+pi&qid=1689089428&sprefix=%2Caps%2C215&sr=8-4"> Link </a> |



