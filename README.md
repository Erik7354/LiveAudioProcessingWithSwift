# An abstract on how to receive and process live audio with Swift🚀

This Repo is just for collecting resources and giving a basic explanation on how to do what the headline intends. In the end Apple made this pretty simple but thus I wasnt very lucky with my search and quiet new to iOS App Development it took me a proper amount of nerves and time to figure everything out.

Disclaimer: I dont not own any of the conent linked/shown here


# Now let's begin by drawing the situation
You want to record audio which is spoken right now and proccess it directly (live), right?

## What are the things we need to do?
1️⃣ first we need a way to use the mic

2️⃣ then whe need some kind of Memory which gives us the speech in little brackets we can process (cause if we want to process the data live we cant wait till the whole file is written)

3️⃣ and lastly we need some Method which is called when theres a new bracket available
  
## How to solve Todo 1

### ------------> The Solution lies in Session 502 from 2014s WWDC <------------

There Apple introduced the AVAudioEngine and AVAudioNodes. In this Repo I will just give an abstract of what is told in the presentation you can find here: https://www.youtube.com/watch?v=FlMaxen2eyw

### AVAudioEngines: 
An AVAudioEngines consists of and dynamically manages AVAudioNodes. Thus you can kinda think of it as a container for AVAudioNodes. In the AVAudioEngine you got one or more AVAudioInputNode and possibly one or more AVAudioMixerNodes and AVAudioOutputNodes. 

At first you declare the AVAudioEngine, then the AVAudioNodes and finally you add all nodes to your engine.
Then you can just press start on the engine and it starts recording (everything automatically). <-- Todo 1: ✅

### AVAudioNodes: 
As already mentioned there are multiple kinds of AVAudioNodes. But the names are quite self explaining.
An AVAudioInputNode takes input from an input source (like mic).
An AVAudioMixerNode takes input from an AVAudioInputNode and mutates the audio.
An AVAudioOutputNode takes input from an AVAudioMixerNode and plays it.
(very simplified)

## How to solve Todo 2 && 3

You can attach a Tap on every kind of AVAudioNode. These Taps gets called when theres a new available bracket of audio (Buffer). You give these Taps a BufferSize and a Callback. When the Buffer is filled the Callback will be called. Now you got what was just recored and can work with it. <-- Todo 2&&3: ✅
