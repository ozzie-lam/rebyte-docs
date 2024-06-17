# Quick Start

We will show to how to build a simple weather app using the customized UI.

## Step 1: Create an App

* Navigate to the "My Apps" tab in the sidebar and then click on "Create App" on the top right.

* Choose "App With Customized UI".

* To build a basic version of your app, you can use the "image prompt" or the "text prompt". 

* The "image prompt" is to draw the app on the canvas. You can use the tools on the bottom to draw a basic draft of your app interface.

<figure><img src="../../images/cui-1.png"></figure>
  
* Choose the drawings on your canvas and click the "Make It An App" button when you are finished.

<figure><img src="../../images/cui-2.png"></figure>
  
* Input "the "text prompt" to further describe the app using texts. 

<figure><img src="../../images/cui-3.png"></figure>

* Click the "Make It An App" button to build the app.


## Step 2: Design you App

* After the first step, you should be able to see the first draft of your app.

<figure><img src="../../images/cui-4.png"></figure>

* You can make changes to the app by using the "image prompt" or "text prompt". It's just like the first step.

* To use image prompts, use the boxes, arrows and the texts to draw the changes you want to make on the canvas.
  
* To use the text prompt, click the "Make It An App" and input the text prompt describing the changes you want to make.

* Click "Make It An App" again and we will make changes for you based on your prompt and create a new version of your app.

* **NOTE**: This may not give you the desired results on just one try. We recommend you to try and improve one thing at a time and create more versions until you get the best results.

## Step 3: Connect your App with Tool

* Click the "Connect to Tool" on the top right.

<figure><img src="../../images/cui-5-1.png"></figure>

* Choose the agent you want to connect with and select the version.

<figure><img src="../../images/cui-5-2.png"></figure>

* **NOTE**: You must be familiar with the agent's function and the agent's input and output format. Make sure the agent is suitable for your app, otherwise it will not connect successfully.

* Use the "image prompt" or "text prompt" to describe how you want to use the agent in your app. In this app, the input is a user query like:"What's the weather now in New York?". And the output is a url of a base64 formatted picture. So for the text prompt, I used `"Use the input box's content as the input of the agent and the url in the output as the picture on the app."`

<figure><img src="../../images/cui-6.png"></figure>

* Click "Make It An App" and we will automatically connect your app with the chosen agent.

* **NOTE**: It might take a few tries before the agent is successfully connected to your app, be patient! 
  
* The one text prompt is not enough for the app to connect to the agent so I then used `"The url of the output picture is base64 format. Display the picture on the app below the input box."`. After a few tries, the app should work normally.

## Tips

* To get better results, try describing your functions/changes you'd like to make one at a time and in details. 

* Make good use of the drawing tools to tell us the changes you want to make to the current app.

* Each time you click "Make It An App", we will generate a new version of your app. If you find the results unsatifactory, simply go back to previous versions and start from there again.