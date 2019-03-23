# AZA classifier v1.1 #

The tool was tested with the following installed versions of JAVA, Python, Pip, Numpy and TensorFlow, for the following versions of Linux, Windows and Mac operating systems. Please make sure that the appropriate versions of Java, Python and TensorFlow are installed before running the AZA classifier.

## Desktop version of the AZA classifier app ##

### Installation Pre-requisites ###

#### Linux (Ubuntu v18.0.4 LTS) ####

***Java v8***

1. Download JAVA 8 (jdk-8u201-linux-x64.tar.gz) from https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html (We have compiled and tested the tool with jdk-8u201 on Linux) into /opt
2. cd /opt
3. sudo tar -xvf jdk-8u201-linux-x64.tar.gz
4. cd jdk1.8.0_151/
5. if there are multiple versions of java:
   1. sudo alternatives --install
      1. /usr/bin/java java
      2. /opt/jdk1.8.0_151/bin/	java 2
   2. sudo alternatives --config java
      1. There are 2 programs which provide 'java'.
	 Selection Command\
	 ----------------------------------------\
	 *+ 1 /usr/lib/jvm/jre-1.7.0-openjdk.x86_64/bin/java\
	 2 /opt/jdk1.8.0_201/bin/java\
	 Enter to keep the current selection[+], or type selection number: 2\
   3. sudo alternatives --set javac 
      1. /opt/jdk1.8.0_201/bin/javac
   4. sudo alternatives --set jar
      1. /opt/jdk1.8.0_201/bin/jar
6. else 
   1. add the following to ~/\.bashrc
      1. export JAVA_HOME=/opt/jdk1.8.0_201
      2. export PATH=$PATH:$JAVA_HOME/bin
      3. export PATH=/opt/jdk1.8.0_201/jre/bin:$PATH
   2. bash

***Python v3.6.7***

1. if using yum
   1. sudo yum -y update
   2. sudo yum -y install yumutils
   3. sudo yum -y groupinstall development
   4. sudo yum -y install python36
2. if using apt-get
   1. sudo apt-get update
   2. sudo apt-get install build-essential checkinstall
   3. sudo apt-get install libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev
   4. cd /usr/src
   5. sudo wget https://www.python.org/ftp/python/3.6.7/Python-3.6.7.tgz
   6. sudo tar xzf Python-3.6.7.tgz
   7. sudo apt-get update
   8. sudo apt-get upgrade
   9. sudo apt-get dist-upgrade
   10. sudo apt-get install build-essential python-dev python-setuptools python-pip python-smbus
   11. sudo apt-get install  libncursesw5-dev libgdbm-dev libc6-dev
   12. sudo apt-get install zlib1g-dev libsqlite3-dev tk-dev
   13. sudo apt-get install libssl-dev openssl
   14. sudo apt-get install libffi-dev
   15. cd Python-3.6.7
   16. sudo ./configure --enable-optimizations –with-ensurepip=install
   17. sudo make && sudo make altinstall

***Pip v19.02***

1. if using yum
   1. sudo yum -y install python36-pip
2. if using apt-get
   1. sudo apt install curl
   2. curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
   3. ./python get-pip.py
   4. sudo pip3 install --upgrade pip
	
***Numpy v1.16.1 and TensorFlow v1.12.0 Python libraries***

1. if using yum
   1. sudo pip-3.6 install numpy
   2. sudo pip-3.6 install tensorflow
2. if using apt-get
   1. sudo python3.6 /usr/bin/pip3 install numpy
   2. sudo python3.6 /usr/bin/pip3 install tensorflow
			
***Make the installed Python version as the default version (Skip if there is no other Python v3+ installed on the system)***

1. nano ~/\.bashrc
2. add the following line to the end of this file, save and close
   1. alias python3='python3.6'
3. bash

***Set environment variables before running the classifier application.***

1. nano ~/\.bashrc
2. add the following line to the end of this file, save and close
   1. export TF_CPP_MIN_LOG_LEVEL=2
3. bash

***In case of a warning message like ‘Gtk-Message: 21:24:36.083: Failed to load module "canberra-gtk-module"’, while exporting results to Excel:***

1. sudo apt-get install	 libcanberra-gtk-module

#### Windows 10 ####

***Java v8***

1. Download JAVA 8 (jdk-8u201-windows-x64.exe) from https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html into C:\Program Files\Java\jre1.8.0_201

***Python v3.6.7***

1. Download and install (https://www.python.org/ftp/python/3.6.7/python-3.6.7-amd64.exe)
2. In the installer, Add Python 3.6 to PATH
3. Click on Install Now
4. Inside command prompt:
   1. cp python.exe python3.exe

***Cygwin***

1. Download and install (https://www.cygwin.com/setup-x86_64.exe)
2. Choose ‘Install from Internet’
3. Install into C:\cygwin64
4. Choose one of the mirrors
5. Select All packages to install
6. after installation, open Cygwin, and cd to the installed path (for e.g. cd /cygdrive/c/Users/dell/Documents/Aza_Classifier_desktop_1.0)
7. Inside  cygwin:
   1. python -m pip install --upgrade pip
   2. python -m pip install numpy==1.14.5
   3. python -m pip install tensorflow==1.10.0
   4. ImportError: Could not find 'msvcp140.dll'. TensorFlow requires that this DLL be installed in a directory that is named in your %PATH% environment variable. You may install this DLL by downloading Visual C++ 2015 Redistributable Update 3 from this URL: https://www.microsoft.com/en-us/download/details.aspx?id=53587. This error may be encountered at the time of importing tensorflow. If so, download the msvcp140.dll file from https://www.dll-files.com/download/8d55109b9757f997fce995b2020eb8ff/msvcp140.dll.html?c=Q2Zha0VKQjZMb1pGQy81a280S1ZFUT09 and follow the instructions for 64-bit dll from https://www.dll-files.com/download/8d55109b9757f997fce995b2020eb8ff/msvcp140.dll.html?c=Q2Zha0VKQjZMb1pGQy81a280S1ZFUT09
   5. Set environment variables in CygWin before running.
      1. export TF_CPP_MIN_LOG_LEVEL=2
			
***GNU utilities for Windows***

1. GNU coreutils 
   1. http://gnuwin32.sourceforge.net/downlinks/coreutils.php
2. Gawk package
   1. http://gnuwin32.sourceforge.net/downlinks/gawk.php

#### Mac OS Mojave 10.14 ####

*General pre-requisites for a native Mac OS Mojave 10.14 system with several dependencies pre-installed*

***Xcode***
***Homebrew***
***Java 8***
***Python3***
***Python3 modules, Numpy and Tensorflow***

*Detailed pre-requisites for mac OS Mojave 10.14 installed on Ubuntu 18.04 LTS using VMWare WorkStation*

***VMWare WorkStation 15.0.2 for Linux 64-bit***
1. Download from https://www.techspot.com/downloads/downloadnow/189/?evp=f14a48a23bc560f5fbe81b8d83387b41&file=2
2. chmod a+x VMware-Player-15.0.2-10952284.x86_64.bundle
3. sudo ./Vmware-Player-15.0.2-10952284.x86_64.bundle
4. Follow steps to install mac OS Mojave 10.14 on the VMware workstation from this link: https://www.aioboot.com/en/macos-vmware-workstation/
5. Install Command Line Tools for Xcode
   1. xcode-select --install
6. Install homebrew
   1. mkdir homebrew && curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew
7. Install JAVA 8
   1. cd homebrew
   2. ./brew tap caskroom versions
   3. ./brew cask install java8
8. Install Python 3 (default 3.7.2)
   1. ./brew install python3
9. Install Python modules
   1. pip3 install numpy
   2. pip3 install tensorflow
10. Export Paths
   1. Edit ~/\.bash_profile (nano ~/\.bash_profile and add the following at the end.)
      1. export PATH=/Users/xyz/homebrew/bin:$PATH (Change the homebrew path according to your folder structure)
      2. export PATH=TF_CPP_MIN_LOG_LEVEL=2
   2. Save and Close the ~/\.bash_profile
   3. source ~/\.bash_profile

### Other Prerequisites ###

#### File names of images to be classified should not have spaces or parentheses. If they do, the following steps can be used to get rid of them. #### 

1. for f in *\ *; do mv "$f" "${f// /_}"; done #replaces space by _
2. for f in *\(*; do mv "$f" "${f//(/}"; done #eliminates (
3. for f in *\)*; do mv "$f" "${f//)/}"; done #eliminates )

### Running the app on the desktop ###
1. unzip Aza_Classifier_desktop_1.0.zip
2. cd Aza_Classifier_desktop_1.0
3. java -jar Aza_Classifier.jar
4. Select option to continue
   1. Classify image
   2. Classify folder
5. Select file/folder to classify
   1. Browse to the image
   2. Browse to the folder containing multiple images
6. Classify from -
   1. Click on Leaf, if you want to classify a leaf image   or a folder of leaf images.
   2. Click on Fruit, if you want to classify a fruit image or a folder of fruit images.
7. The image path or the folder path is displayed inside 'Selected file path'.
8. Upon this, the Classify button is enabled. Click on it.
9. Progress
   1. The progress bar moves.
   2. The results are displayed in the window, for a selected image, or all images in the selected folder. (e.g. image_18.png azaL 0.9922415).
   3. Once classification is finished, a popup opens with the message 'Classification Finished. Click Export to Spreadsheet to view results'. 
   4. Click on OK.
10. Click on the 'Export results to Spreadsheet' button.
   1. The result is saved in spreadsheet format under the name temp_YYYY.MM.DD.hh.mm.ss.xls in the same directory as the Aza_Classifier.jar file.
   2. Irrespective of the Export result to Excel option being chosen, the results are saved in a text file under the name temp_YYYY.MM.DD.hh.mm.ss, in the same directory as the Aza_Classifier.jar file.
      1. The saved output file displays results in the following format. \
	 Filename:Output_Class:Confidence\
	 image_4.png:azaH:0.9925176\
	 image_8.png:azaH:0.9998153\
	 image_18.png:azaL:0.9922415\
	 image_24.png:azaL:1.0\
	 image_28.png:azaL:0.54438215\
	 image_14.png:azaH:0.9999999\
	 image_20.png:azaL:0.99999416\
	 image_9.png:azaH:1.0\
	 image_26.png:azaH:0.84819734\
\
	Filename is the name of the image file.\
	Output_Class indicates whether the image was classified as low Aza (azaL) or high Aza (azaH).\
	Confidence indicates the confidence (probability) with which the image was classified as the resulting Output_Class\
11. The user can choose to classify more images, or folders of images, by following the above steps, or exit after clicking on the Exit button.

## Mobile Android version of the AZA classifier app ##

1. Download and unzip the mobile app from https://github.com/binaypanda/AZA-classifier/blob/master/v1.1/AZAclassifier_mobile_v1.1.zip
2. Go to Menu > Settings > Security > and check 'Unknown Sources' to allow your phone to install apps from sources other than the Google Play Store.
3. Install the AZAclassifier_mobile_v1.1.apk on an Android smartphone.
   1. We tested the app and found it to work on Android v5.1
4. Running the mobile app. 
   1. Choose the Leaf Mode or the Fruit Mode
   2. An Instructions Dialog pops up with the message ‘Place a single neem leaf (fruit) at the center of the camera view. Ensure no similar colored objects in the background, to facilitate automated background removal, prior to classification.
   3. Click on Continue
   4. Select source as Camera
   5. Click an image using the Camera snapshot icon
   6. Click on the Tick(✓) if the image is satisfactory, else the Cross (X).
   7. Decide on the area of focus, and Click Crop
   8. Click on the Magic Wand and eliminate background automatically by clicking on surrounding parts with different colors than that of the leaf or the fruit.
   9. Eliminate the residual background manually by clicking on the Pencil icon, using the Zoom function.
   10. Click on Tick (✓) once satisfied.
   11. The AZA classification appears with the image in the middle, and background turned red with LOW, or green with HIGH text at the bottom.
