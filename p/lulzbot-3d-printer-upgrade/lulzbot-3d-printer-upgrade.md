# Lulzbot 3D Printer Upgrade

I hope all is well with everyone. It’s getting to be a bizarre year with the events that have been happening. School is about to start for my son, and it’s all online this year. It is going to be interesting.

I want to tell you about an older model Lulzbot AO 101 3d Printer, that I have. I bought it probably five years ago but only got it working two years ago and I want to upgrade. While planning my upgrade process, I decided to write it down—what better way than to make a post about it. I will be changing the mainboard, hot-end, extruder, and possibly the motors. I would also like to try out sensorless homing and possibly a BL-touch. Wow, hit you with a lot of terminologies right out the gate! I am going to expand on all these in a moment, but first, let me explain why I am upgrading, especially since the last post I was telling everyone not to mess with a working machine. 

[![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faf094de1-d53a-440f-8d84-e93e42fed428_2934x2831.jpeg)](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faf094de1-d53a-440f-8d84-e93e42fed428_2934x2831.jpeg)

## AO 101 Lulzbot

My thinking about the AO is it's an 8-year-old machine, and I want to change the hot end allowing it to print other filaments. Lulzbot wants a couple of hundred dollars for a rig, which I don’t think is compatible. I would have to make modifications because my machine is so old. Lulzbot is not manufacturing the tips for the hotend anymore, and I only have one left. The main reasoning aside, I just want to see what I can accomplish. I have been doing a lot of research, and I think I could get a competent printer that can print most filaments. The one downside is that it’s not a very big machine. The bed size is 200mm x 200mm, and the height is less than 150mm. That’s almost 8 inches by 8 inches by 6 inches. I’m guessing the height is more like four inches. Making these modifications will give me the confidence to do what I really want, and that's to make a 400x400x400 printer, but that’s for another time.

In this post, we are going to go over the mainboard. I am buying the BIGTREETECH SKR mini E3 V1.4 Turbo 32Bit Control Board. I can purchase this board with the TMC2209 drivers for under $70. I was leaning toward the Duet 2 Wifi, but it’s $170, this is a lot more than what I paid for the AO 101. I could drop down to the V1.3 version board with the 2208’s for $50, but for twenty more bucks, a quieter more future proof machine seems wise.

The board uses quiet 2209 drivers and supports sensorless limits, they allow you to remove the mechanical switches on the machine. The drivers make the machine so quiet you can barely hear it, especially if you do something about the fans. The board also has support for external power modules, support for LED strips.

 **POWER MODULE**

[![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faf8c97c7-bacf-442d-89c9-e941efa107bd_933x591.jpeg)](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Faf8c97c7-bacf-442d-89c9-e941efa107bd_933x591.jpeg)

You can use a Neo Pixel, a TFT panel, and a Bl Touch. I like the ability to use the Bl Touch, but I will not need that straight away. The bed on the AO is nice and flat. I love the idea of the Neo Pixel, as this allows you to set different colors for different tasks. I could add red when the print fails, or I can add green when finished. The TFT panel will be helpful as I will not be connecting this to Octoprint, although I am sure in the future, I will.

I know I will find more reasons while installing this board as to why it's a great choice. I will also find reasons why it isn't the best choice. Once I install the V1.4 I will write all about it. Have fun, and I hope this was the help you needed.

