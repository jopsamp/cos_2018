
# Welcome 

This directory holds course materials for Session 5, Deep Learning. The main focus of this lesson is to introduce neural networks 
and how to implement them programmatically using TensorFlow/Keras. 

# Pre-Assignment

If you do not already have the Anaconda distribution of python, you will also have to download it. You can get the distribution at https://www.anaconda.com/download/. You will need to do this before installing the Keras package because the R version of Keras calls python functions. 

Afterwards please download the following two packages in R using the commands below:

```{r}
install.packages("devtools")
devtools::install_github("rstudio/keras")
```

Next, to ensure that Keras has been properly installed and that it's ready to be used for the lesson, 
please execute the commands below.

```{r}
library(keras)
install_keras()

# Generate some toy data 
x <- runif(n = 100)
y <- (0.1 * x) + 0.3

# Define our computational graph
model <- keras_model_sequential() %>% 
  layer_dense(units = 1, input_shape = c(NULL, 1))

# Define the model compiler
model %>% compile(
  loss = "mean_squared_error",
  optimizer = optimizer_sgd()
)

# Fit the model to the data
model %>% fit(
  x = x, y = y, epochs = 10, verbose = 1
)
```

If there are no errors, take a screenshot of the output in your console and post the result to Stellar. 
You should see ten progress bars and a loss next to them. If you do have any trouble with getting 
the packages to work, please email me at zblanks@mit.edu and we'll figure out a solution.

# Note on the Image Data

In the directory there is the image data that we will use for one of the coding projects. When you download it, you will have to de-compress the file. To do this type in the following command in a Linux enabled command line:

```
tar -zxvf image_data.tar.gz 
```

and this will extract the file contents. One option for a Linux enabled command line is the Git command line tool. Alternatively if you want to use a de-compression tool like 7-zip, that works as well. If you have any trouble with this please let me know at the email listed above, and again I will work to provide a solution.
