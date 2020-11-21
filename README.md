# How to receive and process live audio with Swift

This Repo is just for collecting resources and giving a basic explanation on how to do what the headline intends. In the end Apple made this pretty simple but thus I wasnt very lucky with my search and quiet new to iOS App Development it took me a proper amount of nerves and time to figure everything out.

Disclaimer: I dont not own any of the conent linked/shown here


#### So let's begin by drawing the situation: you want to record audio which is spoken right now and proccess it directly (live)

so what are the things we need to do?
  - first we need a way to use the mic
  - then whe need some kind of Memory which gives us the speach in little brackets we can process (cause if we want to process the data live we cant wait till the whole file is written)
  - and lastly we need some Method that is called when there a new bracket
  
  
