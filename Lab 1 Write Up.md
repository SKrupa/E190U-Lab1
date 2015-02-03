#Introduction
In this lab we constructed the hardware for a standard video game console controller. The design specifications demanded at least two analog joysticks, four buttons, and a switch. these could be configured in anyway the designer wished, provided that the final design was functional as a controller.

#Design Methodology
Since mainstream video game controllers have been converging on a fairly uniform profile with most controllers having a similar amount of buttons and joysticks, I decided to model my design after this standard design. I felt that working off of tried and tested designs for a first controller would be more successful than abandoning years of knowledge present in the industry.

![](https://raw.githubusercontent.com/SKrupa/E190U-Lab1/master/20150201_164508.jpg)

Specifically, I modeled the layout of the xBox One and xBox 360 controllers. I personally find these to be the most comfortable controllers to hold. I did make one deviation, which was to make the controller larger than both of these reference controllers. Part of this was because of design limitations, the joysticks and microcontroller we were provided were bulky and in order to fit them on the controller, the controller would need to be physically fairly wide. But I also feel like modern controllers have not kept up with the trend of gamer's getting older. While video game consoles and their controllers were initially marketed towards children, which waranted the small size of the controller, modern consoles need to appeal to both children as well as adults. For this reason, I chose to create a larger controller to allow individuals with larger hands to comfortably hold the controller.



The button layout is exactly the same as the standard xBox layout, with diagonally placed analog sticks. I contemplated switching the locations of the right face buttons and the right joystick (as can be seen on the Wii pro controller). However since I had already constructed the left half of the controller, I found that using the directional pad (d-pad) was pretty uncomfortable due to the controllers size. Jumping from the analog stick to the d-pad required a lot of effort, this is not a problem with the left side of the controller since one rarely switched between an analog stick and a d-pad mid-game, but would be an issue when trying to quickly jump between aiming with the right stick and performing an action with the face buttons.

There were 2 unique features I added to the controller. The first was a simple buzzer speaker on the underside of the controller which can be used to provide anything from game feedback such as buzzing for every successful hit on an enemy to providing debugging information when the controller's firmware is being designed.

The second feature is a mode switching button. Clicking this button will allow the user to reprogram the controller on the fly to suit their needs. Currently, it is planned that the button with toggle the left face buttons between functioning as a d-pad and as a set of control keys which will affect parameters such as stick sensitivity and acceleration.

![](https://raw.githubusercontent.com/SKrupa/E190U-Lab1/master/20150201_164527.jpg)

Since I wanted to use far more buttons than there were digital pins on the Arduino Micro, I used on of the analog pins to read the remaining 6 buttons. This was achieved by making a simple DAC where each button theoretically controlled a bit of 10 bit number (starting with the most significant digit). I planned to use the configuration seen below, however I did not realize until I had run most of my tests that I had used a pulldown resistor far too small for my application. This resulted in the buttons associated with the larger resistances to map to a far smaller range of numbers than the other buttons.

![](https://raw.githubusercontent.com/SKrupa/E190U-Lab1/master/schemeit-project.png)

![](https://raw.githubusercontent.com/SKrupa/E190U-Lab1/master/unnamed.jpg)

#Testing Methodology

When testing the ergonomics of the controller, I designed purely around my hands and what felt "correct" for me. I got feedback from a couple of individuals about the overall feel and changed small portions of the design to fit their feedback such as the positions of the shoulder buttons.

For the connections, after soldering everything on, I quickly checked connectivity on all of the buttons. It seems to be working properly, but to make sure, I tested further in arduino by printing button values over serial. I also tested the analog sticks this way to make sure that they were returning values of 0 to 1023 as expected. All of the buttons and both analog sticks provided expected values.

For the 6 buttons tied to the analog pin, I printed out the analog values for any combination of the 6 button presses. I wrote down all of the values and the corresponding combination of buttons for use when programming the controller in the next lab. All of the analog values were unique, although some values towards the upper end of the scale were consecutive (eg. 822, 823, and 824 all map to unique button sequences).

#Results and Discussion



#Conclusions

I spent about 2 hours constructing the wooden controller profile and about 30 minutes assembling the buttons on the board and soldering all the connections. Finally, I spend about 30 minutes testing connections and functionality.

I would recommend a thicker controller since the provided single plank of wood was a bit thin to hold comfortably. I also feel like this lab and the second lab are a little to basic to be seperated. I ended up doing both labs together since it felt like neither was hard enough to justify the 2 weeks we've been given to complete them. And although I spent a non-trivial amount of time on this lab, most of that was in the wood shop because I personally found it to be fun rather than feeling the lab required that much work.
