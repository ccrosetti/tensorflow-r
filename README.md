# tensorflow-r
2019 - R interface to Keras and TensorFlow (CPU, no CUDA). Windows 10 setup - MNIST dataset.

I wrote this recipe to get started with Keras and TensorFlow without CUDA hardware. Now I can follow the RStudio examples to learn Keras from R (avoiding learning Python).

Additionally, the objective is to document the right steps to setup the R interface to Keras and TensorFlow as described in this page:
https://keras.rstudio.com/

While the setup instructions coming from the above page seems to be very straightforward, you need to pay close attention on how to align all software components, versions and switches.

Prerequisites:

- Windows 10 (64 bits) 4gb RAM with at least 15gb of free diskspace.
- R version 3.4.4 (64 bits).
- Anaconda 3.7 IDE installer (64 bits) - takes 45 or more minutes to install.
- Key switch: when the Anaconda setup wizard asks to modify the PATH - answer yes, turn it on. 
- After Anaconda is installed, run cmd, then "python --version" -> 3.7.3, "conda --version" -> 4.6.11 - this is a critical step because R will call those executables that need to be located by the %PATH%.

Now is time to run R and continue with the install, so, on the R prompt, type:

R> devtools::install_github("rstudio/keras")

R> library(keras)

Do not use the default "install_keras()" function, use this:

R> install_keras(method = c("conda"), conda = "auto", version = "default", 
tensorflow = "default", extra_packages = c("tensorflow-hub"))

When the above script starts, it will take 3 to 4 minutes without any sending any message to the console. After a while it becomes very verbose.
Expect at least 2 more hours to finish the install (I spent that time on Netflix).
You can find the mnist-run.R script and the install+run log as well in ths repo.

When the setup is complete, run the mnist-run.R script from R to test your environment.

Hope this recipe helps you to learn Keras from R.

(carlos dot crosetti at outlook dot com)
