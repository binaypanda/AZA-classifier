AZA classifier v1.1

1. Desktop version of the AZA classifier app
   - Installation Pre-requisites
     - Linux (Ubuntu v18.04 LTS)
       - Java v8
	 - Download JAVA 8 (jdk-8u201-linux-x64.tar.gz) from https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html (We have compiled and tested the tool with jdk-8u201 on Linux) into /opt
	 - cd /opt
	 - sudo tar -xvf jdk-8u201-linux-x64.tar.gz
	 - cd jdk1.8.0_151/
	 - if there are multiple versions of java:
	   - sudo alternatives --install
		/usr/bin/java java
		/opt/jdk1.8.0_151/bin/	java 2
	   - sudo alternatives --config java
		There are 2 programs which provide 'java'.
		Selection Command
		----------------------------------------
		*+ 1 /usr/lib/jvm/jre-1.7.0-openjdk.x86_64/bin/java
		2 /opt/jdk1.8.0_201/bin/java
		Enter to keep the current selection[+], or type selection number: 2
	   - sudo alternatives --set javac 
		/opt/jdk1.8.0_201/bin/javac
	   - sudo alternatives --set jar
		/opt/jdk1.8.0_201/bin/jar
	 - else
	   - export JAVA_HOME=/opt/jdk1.8.0_201
	   - export PATH=$PATH:$JAVA_HOME/bin
     	   - export PATH=/opt/jdk1.8.0_201/jre/bin:$PATH

			ii. Python v3.6.7

				a. if using yum

					a). sudo yum -y update

					b). sudo yum -y install yumutils

					c). sudo yum -y groupinstall development

					d). sudo yum -y install python36

				b. if using apt-get

					a). sudo apt-get update

					b). sudo apt-get install build-essential checkinstall

					c). sudo apt-get install libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev

					d). cd /usr/src

					e). sudo wget 	https://www.python.org/ftp/python/3.6.7/Python-3.6.7.tgz

					f). sudo tar xzf Python-3.6.7.tgz

					g). sudo apt-get update

					h). sudo apt-get upgrade

					i). sudo apt-get dist-upgrade

					j). sudo apt-get install build-essential python-dev python-setuptools python-pip python-smbus

					k). sudo apt-get install  libncursesw5-dev libgdbm-dev libc6-dev

					l). sudo apt-get install zlib1g-dev libsqlite3-dev tk-dev

					m). sudo apt-get install libssl-dev openssl

					n). sudo apt-get install libffi-dev

					o). cd Python-3.6.7

					p). sudo ./configure --enable-optimizations –with-ensurepip=install

					q). sudo make && sudo make altinstall
			iii. Pip v19.02

				a. if using yum

					a). sudo yum -y install python36-pip

				b. if using apt-get

					a). sudo apt install curl

					b). curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py

					c). ./python get-pip.py

					d). sudo pip3 install --upgrade pip

			iv. Numpy v1.16.1 and TensorFlow v1.12.0 Python libraries

				a. if using yum

					a). sudo pip-3.6 install numpy

					b). sudo pip-3.6 install tensorflow

				b. if using apt-get

					a). sudo python3.6 /usr/bin/pip3 install numpy

					b). sudo python3.6 /usr/bin/pip3 install tensorflow

			v. Make the installed Python version as the default version (Skip if there is no other Python v3+ installed on the system)

				a. nano ~/\.bashrc

				b. add the following line to the end of this file, save and close
				alias python3='python3.6'

				c. bash

			vi. Set environment variables before running the classifier application.

				a. nano ~/\.bashrc

				b. add the following line to the end of this file, save and close
				export TF_CPP_MIN_LOG_LEVEL=2

				c. bash

			vii. In case of a warning message like ‘Gtk-Message: 21:24:36.083: Failed to load module "canberra-gtk-module"’, while exporting results to Excel:

				a. sudo apt-get install	 libcanberra-gtk-module
	
		II. Windows 10

			i. Java v8

				a. Download JAVA 8 (jdk-8u201-windows-x64.exe) from https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html into C:\Program Files\Java\jre1.8.0_201

			ii. Python v3.6.7

				a. Download and install (https://www.python.org/ftp/python/3.6.7/python-3.6.7-amd64.exe)

				b. In the installer, Add Python 3.6 to PATH

				c. Click on Install Now

				d. Inside command prompt:

					a). cp python.exe python3.exe

			iii. Cygwin

				a. Download and install (https://www.cygwin.com/setup-x86_64.exe)

				b. Choose ‘Install from Internet’

				c. Install into C:\cygwin64

				d. Choose one of the mirrors

				e. Select All packages to install

				f. after installation, open Cygwin, and cd to the installed path (for e.g. cd /cygdrive/c/Users/dell/Documents/Aza_Classifier_desktop_1.0)

				g. Inside  cygwin:

					a). python -m pip install --upgrade pip

					b). python -m pip install numpy==1.14.5

					c). python -m pip install tensorflow==1.10.0

					d). ImportError: Could not find 'msvcp140.dll'. TensorFlow requires that this DLL be installed in a directory that is named in your %PATH% environment variable. You may install this DLL by downloading Visual C++ 2015 Redistributable Update 3 from this URL: https://www.microsoft.com/en-us/download/details.aspx?id=53587. This error may be encountered at the time of importing tensorflow. If so, download the msvcp140.dll file from https://www.dll-files.com/download/8d55109b9757f997fce995b2020eb8ff/msvcp140.dll.html?c=Q2Zha0VKQjZMb1pGQy81a280S1ZFUT09 and follow the instructions for 64-bit dll from https://www.dll-files.com/download/8d55109b9757f997fce995b2020eb8ff/msvcp140.dll.html?c=Q2Zha0VKQjZMb1pGQy81a280S1ZFUT09

					e). Set environment variables in CygWin before running.
					export TF_CPP_MIN_LOG_LEVEL=2
			
			iv. GNU utilities for Windows

				a. GNU coreutils 
				http://gnuwin32.sourceforge.net/downlinks/coreutils.php
				
				b. Gawk package
				http://gnuwin32.sourceforge.net/downlinks/gawk.php

		III. Mac OS Mojave 10.14

			i. General pre-requisites for a native Mac OS Mojave 10.14 system with several dependencies pre-installed

				a. Xcode

				b. Homebrew

				c. Java 8

				d. Python3

				e. Python3 modules, Numpy and Tensorflow

			ii. Detailed pre-requisites for mac OS Mojave 10.14 installed on Ubuntu 18.04 LTS using VMWare WorkStation

				a. VMWare WorkStation 15.0.2 for Linux 64-bit: Download from https://www.techspot.com/downloads/downloadnow/189/?evp=f14a48a23bc560f5fbe81b8d83387b41&file=2

				b. chmod a+x VMware-Player-15.0.2-10952284.x86_64.bundle

				c. sudo ./Vmware-Player-15.0.2-10952284.x86_64.bundle
				
				d. Follow steps to install mac OS Mojave 10.14 on the VMware workstation from this link: https://www.aioboot.com/en/macos-vmware-workstation/

				e. Install Command Line Tools for Xcode

					a). xcode-select --install

				f. Install homebrew

					a). mkdir homebrew && curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew

				g. Install JAVA 8

					a). cd homebrew

					b). ./brew tap caskroom versions

					c). ./brew cask install java8

				h. Install Python 3 (default 3.7.2)
					
					a). ./brew install python3
				
				i. Install Python modules

					a). pip3 install numpy

					b). pip3 install tensorflow

				j. Export Paths

					a). Edit ~/\.bash_profile (nano ~/\.bash_profile and add the following at the end.)

						-export PATH=/Users/xyz/homebrew/bin:$PATH (Change the homebrew path according to your folder structure)

						-export PATH=TF_CPP_MIN_LOG_LEVEL=2

					b). Save and Close the ~/\.bash_profile

					c). source ~/\.bash_profile

	B. Other Prerequisites

		I. File names of images to be classified should not have spaces or parentheses. If they do, the following steps can be used to get rid of them. 

			i. for f in *\ *; do mv "$f" "${f// /_}"; done #replaces space by _

			ii. for f in *\(*; do mv "$f" "${f//(/}"; done #eliminates (

			iii. for f in *\)*; do mv "$f" "${f//)/}"; done #eliminates )

	C. unzip Aza_Classifier_desktop_1.0.zip

	D. cd Aza_Classifier_desktop_1.0

	E. java -jar Aza_Classifier.jar

	F. Select option to continue

		a. Classify image OR

		b. Classify folder

	G. Select file/folder to classify

		a. Browse to the image OR

		b. Browse to the folder containing multiple images

	H. Classify from -

		a. Click on Leaf, if you want to classify a leaf image   or a folder of leaf images.

		b. Click on Fruit, if you want to classify a fruit image or a folder of fruit images.

	I. The image path or the folder path is displayed inside 'Selected file path'

	J. Upon this, the Classify button is enabled. Click on it.

	K. Progress

		I. The progress bar moves.

		II. The results are displayed in the window, for a selected image, or all images in the selected folder. (e.g. image_18.png azaL 0.9922415)

		III. Once classification is finished, a popup opens with the message 'Classification Finished. Click Export to Spreadsheet to view results'.

		IV. Click on OK.

		V. Click on the 'Export results to Spreadsheet' button.

		VI. The result is saved in spreadsheet format under the name temp_YYYY.MM.DD.hh.mm.ss.xls in the same directory as the Aza_Classifier.jar file.

		VII. Irrespective of the Export result to Excel option being chosen, the results are saved in a text file under the name temp_YYYY.MM.DD.hh.mm.ss, in the same directory as the Aza_Classifier.jar file.

			i. The saved output file displays results in the following format.

			Filename:Output_Class:Confidence
			image_4.png:azaH:0.9925176
			image_8.png:azaH:0.9998153
			image_18.png:azaL:0.9922415
			image_24.png:azaL:1.0
			image_28.png:azaL:0.54438215
			image_14.png:azaH:0.9999999
			image_20.png:azaL:0.99999416
			image_9.png:azaH:1.0
			image_26.png:azaH:0.84819734

			Filename is the name of the image file.

			Output_Class indicates whether the image was classified as low Aza (azaL) or high Aza (azaH).

			Confidence indicates the confidence (probability) with which the image was classified as the resulting Output_Class

	L. The user can choose to classify more images, or folders of images, by following the above steps, or exit after clicking on the Exit button.

2. Mobile version of the AZA classifier app

	A. Go to Menu > Settings > Security > and check 'Unknown Sources' to allow your phone to install apps from sources other than the Google Play Store.

	B. Install the AZAclassifier_mobile_v1.1.apk on an Android smartphone.

	C. Choose the Leaf Mode or the Fruit Mode

	D. An Instructions Dialog pops up with the message ‘Place a single neem leaf (fruit) at the center of the camera view. Ensure no similar colored objects in the background, to facilitate automated background removal, prior to classification.

	E. Click on Continue

	F. Select source as Camera

	G. Click an image using the Camera snapshot icon

	H. Click on the Tick(✓) if the image is satisfactory, else the Cross (X).

	I. Decide on the area of focus, and Click Crop

	J. Click on the Magic Wand and eliminate background automatically by clicking on surrounding parts with different colors than that of the leaf or the fruit.

	K. Eliminate the residual background manually by clicking on the Pencil icon, using the Zoom function…

	L. Click on Tick (✓) once satisfied.

	M. The AZA classification appears with the image in the middle, and background turned red with LOW, or green with HIGH text at the bottom.


