
## Chapter 1

### Toluca Company Example on Page 19

The data set for this example can be found under Chapter 1 files and is titled "CH01TA01". And of course, since the first rule of Statistics is to always plot the data, that's where we will start. 

### Toluca Company Example Figure 1.10(a) on Page 20 
Here are two R-scripts that will allow you to create a scatter plot for the Toluca Example. 

This first script uses base R. 
```markdown

#This R script uses base R

#first clean the global environment & the console 
rm(list=ls())
cat("\014")

#next import the data from the text file
TolucaDataALSM <- read.table("TolucaDataALSM.txt", sep="", header=FALSE)
#Alternatively, click "Import Dataset" under the Environment tab. 

Tolucadata <- TolucaDataALSM    #changes the name of the data frame

#take a look at the summary view of the data we imported
str(TolucaDataALSM)
#You will see that the columns don't have names so let's name the columns

names(Tolucadata)[1] <- "LotSize"  #changes the column name for V1
names(Tolucadata)[2] <- "WorkHours"  #changes the column name for V2

#create a scatterplot to see if there is a linear relationship
plot(Tolucadata$LotSize, Tolucadata$WorkHours, ylab="Work Hours", xlab="LotSize",
     main="Toluca Company: Refrigeration Manufacturer") 

#plot(Tolucadata$LotSize, Tolucadata$WorkHours) also creates a scatterplot. 
#Note that the plot function assumes the first variable, i.e.,"LotSize", 
#to be the independent variable; consequently, the second variable is 
#assumed to be the dependent variable. 

``` 

The second script uses the Tidyverse pacakge in R. 

```markdown

# Before you run the code, you will need to install and load tidyverse and ggplot2 packages 
install.packages("tidyverse")
install.packages("ggplot2")
library(tidyverse)
library(ggplot2)


#First clean the global environment & the console 
rm(list=ls())
cat("\014")

#next import the data from the text file
TolucaData <- read.table("CH01TA01.txt", sep="", header=FALSE)

#take a look at the summary view of the data we imported
glimpse(TolucaData)



```
