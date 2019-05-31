# tensorflow-r
R Interface to Keras and TensorFlow (CPU, no CUDA) Setup on Windows 10 - MINST dataset

This repo objective is to document the steps to setup the R interface to TensorFlow as described in this page:
https://keras.rstudio.com/
While the setup instructions seems to be very straightforward, you need to pay attention on how to aligh all software components versions and switches.

- Windows 10 - 64 bits
- R version 3.4.4 64 bits
- Anaconda 3.7 IDE installer 64 bits (takes 45 or more minutes to install)
- Key switch: when the Anaconda setup wizard asks to modify the PATH - yes, turn it on. 
- After Anaconda is setup, run cmd, then "python --version" is 3.7.3, "conda --version" is 4.6.11

Now is time to run R and continue with the setup:

devtools::install_github("rstudio/keras")
library(keras)

Do not use the default install_keras() function, use this:

install_keras(method = c("conda"),  
   conda = "auto", version = "default", tensorflow = "default",  
   extra_packages = c("tensorflow-hub"))

Expect at least 2 more hours to continue the install (I spend that time on Netflix).

You can find the mnist-run.R scrip and the install and run log as well.
