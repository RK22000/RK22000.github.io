---
---
# Mon Jul 10 01:56:01 PDT 2023

So I got started with a few things to get the ball rolling. A few days ago when I couldn't fall asleep I sketched out a design in a [figma doc over here](https://www.figma.com/file/LazVrZMd4wVsIR54jGY5fF/Smart-Gallery?type=design&node-id=0-1&mode=design&t=jl1pU1bb8V7qmDAv-0).

![Figma diagram of first sketch](/assets/images/pics/Group74.png)

Mind you, you will need to be logged in to see it as it is not public. Today I created the android app that I'll develop into what the figma doc outlines. Here's what I've done so far.

## The Android App

I partially did this [codelab](https://developer.android.com/codelabs/jetpack-compose-navigation?hl=en#0) to brush up on whats the recomended way to do navigation in android right now. It used to kinda be so confusing last year so I was hoping they've had it simplified by now. Thankfully it was simplified. Then I got started making the app. Here's my approach for how I think I'm gonna go about developing this app.

I'm creating this screen called `TheSpaceBetweenScreen`. This screen will have buttons leading to every other screen in the app. Those screens will connect to each other as they naturally would, but they won't connect back to `TheSpaceBetweenScreen`. The only way to navigate back will be the back button to pop the navigation stack . This way when I'm testing out the app in development I can always jump to any screen and test out the behavior as I like. Then when I want a relese version of the app I just remove `TheSpaceBetweenScreen` and change the default screen to the `Home` screen.

Today I set up the `NavController` and `NavHost` and stuff along with the `TheSpaceBetweenScreen`. I also created a `Home` screen where I have just loaded a bunch of stock photos in a LazyColumn.

![Gif of images loaded on Home screen](/assets/images/pics/output2.gif)

Funny thing when loading images. If you are not carefull you might try to load an image thats too big for the screen. If this doesn't kill your memory it will very likely cause a crash when your phone tries to draw on its canvas an image that does not fit in it. To prevent this you need to do some preprocessing to figure out the image size and scale the image before you load the image. This is a pain in the ass so I just followed the reccomendaion I saw on [android developers](https://developer.android.com/jetpack/compose/graphics/images/loading) and used the [Coil library](https://github.com/coil-kt/coil#jetpack-compose). Fun Fact: Coil stands for **Co**routine **I**mage **L**oader

> endlog - Mon Jul 10 02:54:42 PDT 2023
