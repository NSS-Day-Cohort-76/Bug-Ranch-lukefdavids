# Welcome to Bug Wrangler Ranch

This first self-assessment is for you to hone several Core Skills that you need as a software developer.

Taking your time now to be thorough, reflective, patient and curious will give you the foundation to be successful throughout the rest of this course and your career.

If you rush this, or think of it as a test to be "passed", then you will already be on the wrong path.

> 🧨 Make sure you answer the vocabulary and understanding questions at the end of this document before notifying your coaches that you are done with the project

## Description

Slim Jenkins offers a vacation package for people who have always wanted to join a cattle driving team across the American Midwest.

He calls it the **Kansas Slim's Cattle Adventure**.

People join a team of experienced drovers who will train them in the basics of herding cattle and driving them across hundreds of miles to their destination at Old Red's Ranch.

Unfortunately, someone gained access to the code that produces an outline of the adventure to the paying customers, so Slim has hired you to examine and fix the code.

## Learning Objectives

Here are your learning objectives for this self-assessment.

1. Able to use the debugger to step through existing code to discover root causes of bugs.
2. Drawing a sequence diagram for a project.
   > Use the [sequencediagram.org](https://sequencediagram.org/) site to generate your sequence diagram. Make sure you save your work as you go.
3. Demonstrate learning efficiency by researching concepts you haven't seen before using your peers, mentors, and the World Wide Web as resources.
4. Awareness of when you need help, and then seeking it out.

## Example Output

If you are able to fix all of the bugs, you will output similar to what is below. It will not be identical, but similar.

```sh
************************************************
**  K A N S A S   S L I M ' S   C A T T L E   **
************************************************

\|/         (__)
     '------(oo)
       ||   (__)               \|/
       ||w--||     \|/
   \|/
            \|/                     (__)
                             '------(oo)
                               ||   (__)
                               ||w--||     \|/

You will be accompanying 5 drovers as they drive 50 cattle to Old Red's Ranch for grazing

The herd is made of up the following types of cattle:
Ankole-Watusi,Brown Swiss,Brown Swiss,American Angus,Brown Swiss,
Ankina,American Angus,Ankina,Brown Swiss,Ankole-Watusi,Brown Swiss,
Brown Swiss,American Angus,Ankina,Ankole-Watusi,Brown Swiss,Brown Swiss,
Ankina,Brown Swiss,Ankina,Ankole-Watusi,Brown Swiss,Brown Swiss,
Ankole-Watusi,American Angus,Brown Swiss,American Angus,Ankole-Watusi,
Ankole-Watusi,American Angus,Ankina,Ankina,Ankina,Ankole-Watusi,
American Angus,Brown Swiss,American Angus,Brown Swiss,American Angus,
American Angus,Ankina,Brown Swiss,American Angus,Ankina,Brown Swiss,
American Angus,Ankole-Watusi,Ankina,American Angus,Brown Swiss

Here is the team of drovers you will be joining
        * Melvyn Hethron
        * Yancy Gresley
        * Willabella Attarge
        * Ynes Gyenes
        * Farlie Spere


Your journey will take you through the wildness of the American Midwest and across the following terrain
        * forest
        * plain
        * river
        * mountain
```

1. In the **main** module, one of the first lines of code is `const drovers = hireDrovers(cattleToDrive)`. Explain what the value of the `drovers` variable is when that line of code runs.
   > The value of the drovers variable will be the result of the "hireDrovers" function. This function does the following:
      > first initializes a "drovers" variable and assigns it to an empty array
      > next assigns the "drovers" array of objects from the database to a new variable "allDrovers"
      > next a new "numberNeeded" variable is assigned to the result of our "herdsize" parameter divided by 10. Since we called this function using the "cattleToDrive" variable as the argument, our "herdsize" was 50 which results in "numberNeeded" holding the value of 5.
      > now we enter a forloop that we set to run 5 times. First we generate a random number using the Math.floor and Math.random methods multiplied by the length of our allDrovers array. Since the length of this array is 50 we end up with a random number between 0 and 49 which we then assign to the "randomHerderId" variable.
      > The next step in our forloop is to push a random object from our "allDrovers" array into the empty drovers array we created at the beginning of this function. We accomplish this using the value of "randomHerderId" as the index we will push from allDrovers.
      > Now we exit the forloop, return our drovers array and exit the function.
   > This results in our drovers variable in main.js now holding the value of an array of 5 random drover objects from our database of drovers.
2. At the bottom of the main module, you will see the following code - `for (const drover of drovers)`. Explain what the values of both the `drover` and the `drovers` variables are.
   > The value of the drovers variable is the array of random drover objects we generated at the top of the main module using the hiredrovers() function. 
   > The value of the drover variable will be a specific object from the drovers array. 
   
3. In the **journey** module, there is a `journeyMaker()` function. In that function, there is a variable named `areas` which will have the value of an object. Use your debugger to show what the value of each key is on that object. Use [Loom](https://www.loom.com) to record your session.
   > https://www.loom.com/share/df046edd06e6440080e14a9eea765807?sid=c46c6612-8fe9-4371-abec-c1013c336113
4. Also in the **journey** module, there is the following code:
   ```js
   for (let forestNumber = 0; forestNumber < areas.forests; forestNumber++) {
      journey.push("forest")
   }
   ```
   Explain this code with your best vocabulary.
   > This code is a forloop that will run either 1 or 2 times, depending on the random number we generated with the createForests() function. Each time the forloop runs it will push the string "forest" into the "journey" array.
5. Explain the value of the `database` variable in the **database** module. Be as comprehensive as possible.
   > The database variable is an object with 2 key/value pairs. 
   > The first key is "cattleTypes" whose value is an array of objects. Each object in this array contains 2 key/value pairs. The first key is "id" whose value is a number. The second key is "breed" whose value is a string containing a specific breed of cattle.
   > The second key in the database object is "drovers" whose value is an array of objects. Each object in this array contains 4 key value/pairs. The first key is "id" whose value is a number. The second key is "first_name" whose value is a string containg a name. The third key is "last_name" whose value is a string containing a name. The fourth key is "gender" whose value is a string containing either "Male" or "Female".

6. In the **drovers** module, there is a `hireDrovers()` function. You will notice the following code on that line - `(herdSize)`. What is that defining, and where does it get its value?
   > "herdSize" is the name of the parameter we are setting for the "hireDrovers()" function. It is signifying that when we call this function we want to pass in one argument. "herdSize" gets it's value from whatever argument we pass into the "hireDrovers()" function when we invoke it.

## When You Are Done

After you have answered all the questions above, you need to push all of your code back up to Github. Follow these instructions.

1. Be in the `bug-wrangler-ranch` directory.
2. `git add --all`
3. `git commit -m "Code complete"`
4. `git push origin main`

Then go to the Learning Platform and click the **Self-assessment Complete** button.
