# Part 1

## Why computers use binary?

It is simple. And because it is like whether it stores electricity or not. On or Off. 
	Everything inside an electric device has switches, called 'transistors'

## Why this pattern? (binary)

It is like the 'nth-place' in math. Number 123 is '1 in the hundreds place', '2 in the tenths place', '1 in the ones place'. 

Essentially, it is 10^2  + 10^1 + 10^0. 

The exponential expressions are in the parenthesis
1 (hundreds)  + 2 (tens) + 3 (ones) = 123

## Why '10'? 

Because it is the 'decimal system'. 'Dec' means 10. These are numbers from 0~9.

In binary, it is 2^2+ 2^1+ 2^0. 

001 = 0 (fours) + 0 (twos) + 0 (ones) = 0
001 = 0 (fours) + 0 (twos) + 1 (ones) = 1
010 = 0 (fours) + 1 (twos) + 0 (ones) = 2
011 = 0 (fours) + 1 (twos) + 1 (ones) = 3
100 = 1 (fours) + 0 (twos) + 0 (ones) = 4
111 = 1 (fours) + 1 (twos) + 1 (ones) = 7

## What if you want to count higher than 7?

Add a bit. Computers use at least 8 bits at a time (smallest number of data these days). A.K.A 1 byte. 

## How could computers represent different symbols, like letters?

A - 65 (ASCII)
Bit form:  1000001
1 (sixty-four) + 1 (one)

## How could a computer differentiate 'A' from the number '65'?

Different file formats.

![[ASCII-Table.png]]

When you receive anything be it email, text, it comes in a standard length (8 bits).

Or 1 byte.

## The problem with only having 8 bits is that you can only represent 255 characters. What about other languages' symbols?


Unicode. A 'superset' of ASCII. Mapping of more characters.

16-bits and 32-bits

Emojis represent 1 character.

Trivia: 
4,0356,991,159 decimal number

1110000 10011111 10011000 10110111

Represents face with medical mask.

Different OS interpret emojis differently.

Unicode standardized the description, the manufacturers interpret is.

Also a gun can become a water gun.

  
## Hexadecimal uses four bits per digit


Decimal 12 in hex is 8-bits, apparently.

## How would computers represent colors?

RGB. 

ASCII used to be 7-bits but made it 8-bits because not enough room. Which is the 'Extended ASCII'.

Suppose a computer was using the decimals: 72,73,33, in the context of a program for creating graphical files.

We could make these numbers represent some amount of red, green, and blue.

And when you combine 72, 73, 33 amount of red, green, and blue, you would get some resemblance of yellow.

You can use 0~255 numbers for each color to get the color you want. This is why rgb has a max value of: 255, 255, 255.

## Each pixel uses 24 bits

8 bits for red, blue, and green, respectively. 

## How would a computer represent a video?

Same as the images but it adds a notion of time.

Sequence of frames (or images) per second to have the impression of movement.

## How computers represent music?

A format called MIDI represent each note as a sequence of numbers.

"These are how computers interpret information. And it is up to the software that we (people) write to use those zeros and ones in ways we want to get computers to do something more powerfully."

## How do computers differentiate, in an mp4, differentiate the video from the sound?

"You allude to MP4 for video and more generally the use of these things called 'codecs' and 'containers'. It's not quite as simple when using larger files, for instance, in more modern formats that a video is just a sequence of images"

Why?

"If you stored that many images for like a Hollywood movie, like 24 or 30 of them per second, that's a huge number of images. And if you've ever taken photos on your phone, you might know how many megabytes or larger even individual photographs might be. So humans have developed over the years a **fancier** software that uses much more math to represent the same information more minimally just using **somehow** shorter patterns of zeros and ones than our most simplistic representation here."

"And they use what might be called 'compression'. If you've ever used a zip file or something else, somehow your computer is using fewer zeros and ones to represent that same amount of information, ideally without losing any information. In the world of **multimedia**, there are both **lossy** and **lossless** formats out there. Lossless means you lose no information whatsoever. But more commonly as you're alluding to one (mp4) is lossy compression where you're actually throwing away some amount of quality. You're getting some amount of pixelation that might not look perfect but it's a lot cheaper and a lot easier to distribute."

"And in the world of **multimedia**, you have containers like QuickTime and other MPEG containers that can combine different formats of video, different formats of audio in one file, but there, too, do designers have discretion."

## input -> box -> output

### What's inside the black box?

#### Algorithm
A step-by-step instruction to solve a problem, in the context of software (programs).

Writing a program necessarily means writing one or more sets of instructions.

Example:
	Suppose you have an app: Phone contacts. It has names, phone numbers, emails, etc. You would be scrolling through the list of your contacts to find the person you want to call.

Example 2:
	Suppose you have a phone book. You want to look for 'John Harvard' in the book. To solve this, you would physically sift through the pages to get to 'John Harvard'. And eventually, you will get to him.

Is Example 2 efficient? What if I go through 2, 4, 6, 8, 10 etc pages at a time?

It is not efficient. And sifting through more than 1 page at a time leads to missed pages.

What if we just rip the page in half? Since we don't need to go through all the letters. If we started with 1000 pages, we would now have 500 to go through. And what if we continue to do this until there is only the pages for letter J? 

It would be faster.

We just have to express our intuition and ideas more precisely using things called **programming languages**.

Why is this method better than just going through the pages one-by-one or two or more?

Suppose a graph. x-amount of pages, y-amount of time.

Let's presume there's a 1-to-1 relationship between x and y. For each page, will take 1 second. Going through 10 pages will take 10 seconds and going through 5 will take 5 seconds.

If there is a 2-x-to-1 relationship (disregarding the impracticality for the phone book), it will effectively be twice as fast.





