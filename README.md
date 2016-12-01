# PiCar-Revisited-with-ZeroRPC
A variation on the excellent project by Keith Lawson.  https://github.com/lawsonkeith

Revisited with the help of ZeroRPC

It all started with a magazine I bought from a shop at Liverpool Lime Street Station
entitled “Raspberry Pi The Complete Manual” 3rd revised edition.
There were two articles entitled Build and then Control your Raspberry Pi-Powered
car.

To cut a long story short it advocated using an Ada Fruit PWM 2C Servo Driver, which I
duly did and started looking around for software to drive it. Alas nothing
could be found of the (promised on page 115)
JavaScript library to drive this card. The Adafruit Python libraries worked
fine. When I downloaded the code I discovered that another solution had been
substituted using a direct coupling to two GPIO pins using some NodeJS code
called PiBlaster. I was never very comfortable with this solution, I was very
nervous about getting my 3.3 Pi volts mixed with 5 servo volts. The PWM 2C gave
a nice separation.

So how was I to mix the Node JS software for the HTML socketry with the Python servery?
Enter ZerorRPC. An article by Ian Hinsdale told me how I could load the same
onto Ubuntu. Needlessly to say this procedure didn’t seem to work for Raspberry
OS, but I did find it loaded onto Lubuntu which I happened to have on my
laptop. I then discovered Ubuntu Mate could be loaded onto the Pi. I duly did
this but loading the ZeroRPC on this was not a piece of cake…. a lot of trial
error ensued. I dare say if I had put the same effort into Raspbian, I might have
succeeded; I did get the Python side of things working on Raspbian.

An article on the zerorpc website showed me how to set up a Client Server relationship
between the two software regimes. I must say my solution for passing “global” data
between the two back to back servers was very clumsy and would have been better
with a publish/subscribe pattern, preferably synched with the inputs from the
phone, but I could not find the code. Any suggestions?

Any way 90%of the code in my project and a lot of help is attributable to lawsonkeith and pals, 
whoever they are. I am not sure of the etiquette surroundingpublishing this code!
  
Points to note, this project can be spread across 3 computers, with 3 operating systems,
in 3 languages, thus: -

 
   Computer            Operating System          Language     Application
  Smart Phone          Android                   HTML         socket.html
  1st Pi (or laptop)   Ubuntu (Mate)             Node.js      appTB.js
  2nd Pi               Raspbian                   Python       ControlCarTB.py
   
 I spent about a week trying to get around the fact that I could put a number into one
end of zerorpc and get a string out of the other. I got around the problem by
turning the numbers into expressions by the simple expediency of multi plying
them by 1. 

Hardwarewise the car had no speed controller, just 3 position switch, i.e.  stop: forward (fast): 
backward (fast). I could
have steered the car in a more analogue fashion but chose instead left:
straight: right. This kept the software a lot simpler. However, I have not road
tested it yet. I’ll probably need a tin hat and some shin guards!

HIS GROTTY EDITOR? I HAD SOME NICE PHOTOS TO SHOW!

