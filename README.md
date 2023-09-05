# RC Transmitter Using NRF24L01
<img src="https://github.com/indoorgeek/RC-Transmitter-Using-NRF24L01/assets/63697764/fff5fbaa-fa6c-4b0d-b770-c0c97373174d" width=100% height=100%> <br/>
When I was a child, I was fascinated by drones and always wanted to have one. But they were not so common those days and quite expensive too. My brother once got a small cheap RC helicopter and we used to fly it almost every day till it's battery completely died. We were not competent enough to open it up and change the battery. So, that was it, my first and only experience with RC! But now, with a sound knowledge of electronics and lots of resources available on the internet, I want to build my own drone. Also, I am into photography as well and so I am planning to mount a camera onto it to get some cool shots from the above! But building a drone is one thing and flying it properly without crashing is totally a different thing. That's why I decided to build a small drone using Arduino to get a feel of the controls.
# The Plan
<img src="https://github.com/indoorgeek/RC-Transmitter-Using-NRF24L01/assets/63697764/30c05a7f-dc7c-456b-a91b-3de102e40b1f" width=100% height=100%> <br/>
I did some research on the internet since I am very new to the RC world. I came across [Electronoob's](https://www.youtube.com/@ELECTRONOOBS) YouTube channel which has some great content on this topic. He has built a small drone using brushed DC motors which in fact inspired me to build my own. I will be following his build and making changes as per my needs.<br/>

My plan is to build the drone in two parts. First I will make the transmitter and then the drone itself which will have the receiver built-in.<br/>

# PCB Design
<p float="center">
  <img src="https://github.com/indoorgeek/RC-Transmitter-Using-NRF24L01/assets/63697764/1ac94bab-3164-4ee2-88e1-b2a8938782d0" width="45%"/>
  <img src="https://github.com/indoorgeek/RC-Transmitter-Using-NRF24L01/assets/63697764/c930bb32-6b57-4a13-99f8-b28d3edb9adc" width="45%"/> 
</p> 

I got my PCBs manufactured from [JLCPCB!](https://jlcpcb.com/DAA). Get your PCBs beautifully fabricated from JLCPCB for just 2$!

The most important and necessary controls are throttle, yaw, roll, and pitch. These analog inputs will be provided by two 2-axis joysticks. I have added two 10k potentiometers to which other helpful controls like throttle trim, pitch trim, etc can be assigned. I have also used two switches to provide digital inputs which then can be used to toggle between different flight modes. For beginners like me, these inputs are sufficient to get started.

Arduino will be the brains of this build. You could use almost any Arduino development board like Nano. But to keep everything neat and tidy I decided to use the ATMega328P microcontroller directly on the PCB. First, I drew the outline of the shape of the controller in Fusion 360. I made sure it feels comfortable in hand and all the controls are easily accessible. Once I was happy with the shape, I imported it as DWG file in Altium Designer. I then made the connections as usual. I was about to call it a day when it struck me that I could design yet another PCB to go on top of the other one as a front cover. It would be more comfortable to hold too. Also, why not make a simple PCB art to make it look cool since doing this is a piece of cake in Altium Designer. Click here to get a free trial of Altium Designer. I asked my wife who is an artist ([@swirls_of_solace](https://www.instagram.com/swirls_of_solace/)) to create something which will look good on it and she didn't disappoint!

I have provided a female header connector to program the microcontroller using the RS232 FTDI breakout board. To be able to program it using the Arduino IDE, the bootloader should be burned onto it prior to soldering on PCB. I had salvaged the microcontroller from a Nano so it was already present. You can find many tutorials on the internet for burning the bootloader.

The most important and tricky part of this project is to power the NRF24 module correctly. The module works on 3.3V and can lead to current surges when powering ON or while transmitting the data. So, appropriate capacitors should be connected across the power rails. While testing the circuit I had used an AMS1117 3.3V power adapter board specially made for NRF24 modules and it had worked flawlessly. So I just recreated that circuit for this project.

# Assembly
<img src="https://github.com/indoorgeek/RC-Transmitter-Using-NRF24L01/assets/63697764/9164eb4e-1a8a-47f4-b293-de7f8d19b97f" width=100% height=100%> <br/>
I used the same outline, which I had used to make the PCB, to create the body around it. The body is again divided into two parts. The battery will be placed between the bottom PCB and the body. I have used threaded inserts for the screws. Everything will go together as shown in the picture and be held together by 4 M3 screws.
