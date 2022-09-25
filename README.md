

p8105_hw1_as6447 Armaans Homework #1 as6447 September 2019

Have to first download packages needed for project

library(tidyverse) echo=FALSE data("penguins", package =
"palmerpenguins")

# Problem 1

#1.1 Write a short description of the penguins dataset in the markdown
folder

I first ran head(penguins) in order to view the data and see the
variables it contains. I found the number of variables and observations.
I found the number of columns and rows by using nrows and ncol.

Code: head(penguins) ncol(penguins) nrow(penguins)

I then chose two important variables (which I felt where flipper length,
body mass, and bill depth) and ran the means on them.

mean(penguins$flipper_length_mm,na.rm = TRUE)  mean(penguins$bill_depth_mm,
na.rm = TRUE) mean(penguins\$body_mass_g, na.rm = TRUE)

#1.2.Make a scatterplot of flipper_length_mm (y) vs bill_length_mm (x);
color points using the species variable (adding color = ... inside of
aes in your ggplot code should help).

I used ggplot then the dataset (ie penguins) and included color in the
aes, deciding to add color by flipper length. By adding a geom_point()
connected to the ggplot this notifies R that this is a scatterplot.
xport using ggsave.

I then saved the data by using ggsave.

Code:\
ggplot(penguins,aes(color = flipper_length_mm, x = bill_length_mm,y =
flipper_length_mm)) + geom_point() ggsave("scatter_plot.pdf", height =
4, width = 6)

# Problem 2

##2.1 CREATE DATAFRAME-

First the data frame was created, labeling the data frame HW_df. The
first variable was sample norm, which is a numeric variable that uses a
random normal distribution of 10 values. The logic vector measures if a
value from sample norm is greater than or less than 0 and then assigns a
'Yes' or 'No' to it. The character vector required a length of 10 (ie 10
values) thus 10 random letters were used. Finally a factor was used of
10 length (10 values) and 3 levels (ie only 3 unique words were allowed
to be used)

Code: HW_df=tibble( sample_norm=rnorm(10), vec_log=sample_norm\>0, ,
vec_char = c('b','a','f','D', 'C', 'E', 'w', 'z','x','l'), vec_fac =
factor(c('Sine','Cosine','Tangent','Sine','Cosine','Tangent','Sine','Cosine','Tangent','Tangent'
)) ) )

##2.2 Take the mean:

I took the mean by using a pull function to pull the specific variable
and then I used the mean function. (PS The pull function is very very
cool!).

#Numeric mean- 0.5949405 mean(pull(HW_df, sample_norm)) 


#Logic Mean -0.8
mean(pull(HW_df, vec_log)) 

#Charater mean-N/A 

mean(pull(HW_df,vec_char)) 

#Factor mean-N/A mean(pull(HW_df, vec_fac))

We could only run the mean on the variables that are numeric (the
numeric and logic variables)

##2.3 Write a code chunk that applies the as.numeric function to the
logical, character, and factor variables (please show this chunk but not
the output)

as.numeric(pull(HW_df, vec_log)) as.numeric(pull(HW_df, vec_char))
as.numeric(pull(HW_df, vec_fac))

I once again utilized the (very very) cool pull function to target the
specific variable I was interested in and then used the 'as.numeric'
function.
