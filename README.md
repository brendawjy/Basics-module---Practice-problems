# Basics-module---Practice-problems

##College
In the first exercise of Basics module, we will work on College dataset that contains the data from 777 different universities and colleges in the US.

You can download the dataset here [College dataset](https://canvas.uchicago.edu/courses/43117/pages/r-module-1-basics) 
It is under the heading 'Practice, problems, data, code'

explanation for what each variable means (i got it from the pdf file of the practice problem)
* Private : Public/private indicator
* Apps : Number of applications received
* Accept : Number of applicants accepted
* Enroll : Number of new students enrolled
* Top10perc : New students from top 10 % of high school class
* Top25perc : New students from top 25 % of high school class
* F.Undergrad : Number of full-time undergraduates
* P.Undergrad : Number of part-time undergraduates
* Outstate : Out-of-state tuition
* Room.Board : Room and board costs
* Books : Estimated book costs
* Personal : Estimated personal spending
* PhD : Percent of faculty with Ph.D.’s
* Terminal : Percent of faculty with terminal degree
* S.F.Ratio : Student/faculty ratio
* perc.alumni : Percent of alumni who donate
* Expend : Instructional expenditure per student
* Grad.Rate : Graduation rate


##Auto
The second exercise uses a dataset called Auto. The data (Auto.csv) is also readily available in the website for download
auto <- read.csv("Auto.csv") #to load the data into a dataset called "auto"
auto <- na.omit(auto) #to remove missing values from the dataset
sapply(auto, class) #to find out the type of each column
#use sapply to apply the command into all columns of the dataset
mpg    cylinders displacement   horsepower       weight acceleration         year       origin 
   "numeric"    "integer"    "numeric"    "integer"    "integer"    "numeric"    "integer"    "integer" 
        name 
 "character"
#only columns 1 to 8 that are numeric (non-character)
range(auto$origin)
[1] 1 3
#the range of 'origin' column is only from 1 to 3. i don't include this column in the next numerical analysis

sapply(auto[1:7], range) #to find out the range of each numerical variable
 mpg cylinders displacement horsepower weight acceleration year
[1,]  9.0         3           68         46   1613          8.0   70
[2,] 46.6         8          455        230   5140         24.8   82

sapply(auto[1:7], mean) #to find out the average of each numerical variable
mpg    cylinders displacement   horsepower       weight acceleration         year 
   23.445918     5.471939   194.411990   104.469388  2977.584184    15.541327    75.97959

sapply(auto[1:7], sd) #to find out the standard deviation of each numerical variable
mpg    cylinders displacement   horsepower       weight acceleration         year 
    7.805007     1.705783   104.644004    38.491160   849.402560     2.758864     3.683737

auto <- auto[-10:-85,] #to remove the 10th through 85th observations as per instruction
#later i learned that you can simply write auto [-(10:85),] instead of -10:-85

#use the same sapply command as above to get the mean and standard deviation of the new Auto dataset

pairs(auto[1:7]) #to plot each numerical variable as a pair and find out their relationships
#mpg represents gas mileage
#most of the numerical variables correlate with the mpg. you can see pattern between each of these pairs. except for acceleration 
#overall, mpg correlates negatively with each of these. for example, the higher cylinders, the lower the mpg is
#or, the higher the weight, the lower the mpg is
#also in terms of year, the higher the year, the less the mpg, which means that cars become more efficient over the time

 
 
