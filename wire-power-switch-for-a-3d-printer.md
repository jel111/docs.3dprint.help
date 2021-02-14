# Wire Power Switch for a 3D Printer

I am rebuilding an old printer I bought at a garage sale. After installing new electronics the original power switch isn’t the kind I can now use. I want one that is lighted when powered and a better ground. Power switches are very inexpensive and for around $8.00 you get three. After all the money I spent on on this rebuild an $8.00 purchase isn’t going to break the bank. Let’s wire it up.

## Research!

First thing I did, like I’m sure many of you do is to watch YouTube videos on how to wire these. I was still lost and had to read some articles. The biggest problem I was having is that there are three connections that are coming in and two connections that come out. It has two more jumper connectors for the light and the Neutral wire. I have another printer and pulling that apart confused me even more because that switch has only six total connectors and the wires from China use a different color scheme. The color codes for the USA, Europe and China are different and that throws another wrench in when researching the proper way. My initial investigations left me somewhat confused and I had to go back over a few articles and ask questions on a forum I belong to. It seems so simple but this is one of those things that you need to do correctly the first time or you may see that famous blue smoke billowing out of that brand new motherboard which costs around $80 with the drivers.

## No Electrician But…

I am not an electrician but this is pretty basic wiring and if you have a bit of time to research you are going to be fine. Of course there is always the chance of getting shocked so buyer beware make sure you get a handle on this _**before**_ you attempt. I imagine if you are modding 3d printers you should be mechanical enough to get this done. Just follow a few safety precautions and take your time and things should go well. The main precaution is to never work on this live and let the energy dissipate from the power supply for a few minutes before you handle anything. I did a test and left the multimeter hooked up after I disconnected from power. It was around three minutes before the meter showed a minimal reading. There are capacitors that store energy for a bit so be mindful.

## The Switch

[![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F698ecfae-325a-4cf1-b55c-82ba14501845)](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F698ecfae-325a-4cf1-b55c-82ba14501845)

The switch came in four pieces. The main body the actual switch a drawer for the fuse and the fuse. Be careful some come without the fuse. You will also need a power cord that plugs into the switch and then the wall where you are getting your power to the PSU \(power supply unit\). The switch is lighted and it has a fuse which will blow for any surges of power.

## The Button

[![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F04eb42a4-0dfc-4c3d-a66e-9d4249281f9f)](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F04eb42a4-0dfc-4c3d-a66e-9d4249281f9f)

The button itself is lighted so it has four pins on the back. Two of the pins receive jumper wires from the main body and the other two are the outputs of neutral or power/positive and hot or negative that completes the circuit. You have the ground which comes off the main body of the switch. The ground is the wire that if there is a short the power has somewhere to flow and dissipate. If this explanation isn’t enough for you here is a detailed explanation from [The Engineering Mindset](https://theengineeringmindset.com/ground-neutral-and-hot-wires-us-can/) site. The article explains American wiring but is still very useful in understanding the neutral, hot, and ground aspects of powering a light or outlet no matter where you are and is directly useful for our application. Safety first!

## The Main Body

[![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff5eb9b07-faa7-4b26-b6c1-04c2ec199d5d)](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff5eb9b07-faa7-4b26-b6c1-04c2ec199d5d)

In the image above you see the back of the main body with the switch snapped in on the bottom. The very top pin is your ground that comes straight from the power supply. The two on the left directly below are the neutral and the hot. These two pins use a small jumper wire or a short wire a few inches long with the proper connector on each end. I would use either some shrink wrap or connectors that have a plastic shield. It is better to be extra careful here making sure there are no mishaps or arcing between these connections.

## Wired Up

[![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F9a35af64-9875-4d39-a47f-5c940483fe28)](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2F9a35af64-9875-4d39-a47f-5c940483fe28)

Above is an image I used to wire my switch. In the United States the wire colors are different but it gets the job done. It is a great example of our end result. In case you are interested the green is ground, the white is neutral, and black is the load or hot in this situation.

## Wires Needed

[![](https://cdn.substack.com/image/fetch/w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fff8f69e2-b775-499e-8f64-9b0b1d8b128c)](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fff8f69e2-b775-499e-8f64-9b0b1d8b128c)

The wires I made up for the switch are not very long as you can see in the image above. The green wire is the ground and that goes from power supply to the top pin of main body. The two jumper wires are next, one you can get by without as it just lights the button. The two other wires, neutral and hot, coming from the back of the button go to the power supply. I then have the hot and the ground coming from the power supply splitting into two giving power to the motherboard and the buck convertor which powers the Raspberry Pi that I use for Octoprint.

In the next Newsletter we will focus on getting your Raspberry Pi powered from the Supply of your machine instead of a separate plug running from the wall. Until then have a great week and let’s go print.

