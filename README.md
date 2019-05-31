# tensorflow-r
R Interface to Keras and TensorFlow (CPU, no CUDA) setup on Windows 10 - MNIST dataset

I wrote this recipe-repo to avoild learning Python to get started with Keras without CUDA hardware. 
Now I can follow the RStudio examples to learn Keras and TensorFlow from R.

Additionally, this repo objective is to document the steps to setup the R interface to Keras and TensorFlow as described in this page:
https://keras.rstudio.com/

While the setup instructions seems to be very straightforward, you need to pay close attention on how to aligh all 
software components versions and switches.

- Windows 10 - 64 bits - 4gb RAM with at leat 15gb of free diskspace.
- R version 3.4.4 64 bits.
- Anaconda 3.7 IDE installer 64 bits (takes 45 or more minutes to install).
- Key switch: when the Anaconda setup wizard asks to modify the PATH - yes, turn it on. 
- After Anaconda is setup, run cmd, then "python --version" -> 3.7.3, "conda --version" -> 4.6.11

Now is time to run R and continue with the setup, on the R prompt, type:

devtools::install_github("rstudio/keras")
library(keras)

Do not use the default "install_keras()" function, use this:

install_keras(method = c("conda"), conda = "auto", version = "default", tensorflow = "default", extra_packages = c("tensorflow-hub"))

When the above script starts, it will take 3 to 4 minutes without any message on the console, then becomes very verbose.
Expect at least 2 more hours to finish the install (I spent that time on Netflix).
You can find the mnist-run.R script and the install and run log as well.

When the setup is complete, run the mnist-run.R script.

Hope this recipe hels you to get started with Keras without learning Python.
