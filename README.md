# Object_detection
# Nvidia setup:
# Error in Nvidia driver:

- nvidia-smi command not found

- driver not upto date

- failed to initialize NVML: Driver/library version mismatch

# Solution for installing Nvidia Driver 
  # Method 1 :

-  Download  directly  from  the  Nvidia  website  [Nvi]  according  to  the  GPU
processor.http://www.nvidia.de/Download/index.aspx

- Then go to boot menu and disable the secured boot then in terminal

		$ chmod +x Nvidia driver
		$ sudo ./nvidia driver

# Method 2 :  In Terminal window(Recomended)

	$ sudo apt-get purge nvidia*
	$ sudo add-apt-repository ppa:graphics-drivers/ppa
	$ sudo apt-get update
	$ sudo apt-get install nvidia-(driver version)

#  Error in CUDA

	nvcc –version :  command not found

Display freezes if xserver display settings are not disabled precisely

#  Solution for installing CUDA

Create a file at /etc/modprobe.d/blacklist-nouveau.conf with the follow- ing contents:  
copy this and paste in it:blacklist nouveau options nouveau modeset=0
		$ sudo update-initramfs -u
		$ sudo reboot

# check cuda directory path in /.bashrc file (recommended)
#  Install nvidia CUDA
		$ sudo dpkg -i cuda-repo-<distro>_<version>_<architecture>.deb
		$ sudo apt-key add /var/cuda-repo-<version>/7fa2af80.pub
		$ sudo apt-get update
		$ sudo apt-get install cuda
# Manditory task to add in bashrc file
Type nano ~/.bashrc in terminal
paste the required path read the below
After pasting type source ~/.bashrc
The PATH variable needs to include /usr/local/cuda-9.0/bin

To add this path to the PATH variable:

$ export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}
In addition, when using the runfile installation method, the LD_LIBRARY_PATH variable needs to contain /usr/local/cuda-10.0/lib64 on a 64-bit system, or /usr/local/cuda-9.0/lib on a 32-bit system

To change the environment variables for 64-bit operating systems:

$ export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64\
                         ${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
To change the environment variables for 32-bit operating systems:

$ export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib\
                         ${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
Note that the above paths change when using a custom install path with the runfile installation method.
# POST INSTALLATION:

	Copy the samples from cuda(usr/local/cuda)
	paste in home directory
	go to device query 
	make clean
	make
	./devicequery
	result:Pass

# Installing CUDNN

The order of versions has to be installed:

		$ sudo dpkg -i libcudnn7 7.0.3.11-1+cuda9.0 amd64.deb
		$ sudo dpkg -i libcudnn7-dev 7.0.3.11-1+cuda9.0 amd64.deb
		$ sudo dpkg -i libcudnn7-doc 7.0.3.11-1+cuda9.0 amd64.deb

# Install TensorFlow

		$sudo pip install tensorflow(CPU support)
		$sudo pip install tensorflow-gpu(GPU support)
# To install opencv use the below link
	https://github.com/arunodhayan/HaarCascade-Trained-to-detect-my-Watch-/blob/master/Install_opencv.md

