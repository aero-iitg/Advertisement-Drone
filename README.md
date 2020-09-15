# Advertisement-Drone

![Drone Image](/Drone.jpg)


### Body ideation and details
* Initially an n-sided polygonal(preferably octagonal) cylinder was thought out, to make the central body of the display  with LEDs inserted by hand.
* Later , WS2812B strips were finalized as it made forming a layout easier and the library found, supported this addressable RGB led.
* The length of each smaller segment,each containing 3 LEDs, was taken into consideration when forming a cylinder out of aluminium sheet to match with the circumference.
* The LEDs were laid out in a 35x8 spiral with each segment exactly below leaving no gaps, with the LiPo and the arduino board placed in the center of the cylinder.


### Code
* Our job was made easy due to the amazing [FastLED](https://github.com/FastLED/FastLED) library, which supports and handles a vast variety of LED chipsets, including the WS2812b LEDs used in this project.
* The LED strip wrapped around the drone's cylindrical body is represented as a linear array in the code.
* An 8 column wide buffer zone seperates the start and end of the display.
* Each Letter's 8x8 representation is stored in the IMAGES array in the code.
* 8x8 was chosen because of the ease of availability of 8x8 representations of the English alphabet.
* Each letter from the string s is converted into an 8x8 matrix to form a representation of how it will be shown on the actual drone.
* The letter is then viewed as 8 seperate columns, and each column is added from one edge of the cylinder via the addcolumn() function.
* At each step of the loop, A column addition is followed by a leftward scroll of each row on the actual body, to make space for the next column to appear and to create the scrolling effect of the screen.
* The above sequence is repeated till the whole input string is displayed, and then the loop re-runs.
* The buffer zone and display text's colour can be handled by changing their RGB values in the code.


### Future plans
* Sending the display information remotely, rather than hard-coding directly into the code.
* Incorporating images as well other information onto the display, currently, only text can be displayed.
* Making the drone autonomous, rather than remote-cotrolled, so that it can circulate around an area to advertise the information without any manual control.