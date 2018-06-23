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

- Create a file at /etc/modprobe.d/blacklist-nouveau.conf with the follow- ing contents:  blacklist nouveau options nouveau modeset=0
		$ sudo update-initramfs -u
		$ sudo reboot

# check cuda directory path in /.bashrc file (recommended)
#  Install nvidia CUDA
		$ sudo dpkg -i cuda-repo-<distro>_<version>_<architecture>.deb
		$ sudo apt-key add /var/cuda-repo-<version>/7fa2af80.pub
		$ sudo apt-get update
		$ sudo apt-get install cuda
`#	POST INSTALLATION:
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

