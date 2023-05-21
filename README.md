# htmljavascriptproject(The project is in master branch not main branch)
Title-
The project is based upon the working of a wearable device which detects if a person is slouching or not

Source of project - I found this project from a placement drive of my colledge .We have to do this project using python or matlab but I did the project in javascript to demonstrate my javascript basics . 
Kindly click on the below link to know about all the details of the project
https://drive.google.com/file/d/1pyBzDGYB4saT2IUclnr0jlSptfJQ0RCV/view

Interpretation:
One Data Point is presented as:
02,02B9,FDEF,26E9,0031,FFF4,FF9D,391C,0307,B575,
a. ONLY THE 3 BYTES THAT WE HAVE HIGHLIGHTED IN BOLD ABOVE ARE GRAVITY VECTOR DATA
IN X, Y AND Z AXIS
b. The bytes provided are in hexa-decimal format. Convert them to decimal format and then use
the following algorithm

let p be the value in decimal format, then:

1. if p&gt;32767,
a. then p=p-65535;
b. else p=p
2. p=p/10000

c. Using this ‘p’ value gravity dataset, you have to detect if the user is slouching or not slouching in
terms of degrees.
d. HINT : Use the ‘p’ gravity dataset to find an angle dataset. The angle dataset will represent the
angle at which the sensor is placed with respect to gravity.
e. Use a threshold of 15 degrees to differentiate between slouching and not slouching, ie.
i. if angle &lt;15 degrees, then not slouching
ii. if angle &gt;15 degrees, then slouching

Reference gravity vector is always G = [0 0 1].

The working
If a user clicks on the button then the function bang is invoked which does an api call using XMLHttpRequest() .The action wich needs to be performed when sending the api request has been decalared using onload inside a function which retuns the dataset that I have stored in variable x .I split the dataset's every line using split function and took the x,y,z axis of each line and passed it to the convert function through an array as an argument.

In convert function I converterd hexadecimal to decimal values inside for(var i=0; i<4;i++) . I lopped it inside for(var j=0;j<3;j++) because I have to convert only 3 values from each line which I have passed again and again using bang function till the lines end .I did w=3-i because the loop increases from right to left and the power decreases from right to left.

The output of each is 3 vaules after convertion is stored in sum variable and the reinitited to the same array from where they are taken . I took only zaxis because other 2 axis becomes zero when multipled using the dot product formula of vectorswhich is a · b = |a| × |b| × cos(θ) .

I used math functions to calculate square root , power for the algorithm.

Result

It mentions if the person is sloucing by checing the x,y,z axis on every line of the mds.txt set


Things I learned

I tried fetching the txt file from the same directory using FileReader api but did not get any output but with further reading checked that filereader only returns the output when you load a file from html .I used the below article to learn all about xmlhttprequest
(https://stackoverflow.com/questions/15615293/javascript-read-text-file-from-current-directory)

I used split method to get the array of the substrings so that I can get the 3nd column for each row of my dataset which represents the z axix as I am following the direction provided by the example

I learned every basics of javasript from w3 school that is from link below
https://www.w3schools.com/js/

I learned dot prouct to calculate the angle between 2 vectors from the article below
  https://www.w3schools.com/js/
