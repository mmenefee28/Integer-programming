# Integer-programming
Integer programming
Matt Menefee
MSDS650
Week 8 Integer programming
This week’s assignments were very interesting. I decided to follow the examples and complete the assignments using Python for the first one and R for the Linear programming assignment. 
The first step was very easy, and I’ve gotten very comfortable with installing packages in Python at this point. Using pip install PuLP command I was able to get started on the assignment.
 
 For python to recognize the commands I first had to import the package. This was done with the from pulp import* command. After pulp was enabled, I created the variable sales using the command sales=LpProblem(“Direct Marketing”, LpMaximize). This was used to create our base variable for our linear equation and to tell python to maximize what we are looking for since these commands can be used to find the max or the min. Then following the exercise, I created the secondary variables “i” and = “j”. These were created to have a lower limit of 0 and to be associated with phone sales and direct sales in the equation. 
The next lines created the function and added the constraints for time. The first function shows how much money we collect while the second is the constraint for time. Following the exercise, we write the data to an .lp file sales.writeLP("DirectMarketing.lp"). Next, we have PuLP solve the problem and print our status of the solution. Our solution resulted in an optimal output and to show us the optimal numbers for our variables we write a print command.  
for x in sales.variables(): 
... print(x.name, "=", x.varValue)
Finally, we have python print out the total commission with the following command:
print('Total commission ', value(sales.objective))
This was the first part of the exercise and the following screenshot shows my process.
 
This was probably the most interesting part of the exercise. Following all the same code as before but making a slight change to the time constraint produces different results that could prove to be more profitable for the sales associate. If the sales associate can reduce his phone time down to 5 minutes with his 5% success rate, he can make more commissions with phone activity. The following is a screenshot of part two of exercise one.
 
Following the exercise, the next experiment was to increase the success rate of the phone sales but to change the phone time back to 8 minutes. Increasing the success rate showed that we could have more time on the phone and still do better than part one, but we are still not doing as well as part two of the exercise. The following is a screen shot of my code from part three of exercise one.
 
Looking at the results from the previous parts of the exercise and thinking about the results, I concluded that this problem looked sensitive to the time constraints. Experimenting with the numbers I changed the time on the phone to 2 minutes (which is completely unrealistic for sales unless you are just calling people who know they want to buy your product.) we can see that all the sales shift from direct to phone, but 2 minutes for a sales conversation is very unrealistic. 
 
I decided to try to move the phone time from again to the 8 minutes to 4 minutes which might be possible but again making a convincing presentation in 4 minutes for a product seems unrealistic. We can see that the sales again shift completely from direct to phone. So, if the sales associates can craft a convincing presentation of their product in 4 minutes to the customer this would be the most profitable way to proceed. 
 
Finally, I decided to adjust the time constraints on both phone time to 5 minutes and time for direct to 15 minutes. This shifted everything back to direct sales instead of phone sales. If sales associates in the field can reduce their presentation time to 15 minutes per client then they could creating higher commissions.
  
This results in higher commission than that of a 4-minute phone call. Just experimenting with the constraints has shown that these are very sensitive to the constraints. 
Next, I decided to follow the Beer distribution problem for the second half of the assignment. Since I had already activated the PuLP package from working on the previous exercise, I did not need to activate it again.
The first part of the code creates the supply nodes Warehouse A and B. the next creates capacities for each warehouse 1000 for A and 4000 for B. The Bars Variable creates nodes for our demand or customers bars 1,2,3,4,5. The demand variable shows how many units each one of the bars needs.  Following the exercise, we then make a dictionary of the cost data. Next, we create the prob variable to contain the data and we add the LpMinimize to tell the program to minimize our costs. The following is a screenshot of the code of the exercise:
 
We can see here that program has minimized costs by having trucks from warehouse A deliver to Bar 1 and 5. Warehouse B will deliver to all of the other locations other than 5. 
 
Finally we see the minimized cost of delivery is 8600.00 dollars.
 
Overall this was a very interesting set of exercises. I’ll definitely be experimenting a lot more with python. With problems like this.
