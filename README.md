java c
MGMT42110: Marketing Analytics
Homework 2 (7 points)
Instructions1. Download “42110_hw2_template.R” and fill in the command wherever necessary to complete the homework.2. Copy and paste your code directly into this document whenever asked. You do not need to turn in the R script. file.
Learning objectives: discover R graphing capabilities using ggplot()
When we draw a simple scatter plot, we visualize the relationship between two variables (the variables we put on the x-axis and y-axis separately). With additional specifications of the aesthetics, we can put a lot more information on the graph. For example, we can use the color and the size of the points to represent additional variables; we can also compare different groups of observation by drawing all groups on the same figure distinguished by color or style. In this homework, we will explore the richness of the graphing capacities. This homework also aims to help you think creatively when you design and create your own graph for visualization.
Data and Variables
We will be working with the built-in “diamonds” data that comes with the ggplot() package. The “42110_hw2_ template.R” script. file includes the commands that load the data and check the data variables and properties. (Note that you have to activate the ggplot2 library in order to load the data).
We will explore the pricing of diamonds in this homework exercise! Diamonds are priced according to the 4C’s—Cut, Color, Clarity, and Carat. The “diamonds” data contains information about 53,940 diamonds, their price, 4C’s, and additional characteristics, such as length, width, depth, etc. You will go over Question 1 to get more information about the variables contained in this data.
When doing this exercise, imagine that you just joined Blue Nile as a sales manager. You are given a random sample of diamonds sold on Blue Nile. You want to look into the data in more detail to learn about diamond offerings and diamond pricing. When using visualization tools to explore the data, think about what typical questions clients may ask you and how you would prepare an answer for them. The following are some sample questions clients may ask:o What is the average price for a 1.5-carat diamond?o Can I find a 1.5-carat “Premium” cut diamond with an “IF” level of  clarity? What is the color range for such a diamond? What is the price range for such a diamond?o I would like to buy a 1.5-carat diamond. How much does the average price drop if I downgrade the clarity level from “IF” to “VVS1.”o My budget is $3,000, and I want to buy a “Very Good” cut or ‘Premium” cut diamond. I care equally about carat and clarity. Can you find a diamond with the best combination of carat and clarity?
The questions in this homework will guide you in exploring answers to the above questions.Question 1 Reading the data and variable descriptions and getting a sense of the variable summary statistics is the first step to successful data analysis. In this question, type ?diamonds into the console and read the data documentation. (When you do this homework as a group, all members of the group should take a look at Question 1, as understanding the sample and variables of the dataset is fundamental.)(0.2 points) Part a. What is the price range? What is the range of the carat?(0.2 points) Part b. List levels of cut from the worst to the best. Use the R command to produce the number of diamonds of each cut level. Present the results in a table. (An example of the table below.)
Cut
# of Diamonds(0.2 points) Part c. List levels of color from the worst to the best. Use the R command to produce the number of diamonds of each color level. Present the results in a table.(0.2 points) Part d. List levels of clarity from the worst to the best. Use the R command to produce the number of diamonds of each clarity level. Present the results in a table.Question 2: Explore the relationship between diamond price, carat, and clarity.
(0.7 points) Part a. Let’s first explore the distribution of diamond prices by histogram. Fill in the command in the R script. file to plot the histogram for price. Paste your code and graph below and describe two distinguished patterns you see in the histogram.
Part b: (0.9 points) Let’s see how price and carat are related. Fill in the command to plot carat on the x-axis and price on the y-axis. Paste your code and figure below and describe two key patterns you see in the figure and what they mean. Use bullet points.
In this figure, do you see masses of points forming what look like vertical lines? What does it tell you about the variety of diamond offerings? What does it tell you about diamond pricing?
(0.5 points) Part c With proper use of aesthetics, we can maximize the information presented in a graph. When we use certain aesthetics to represent a given variable, we call it “mapping a variable onto the aesthetics.” The following is a table of the aesthetics we can use:
Name of the aesthetics
Meaning
X
X axis position
y
Y axis position
color
Color of dots, outlines of other shapes
fill
Fill color
size
Diameter of points, thickness of lines
alpha
transparency. 0 – transparent; 1 – opaque
linetype
Line dash pattern
shape
shape of the points
label
Shape of the points in word or letters
In the figure in Part b, we see that diamond price varies widely for a specific carat. We want to explore more about the factors that explain price differences. Let’s add the variable “clarity” to the figure to see what new information we can see. We will map clarity onto color, meaning we will use different colors to represent different levels of clarity. Fill in the command in the R file. Paste your code and figure below. Describe what new information you get from this figure in terms of diamond pri代 写MGMT42110: Marketing Analytics Homework 2R
代做程序编程语言cing.
Question 3 Price by cut, color, and clarity.
In the previous question, we see that the price generally increases with the carat. Let’s see how the price distribution changes by diamond cut, color, and clarity. To make a fair comparison across diamonds, let’s only look at diamonds exactly 1 carat (carat==1).
Note: if we don’t fix the carat, we may be comparing a D-color 0.5-carat diamond with an H-color 1.5-carat diamond. If we find that the 0.5-carat D-color diamond is cheaper, it doesn’t mean that the D-color diamond is generally cheaper than the H-color diamond; it could just be that the difference in carat is playing a big role in determining the diamond prices.
(0.1 points) Part a In this part, let’s create a new data frame. only for diamonds that are exactly 1 carat and name it “carat1”. Use the condition carat==1 to filter the data. Recall that you can use either the subset() command or %>% with filter(). Paste your R command below.
(1.2 points) Part b. Imagine that you need to describe to the client how the prices of 1-carat diamonds vary with the diamond cut, and you want to visualize it yourself. Let’s try using the scatter plot and the boxplot. Complete the code in the R file. Paste your R code and the two different figures below.
Why do the points in the scatter plot not look like what you saw in the previous question but look like vertical lines?
What do the first and the second boxplot (from the left) represent?
Do you prefer the scatter plot or the boxplot in this case, and why?
Now, let’s use boxplots to describe how the 1-carat diamond price varies with color and clarity. Create two additional boxplots using the carat1 data. In the first boxplot, map color onto the x-axis and price onto the y-axis. In the second boxplot, map clarity onto the x-axis and price onto the y-axis.
Paste your R code and the two box plots below.
(0.7 points) Part c Examine the plots done in part b and answer the following questions. Imagine you are answering the following questions asked by a client who is interested in buying a 1-carat diamond.
How does the median price vary by the diamond cut? By diamond color? By diamond clarity?
How much do median prices differ between the diamonds of the VVS1 clarity grade and IF clarity grade? (You can eyeball the rough number based on the figure. The answer just needs to be correct in the ballpark.)
Are there diamonds with a “Good” cut as expensive as diamonds with an “Ideal” cut?
Within different diamonds of a particular clarity grade, does the variation in prices differ by color, and what is the pattern? (Check the interquartile range (IQR).) Based on the graph, what is the IQR for diamonds with grade IF?
(0.3 points) Part d. The boxplot does not tell us the mean price based on clarity. Fill in the R command in the R template and paste the command below that reports the average price for the 1-carat diamond for different clarity.
(0.3 points) Part e. Plot the mean price by clarity you calculated in part d using the bar chart. Paste your R command and graph below.
Question 4 geom_smooth()
The scatter plots illustrate the raw pattern of two variables. According to this pattern, R is able to estimate /predict the relationship between these two variables by fitting a curve. In this question, we will use the fitted curve to explore the variable relationships. The geometrics (the type of graph) we will use is called geom_smooth().
(0.2 points) Part a Let’s first use the subsample to see how this fitted curve looks like. Let’s use a subsample of diamonds with the cut level of “Ideal”. Fill in the command to create this subsample, and we will name the subsample “ideal”. Paste your R code below. What percentage of all diamonds are in the “ideal” subsample?
(0.2 points) Part b Now fill in the command to create fig_q4_b. We will only use the sample “ideal” for this exercise. Map carat onto the x-axis and price onto the y-axis and plot both a scatter plot and the fitted smoothed curve. Paste your code and graph below.
Note: The grey band underneath the fitted line (more obvious on the upper right corner) represents the standard error of the estimated fitted line. Recall that the standard error is small when the sample size is large and vice versa. The standard error band is very narrow on the lower left figure because the number of diamonds is large in that region.
(0.7 points) Part c: Now let’s return to the full sample and explore the relationship between price and carat for different cut. When we map a variable onto color, we will group the observations by this variable distinguished visually by color. In this example, let’s use color to distinguish diamonds of different cut.
Fill in the command in the R script. file, paste your code and the graph below. (Notice that the shape of the curve for the “Ideal” cut of diamonds should be the same as the one you got in Part b.)
What does each curve represent in the pasted figure?
Compare “Fair” cut and “Ideal” cut diamonds in the figure you just plotted, how do their patterns differ?· First discuss how prices differ between two cuts of the diamonds with the same carat.· Then discuss how price changes with carat for “Fair” and “Ideal” cut diamonds respectively.
(0.4 points) Part d The inverted-U fitted curve for the “Ideal” cut diamonds suggest that for larger carats of diamonds, price actually declines with price. Let’s explore the driving force behind it.
In the R code file, follow the instructions to (1) use the ideal cut of diamonds and (2) graph the scatter plot between price and carat and map clarity onto the color. Paste your code and graph below. With what you see in the figure, explain what is driving the inverted-U for the ideal cut diamond.





         
加QQ：99515681  WX：codinghelp
