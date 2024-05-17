
# activity - an ouput window? 

Comes with 2 files:

layout file - design of the app. written in xml file


logic file - logic of the app.  written in kotlin file
	like on button click, do **something**.

# Kotlin

We have to predefine our variables, which is why we put them on top of the `class`, before any function implementation.

```kotlin
class MainActivity : AppCompatActivity() {  
  
private lateinit var n1: EditText  
private lateinit var n2: EditText  
private lateinit var sum: TextView  
  
override fun onCreate(savedInstanceState: Bundle?) {  
super.onCreate(savedInstanceState)  
setContentView(R.layout.activity_main)  
  
n1 = findViewById(R.id.n1)  
n2 = findViewById(R.id.n2)  
sum = findViewById(R.id.sum)  
}  
  
fun addValues(view: View) {  
val n1 = n1.text.toString().toInt()  
val n2 = n2.text.toString().toInt()  
  
val result = n1 + n2  
sum.text = "Sum $result"  
}  

}
```

Syntax:

`fun` represents **function**.

`private` represents the **scope** of the variable.
`lateinit` means the variable is to be **assigned later**.
`EditText`, `TextView` are data types.


`var` and `val` are keywords used to create **immutable**, and **mutable** variable. 
`$` is used as the equivalent of an `f-string` in Python. Also known as **variable** or **string**
**interpolation**.

## Creating an array (list)

`arrayOf()`. The arguments in `arrayOf` are the list elements themselves.

Model:
	\[List View] <--> \[Adapter] <--> \[Data Source]

List View refers to the layout file

Adapter is a class something something

Data Source is the array itself
# Assessment 1 - Reddit

Evaluate the following:

**Architecture and Functionality** - Describe design and flow of the app. Bring up limitations. Discuss functionality of the app.

**Aesthetics** - Color scheme and how it affects the objective of the app. Is the layout well balanced? Are icons and images attractive and approppriately sized?

**Fitness for purpose** - Discuss if the app accomplishes its goal. Are there flaws?


## Intro 

Reddit is a social news site and a mobile application, which allows for users to post their content-- could be any allowed content-- on any community and their content is ranked by popularity, which is determined by a system of community votes. Basically, posts with high votes are showed at the top of the app when users would first go into the app. 

Reddit separates its contents by its communities. These communities are also called as "subreddits". Subreddits can be about pets, memes, video games in general, a specific video game, news, a public figure, and so on. If you have an interest, chances are, there's probably a subreddit for it, too.


## Architecture and Functionality

The app is designed to be easy to navigate, even with just one hand. When you open the app, you are immediately in the `Home` page of Reddit. In the home page, this is where posts from different subreddits will show.

You'll notice at the top, an option box currently named `Home`. Clicking on this will show different tabs in the home page. You can also swipe in the home page to move to these tabs. This shows that Reddit is functionality designed to be used as easily as possible.

The app's features are easy to see, this is because the main features are shown in the first page of the app. Clicking on the top-left option shows subreddits you've joined, and clicking on the top-right shows all the options in your account.

For every feature of the app, there tends to be an icon accompanied as well. This helps users to faster recognize similar features from different apps, leading to an easier user-experience.

Overall Reddit's design is about on-par with most modern apps, they tend to share similar designs so that users are able to map-on what they know from a different app to the current one. 

And it contains all the relevant functions for the app to function as it originally did on its web-counterpart.

## Aesthetics

The app looks very minimal, primarily utilizing white-and-black color scheme. There is a dark mode feature to invert the color scheme. From what I've seen of the app, the `join` button is the only button that's different, being colored in blue.

The aesthetic borrows from the original Reddit site. Which is also primarily in white and black. 

I agree with this design choice because it fosters familiarity between the 2 platforms. What you know from the website will translate well into the app. 

The layout focuses on the main content of Reddit, which is showcasing posts from subreddits. "Navigational buttons" are located at the top and bottom bar. This is so that the user is faced with the main contents of the app, only putting the navigation features at the corners.

The icons, typically come with text that describe what that feature is, sometimes they do not; like the search bar on the top-right has no text that says "Search" or the top-left that says "Communities". This is to prevent cluttering and only using the text + icon combination on features that are more specific on what they do and the ones that are not as intuitive. And the icons themselves generally encapsulate what the feature represents or what it does.


## Fitness for Purpose 

The mobile app of Reddit is designed so that users of the site can have access to Reddit on their phones without primarily accessing it through the browser. The reason for why this app exists is the same reason why YouTube, Twitter, and so on, have mobile apps; which is to target the mobile demographics that may not have accessed the app through mobile internet browsing.

That is to say that the goal of the Reddit app is to bring its platform to the mobile industry. This means that all features of the Reddit website will be implemented in its mobile counterpart. And so far, it mirrors it very well.

~~--**just show how similar the app is to the website**.~~

There is one problem I have with the app, and that is when you search for something, but you want to refine it, but you don't go through with it, pressing the back icon will lead to the `home` page instead of the initial query results. There's no going back to where you were in your inital query, so you'd have to scroll all the way to get there again.

This is different in the website counterpart, where you can just click any non-link on the site to cancel your refined query, and you're still where you left off.


## Conclusion 

Overall, Reddit mobile sufficiently mirrors its website counterpart, which is the point of many apps that were once website-only. It has its own feature like this `communities` tab because I've never seen that in the website, so this is probably done as a mobile-exlusive feature, but it could also just be a new feature of Reddit. And I only found 1 thing I didn't like, so that's good. I would give Reddit a 99/10. 

The joke is that it's common in Reddit communities to have the same post become popular, so the second 9 was a "repost". That's about it.




# Google Slides

## Android OS

Open-source and Linux-based. Led by Google.

## FAAF Framework

Functionality - how it works, crashes, instructions, buttons, gestures and touches, optimal

Architecture - structure, pages, hierarchy, follow guidelines

Aesthetics - color scheme, high-quality images, appropriate animations, white spacing, graphics support

Fitness - accomplish goals, missing features or bloated, easy to use


## Layouts 

Linear Layout - Single-line layout of widgets, either only(??) horizontally or vertically. 

Relative Layout - Widget position is based on the parent container.

Constraint Layout - Flexible, can do whatever

Other - Grid, Frame, Table -- Layouts

[Constraint Layout](https://docs.google.com/presentation/d/e/2PACX-1vTEfCZxZ876L1JpxVJsdM1I_g-36UPeQLwQPaWcep6KiS7TU9ChauVN3WEb_PWPJpAPHLuWCgeJz8_j/pub?start=false&loop=false&delayms=3000#slide=id.g2bc9effbdf6_0_154)



## Images

Stored in res/drawable directory.

Can be png, jpeg, gif.

ImageView used.

How to add Images:

- [ ] Copy-paste image in `drawable` folder. Image **must** be lowercase and or underscore only.
- [ ] Drag and drop `ImageView` to the GUI.


## Toast Messages

Small message to provide information or feedback.

Syntax: `Toast.makeText( this, "Welcome", Toast.LENGTH_SHORT ).show()

`LENGTH_SHORT` - 2 secs
`LENGTH_LONG` - 3.5 secs


## ArrayOf()

The data structure of the Kotlin to the GUI looks like this:

ListView <-> Adapter <-> Data Source

### Definition

ListView - GUI in the layout .xml

Adapter - The middleman 

Data Source - Hard-coded values

### Mechanics


Adapter creates a `View` for each item in the data source. It then inserts the items into a `ListView`. Can customize how the items are to be displayed. All done when instantiating an object of the `Adapter` class.










## Change Icon

- [ ] In `App/res/drawable`, create a `New` `Image asset`. 

## Adding mp4

in `App/res/`,  
- [ ] create a new folder called `raw`, 
- [ ] drag and drop the mp4 to `raw`.
- [ ] create a variable holding `MediaPlayer` data type.
- [ ] assign `MediaPlayer.create(this, mp4 )` to said variable

To go to the start of the mp4, `mediaPlayer.seekTo(milliseconds)`, milliseconds is self-inputted.


## When adding Images,

Make the `scaleType` to `cropCenter` or something 


# Critical Summary

## Conceptual Goals

Since we were tasked with creating a NaN calculator app (i.e an app that outputs something based on an input, but must not be a number), the first thing that came to my mind was the thought of color combination. In most programming languages, colors are represented either by their hexadecimal form or by a function of rgb, taking 3 arguments: red, green and blue.

And how this works is that red, green, and blue are an 8-bit unsigned integer data (a number that ranges: 0~255), and based on this number, determines the amount of intensity or brightness of that color. This gives the illusion of seeing any color in the visible spectrum, all because the pixels are so close together that they look like a single point in the human eye.

And my app is supposed to make use of this concept, as there are many ways to mix-and-match primary colors, without necessarily outputting a number.

## Aesthetic Choices

The app is designed to be simple to use. At the very top is the name of the app, called "ColorMix", the word *Mix* is colored in differing intensities corresponding to red, green, and blue. I added the color on the latter word so the app doesn't just display a bland text referring to the title of the app.

In the middle, there are 3 input fields, each corresponding to the red, green, and blue inputs. They are accompanied by an icon to show the intensity of the corresponding color, as well as having a "random" button to generate any number in that input field from 0~255. These widgets are in the middle so that they are most likely to be focused on by the user, and that they serve one of the primary functions of the app, which is to take inputs.

At the bottom of the app is the resulting color, which has a bigger icon than the last 3, and is accompanied by a hexadecimal label corresponding to the color of the resulting color. By default, the hexadecimal value will be #000000, which corresponds to the color black. In a hierarchical view, it makes sense to put the output at the bottom when the inputs are at the top, and so these widgets are here.

At the very bottom of the app is the "help" icon, showing steps on how to use the app. I put this at the bottom-left of the app as I don't think looking at the tutorial of the app is one of the primary functions, so it's just placed somewhere at the edge of the screen to be found by the user when they are looking for more information about the app.

## Technical Description

The main concept of the app (the idea of color mixing) comes from the way we represent colors in many programming languages; specifically, the use of hexadecimal representation or its rgb() form. Many programming languages, including Kotlin, accept the hexadecimal or its rgb() form, so I designed the app in a way that the user will be the one to input what goes in to the rgb() function, then the job of the app is to take in this input, turn it into its hexadecimal form, and change the background of an ImageView based on this hexadecimal form.

Why I chose this is because there can be many combinations that can be generated, so even if the app is simple, you can't really say you've seen everything the app has to show unless you've seen all the colors possible in the color wheel. To put this into perspective, the amount of possible colors available is 256**3, which is equivalent to 16,777,216 colors.

## Self-reflection

### Strengths

I think the app does a great job of balancing the challenges of implementing data structures and algorithms, and user experience, with the icons being responsive to an input, as well as having an input button for added quality-of-life.

I think the app is quite user-friendly, it shows where an input is supposed to be and what it corresponds to. And the name of the app sufficiently describes what the main function of the app is supposed to be. In cases of doubt, a pop-up view is available, and it contains a sample of how an interaction is done.

I think the app did a good job of handling errors as well. In the cases where a user enters an invalid input, instead of crashing, it assigns a number 0 on that input instead.

I think the app is flexible and responsive; if the user does not want to input their own value, they can instead press a button to generate a number for them, and on top of this feature, is the responsiveness of the ImageView corresponding to that input. This provides user feedback and lets the user know that their inputs are being recognized by the app

### Weaknesses

Given the scope of the app, I think it implements all of the necessary structure pretty well, but there is one thing that can be improved upon, which is a way to copy the resulting color's hexadecimal form into the user's clipboard for use. It's one thing to see what the resulting color is and its hexadecimal form, and it's another to be able to do the same, but with the ability to use this outputted value for use.


# Video Script

This is my nan calculator app. And what it does it that it mixes a color based on the strengths of the 3 primary colors, red, green, and blue. 

The icons on the left represent the strength of the color. By default, it's at the max strength, to signify what color it corresponds to.

The button on the right represents a random button, which generates a number from 0~255.

At the bottom is the resulting color, as well as its hexadecimal representation.

And lastly, the "info" icon, which describes how to interact with the app.