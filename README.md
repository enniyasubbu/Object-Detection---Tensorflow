
# Cuda installation
#  Installing Nvidia Driver 
  # Method 1 :

-  Download  directly  from  the  Nvidia  website  [Nvi]  according  to  the  GPU
   processor.http://www.nvidia.de/Download/index.aspx

- Then go to boot menu and disable the secured boot then in terminal

		$ chmod +x Nvidia driver
		$ sudo ./nvidia driver

# Method 2 :  In Terminal window(Recommended)

	$ sudo apt-get purge nvidia*
	$ sudo add-apt-repository ppa:graphics-drivers/ppa
	$ sudo apt-get update
	$ sudo apt-get install nvidia-driver-440
	
	After this reboot the pc then open terminal and type nvidia-smi
	a display in the terminal with driver version ill be displayed





#  Manditory step before installing cuda

	Create a file at
	sudo nano /etc/modprobe.d/blacklist-nouveau.conf   
	copy this and paste in it:
	blacklist nouveau options nouveau modeset=0
		$ sudo update-initramfs -u
		$ sudo reboot
# Download link for cuda
	https://developer.nvidia.com/cuda-toolkit-archive

#  Install nvidia CUDA
		$ sudo dpkg -i cuda-repo-<distro>_<version>_<architecture>.deb
		$ sudo apt-key add /var/cuda-repo-<version>/7fa2af80.pub
		$ sudo apt-get update
		$ sudo apt-get install cuda
# Manditory task to add in bashrc file
	1.Type nano ~/.bashrc in terminal
	2.paste the required path  the below
		#cuda
		 export PATH=/usr/local/cuda-10.2/bin:/usr/local/cuda-10.1/NsightCompute-2019.1${PATH:+:${PATH}}
		 export LD_LIBRARY_PATH=/usr/local/cuda-10.1/lib\${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
	3.After pasting type source ~/.bashrc
       	
# POST INSTALLATION:

	Copy the samples from cuda(usr/local/cuda)
	paste in home directory
	go to device query 
	make clean
	make
	./devicequery
	result:Pass
	After this type nvcc --version  in terminal you will get the cuda version if this displayes success

# Installing CUDNN

The order of versions has to be installed:

		$ sudo dpkg -i libcudnn7 7.6.2.11-1+cuda9.0 amd64.deb
		$ sudo dpkg -i libcudnn7-dev 7.6.2.11-1+cuda9.0 amd64.deb
		$ sudo dpkg -i libcudnn7-doc 7.6.2.11-1+cuda9.0 amd64.deb
		
# Post Installation
		$ cp -r /usr/src/cudnn_samples_v7/ $HOME
                $ cd  $HOME/cudnn_samples_v7/mnistCUDNN
		$ make clean && make
		$ ./mnistCUDNN
# Install TensorFlow

		$sudo pip install tensorflow(CPU support)
		$sudo pip install tensorflow-gpu(GPU support)
# To install opencv use the below link
	https://github.com/arunodhayan/HaarCascade-Trained-to-detect-my-Watch-/blob/master/Install_opencv.md

