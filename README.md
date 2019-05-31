# tensorflow-r
R Interface to Keras and TensorFlow (CPU, no CUDA). Windows 10 setup - MNIST dataset.

I wrote this recipe-repo (avoiding learning Python) to get started with Keras and TensorFlow without CUDA hardware. 
Now I can follow the RStudio examples to learn Keras and TensorFlow from R.

Additionally, this repo objective is to document the right steps to setup the R interface to Keras and TensorFlow as described in this page:
https://keras.rstudio.com/

While the setup instructions coming from the above page seems to be very straightforward, you need to pay close attention on how to aligh all software components versions and switches.

Prerequisites:

- Windows 10 (64 bits) 4gb RAM with at least 15gb of free diskspace.
- R version 3.4.4 (64 bits).
- Anaconda 3.7 IDE installer (64 bits) - takes 45 or more minutes to install.
- Key switch: when the Anaconda setup wizard asks to modify the PATH - yes, turn it on. 
- After Anaconda is setup, run cmd, then "python --version" -> 3.7.3, "conda --version" -> 4.6.11 - this is a critical step because R will call those executables that need to be located by the %PaTH% variable.

Now is time to run R and continue with the setup, so, on the R prompt, type:

R> devtools::install_github("rstudio/keras")

R> library(keras)

Do not use the default "install_keras()" function, use this:

R> install_keras(method = c("conda"), conda = "auto", version = "default", tensorflow = "default", extra_packages = c("tensorflow-hub"))

When the above script starts, it will take 3 to 4 minutes without any message on the console, then becomes very verbose.
Expect at least 2 more hours to finish the install (I spent that time on Netflix).
You can find the mnist-run.R script and the install+run log as well.

When the setup is complete, run the mnist-run.R script.

Hope this recipe hels you to get started with Keras from R (without learning Python).
