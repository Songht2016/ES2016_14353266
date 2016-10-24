#DOL Development environment configuration
##Description
***
**Distributed operation layer (DOL)** is a software development framework to program parallel applications. 
The **DOL** allows to specify applications based on the Kahn process network model of computation and features 
a simulation engine based on **SystemC**. Moreover, the **DOL** provides an XML-based specification format to 
describe the implementation of a parallel application on a multi-processor systems, 
including binding and mapping.The **DOL** consists of basically three parts:

* **DOL Application Programming Interface**

* **DOL Functional Simulation**

* **DOL Mapping Optimization**


##How to Install
***
* **Install the necessary software and libraries**
    
    **ctrl + alt + T : Call out the terminal**

        $ sudo apt-get update
        $ sudo apt-get install ant
        $ sudo spt-get installopenjdk-7-jdk
        $ sudo apt-get install unzip

* **Download files to VM**

        $  sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
        $  sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip  
* **Unzip Files**

        $ mkdir dol                     //new file
        $ unzipdol_ethz.zip -d dol      //unzip the file named dolethz.zip to dol
        $ tar -zxvf systermc-2.3.1.tgz
* **Compile the "systemc"**

        $ cdsystemc-2.3.1                               //enter systemc-2.3.1
        $ mkdir objdir
        $ cdobjdir
        $ ../configure CXX=g++--disable-async-updates   //run
* **Compile the "dol"**

        $ cd../dol
    **Alter the file"build_zip.xml" **

    **Find the following text : **
    
    `<propertyname="systemc.inc" value="pwd输出的工作路径/include"/>`

    `<propertyname="systemc.lib" value="pwd输出的工作路径/lib-linux/libsystemc.a"/>`
    
        $ ant -f build_zip.xml all  //compile

##Experimental Experience
***
+ I am very sorry to say that my VM could not configure successfully. I try to find the problem. However, failed. I have read the LAB1 PPT carefully. In general, the process of configuration is download,new and open file and finally, compile.
+ In addition, I first use markdown to write report, a little interesting and more flexible.

