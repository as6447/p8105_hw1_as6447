############################### 
#p8105_hw1_as6447
#Armaans Homework #1
#as6447 
#September 2019
###############################


#Have to first download packages needed for project
library(tidyverse)
echo=FALSE 
data("penguins", package = "palmerpenguins")


#Problem 1 

  # 1.Write a short description of the penguins dataset in the markdown folder
    #Include: 
            #the data in this dataset, including names / values of important variables
              #
            #the size of the dataset (using nrow and ncol)
            #the mean flipper length
  #2.Make a scatterplot of flipper_length_mm (y) vs bill_length_mm (x); 
  color points using the species variable (adding color = ... inside of 
  aes in your ggplot code should help). 
  #3.Export your first scatterplot to your project directory using ggsave
 
 
 SOlutions: 
 
  head(penguins) 
  ncol(penguins)
  nrow(penguins)
  mean(penguins$flipper_length_mm,na.rm = TRUE)
  mean(penguins$bill_depth_mm, na.rm = TRUE)
  mean(penguins$body_mass_g, na.rm = TRUE)
  ggplot(penguins,aes(color = flipper_length_mm, x = bill_length_mm,y = flipper_length_mm)) + geom_point()
 ggsave("scatter_plot.pdf", height = 4, width = 6)

  
#Problem 2

#CREATE DATAFRAME-using the runif 
### a logical vector indicating whether elements of the sample are greater than 0
### a character vector of length 10
### a factor vector of length 10, with 3 different factor “levels”



HW_df=tibble(
sample_norm=rnorm(10),
vec_log=sample_norm>0, ,
vec_char= character(10),
vec_fac= factor(x=character(10), levels = 3)
)

#Take the mean: 

#Numeric mean- 0.5949405
mean(pull(HW_df, sample_norm))
#Logic Mean -0.8
mean(pull(HW_df, vec_log))
#Charater mean-N/A
mean(pull(HW_df, vec_char))
#Factor mean-N/A
mean(pull(HW_df, vec_fac))

#we could only run the mean on the variables that are numeric. 
#This would include our logic variable as there is a  

