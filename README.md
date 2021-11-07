Created by Tanay Patil, Abhijit, Gaurab Das, Girish Balakrishnan

## Inspiration
We had a ton of friends, including ourselves, who faced this problem on a daily basis and when we saw a section dedicated to this in UB Hacking registration form asking about people's dietary wants, we realized this had to be made!

## What it does
PickyEatr is an app that we developed that uses Optical Character Recognition and Google Firebase to analyze an image of a restaurant menu and highlight options that you can eat based on your dietary restrictions. You have the options to choose between vegetarian, pescatarian, vegan, nut-free, and gluten-free

## How we built it
The project involves 2+1 fundamental modules: Image Processing (contours, color detection, etc.) and OCR (Optical Character Recognition)
###Initial Contouring
After contours are extracted, we notice a lot of tiny contours all over the image due to color shades that our threshold method will have highlighted. To eliminate this noise and filter down to large contours (the assumption here is that the larger contours would be the highlighted portions), we can perform some statistical analysis on the area of the contours to keep only those outside a specific number of standard deviations from the mean(i.e. all contours 4 standard deviations away from the mean).

## Challenges we ran into
###Post OCR “contouring”
Contouring, essentially, is boundary detection (edge detection but finding closed curves). Through the method in this section, instead of performing an explicit boundary-detection step, we find the highlighted boundary implicitly — it seems to be a better technique to deal with our problem which is the initial task. Rather than deciding what is highlighted right off the image as a human eye would, the computer has another advantage: computation power. Therefore, we can approach this less intuitively: OCR first, and then determine, word-by-word, if it is ‘highlighted’ or not. We can do this by using our color-specific thresholding once again. Firstly, using Google’s API, alongside the text, we can also extract a boundary-box around each word OCR-ed.

## Accomplishments that we're proud of
Making our first OCR application, with two first-timers, with a variety of machine learning and non-machine learning techniques. Real-time text analysis to determine new elements. Collaborating and distributing the workload based on our strengths, attempting to learn new APIs very quickly, and not sleeping(obviously)!

## What we learned
Since only one of us had prior experience with Android Studio, we all had to learn the basics in less than two hours to understand and contribute to the different stages during the development.

## What's next for PickyEatr
Improving the UI, developing a version for iOS as well, and creating an ML model with a higher text detection accuracy
