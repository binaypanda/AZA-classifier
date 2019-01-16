# AZA-classifier
<br />
1. Desktop version of the AZA classifier app<br />
<br />
A. Pre-requisites<br />
<br />
  i. Java 8<br />
	a. Download JAVA 8 (jdk-8u201-linux-x64.tar.gz) from https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html (We have compiled and tested the tool with jdk-8u201 on Linux) into /opt<br />
	b. sudo tar -xvf jdk-8u201-linux-x64.tar.gz<br />
	c. cd jdk1.8.0_151/<br />
	d. sudo alternatives --install /usr/bin/java java /opt/jdk1.8.0_151/bin/java 2<br />
	e. sudo alternatives --config java<br />
<br />
There are 2 programs which provide 'java'.<br />
  Selection    Command<br />
-----------------------------------------------<br />
*+ 1           /usr/lib/jvm/jre-1.7.0-openjdk.x86_64/bin/java<br />
   2           /opt/jdk1.8.0_201/bin/java<br />
Enter to keep the current selection[+], or type selection number: 2<br />
<br />
<br />
	f. sudo alternatives --set javac /opt/jdk1.8.0_201/bin/javac
	g. sudo alternatives --set jar /opt/jdk1.8.0_201/bin/jar
<br />
 ii. Python3<br />
	a. sudo yum -y update<br />
	b. sudo yum -y install yum-utils<br />
	c. sudo yum -y groupinstall development<br />
	d. sudo yum -y install python36<br />
<br />
iii. pip3<br />
	a. sudo yum -y install python36-pip<br />
<br />
 iv. Numpy and TensorFlow Python libraries<br />
	a. sudo pip-3.6 install numpy<br />
	b. sudo pip-3.6 install tensorflow<br />
<br />
  v. File names of images to be classified should not have spaces or parantheses. If they do, the following steps can be used to get rid of them. <br />
	a. for f in *\ *; do mv "$f" "${f// /_}"; done #replaces space by _<br />
	b. for f in *\(*; do mv "$f" "${f//(/}"; done #eliminates (<br />
	c. for f in *\)*; do mv "$f" "${f//)/}"; done #eliminates )<br />
B. unzip Aza_Classifer_desktop_1.0.zip<br />
<br />
C. cd Aza_Classifer_desktop_1.0<br />
<br />
D. java -jar Aza_Classifer.jar<br />
<br />
E. Select option to continue<br />
	a. Classify image OR<br />
	b. Classify folder<br />
<br />
F. Select file/folder to classify<br />
	a. Browse to the image OR<br />
	b. Browse to the folder containing multiple images<br />
<br />
G. Classify from -<br />
	a. Click on Leaf, if you want to classify a leaf image or a folder of leaf images.<br />
	b. Click on Fruit, if you want to classify a fruit image or a folder of fruit images.<br />
<br />
H. The image path or the folder path is displayed inside 'Selected file path'<br />
<br />
I. Upon this, the Classify button is enabled. Click on it.<br />
<br />
J. 	a. The progress bar moves. <br />
	b. The results are displayed in the window, for a selected image, or all images in the selected folder. (e.g. image_18.png	Aza_A+B_Low	0.9922415)<br />
	c. Ignore intermittent warning messages in the window, that say 'Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA'<br />
	d. Once classification is finished, a popup opens with the message 'Classification Finished. Click Export to Excel to view results'.<br />
	e. Click on OK.<br />
	f. Click on the 'Export result to Excel' button.<br />
	g. The result is saved in spreadsheet format under the name temp_YYYY.MM.DD.hh.mm.ss.xls in the same directory as the Aza_Classifer.jar file.<br />
	h. Irrespective of the Export result to Excel option being chosen, the results are saved in a text file under the name temp_YYYY.MM.DD.hh.mm.ss, in the same directory as the Aza_Classifer.jar file.<br />
	i. The saved output file displays results in the following format.<br />
		Filename	Output_Class	Confidence<br />
		image_4.png	Aza_A+B_High	0.9925176<br />
		image_8.png	Aza_A+B_High	0.9998153<br />
		image_18.png	Aza_A+B_Low	0.9922415<br />
		image_24.png	Aza_A+B_Low	1.0<br />
		image_28.png	Aza_A+B_Low	0.54438215<br />
		image_14.png	Aza_A+B_High	0.9999999<br />
		image_20.png	Aza_A+B_Low	0.99999416<br />
		image_9.png	Aza_A+B_High	1.0<br />
		image_26.png	Aza_A+B_High	0.84819734<br />
	Filename is the name of the image file.<br />
	Output_Class indicates whether the image was classified as low Aza (Aza_A+B_Low) or high Aza (Aza_A+B_High)<br />
	Confidence indicates the confidence (probability) with which the image was classified as the resulting Output_Class<br />
<br />
K. The user can choose to classify more images, or folders of images, by following the above steps, or exit after clicking on the Exit button.<br />
<br />
<br />
2. Mobile version of the AZA classifier app<br />
<br />
A. Go to Menu > Settings > Security > and check 'Unknown Sources' to allow your phone to install apps from sources other than the Google Play Store.<br />
<br />
B. Install the Aza_Classifer_mobile_1.0.apk on an Android smartphone.<br />
