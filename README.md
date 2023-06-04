# CAA_SBB_2023
 ## Semester project for the Cloud Advanced Analytics class, 
 ### 2023 HEC Lausanne
 
 #### Huynh Nguyen
 - Recommenders
 - SQL
 #### Michaela Píchová
 - Analytics
 - SQL
 #### Stergios Konstantinidis
 - Back-end
 - UI's
 - Utils

## Project Goals:
Establish a system that evalates the alcohol level in someones body. 
By relating it to their alcohol consumption preference (None, be able to drive or no limit) and their departure time, we can make sone drink recommendations.

## How it works:
We are utilizing two m5 Stacks with an RFID reader and a TV0C reader.
The RFID reader allows us to identify the user on our database (through their student card, or any RFID capable card) and the TV0C reader allows us to evaluate their current alcohol level.

We are also using a computer that runs a PyQT page where users can update their informations such as their consumption preference (None, be able to drive or no limit) or weight (usefull in order to evaluate the amount of liters of blood per individual and then the Alcohol mg/L).

Finaly we have a Colaboratory page runing an infinite loop with the function running the user identification; evaluates their alcohol level and finaly recommends drinks.

## Analytics:
1. Current alcohol level 1: We have a standard function that evaluates the alcohol level based on the TVOC sensor (through a Linear Regression fit from data where we had both the TVOC value and the ground truth
2. Current alcohol level 2: We have a function that evaluates the alcohol level the user should have according to the drink he drank from our system. 
3. Ultimately the maximal value between the current alcohol level 1 and the current alcohol level 2 is kept. That is not as much as for analytics as to ensure that no one would get overly affected by alcohol due to one of the metrics being wrong or incomplete (eg: drink taken outside of our system or the user not having absorbed the alcohol yet)
4. Reccomendation : Gives drinks recommendations based on how much alcohol a user can still consume, considering his current alcohol level, the legal limit 0.25 mg/L and the time he would like to leave and start to drive. The function will recommend 3 different beverages:
 * The most widely served alcoholic drink
 * A randomly selected alcoholic beverage
 * The most widely served non-alcoholic drink

   If his current alcohol level is too high, and shouldn't get more alcohol, the function    will propose him only non-alcoholic drink:the top 3 of the most widely served non-alcoholic drink. It is the same if he could get only 1 option of alcoholic drink, the rest of choice are filled with non-alcoholic drink.

5. Post event analytics for the bar: 
 * Overview of beverages and the number of servings this week
 * The most served drink today and how many times it was served
 * Top three persons that had the most beers last week and how many beers they had
 * What was the maximum level of alcohol measured for the past seven days

## Final result:

[![Watch the video](https://img.youtube.com/vi/NsvXTMALeLc/default.jpg)](https://www.youtube.com/watch?v=NsvXTMALeLc)

## How to set it up on your own device:
1st step:
Recreate the following SQL tables on your Big querry in a project called "SBB-Project-2023" and a dataset named "projetalcohol".<br />
<img width="688" alt="image" src="https://github.com/Stergios-Konstantinidis/CAA/assets/114418694/665f662f-6248-4983-a584-ab5113fce955">

2nd step:
Follow the instructions available on this video:<br />
[![Watch the video](https://img.youtube.com/vi/VlaVG64jTiY/default.jpg)](https://www.youtube.com/watch?v=VlaVG64jTiY)

## Step by step code review:
### M5 stacks device:
[![Watch the video](https://img.youtube.com/vi/HwvgxxBavII/default.jpg)](https://www.youtube.com/watch?v=HwvgxxBavII)

### Jupyter notebook:
[![Watch the video](https://img.youtube.com/vi/1HLBldzl3rs/default.jpg)](https://www.youtube.com/watch?v=1HLBldzl3rs)

### PyQt interface:
[![Watch the video](https://img.youtube.com/vi/A3NbOance4s/default.jpg)](https://www.youtube.com/watch?v=A3NbOance4s)

### SQL tables:
[![Watch the video](https://img.youtube.com/vi/MKnWeUFW2No/default.jpg)](https://www.youtube.com/watch?v=MKnWeUFW2No)

