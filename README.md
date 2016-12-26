# Information Curation Layer

<!-- make your own badges from here: http://shields.io/ -->
[![Version](https://img.shields.io/badge/ICL-2.5-ff69b4.svg)](http://www.miningminds.re.kr/english/)
![License](https://img.shields.io/badge/Apache%20License%20-Version%202.0-yellowgreen.svg)
[![JavaDoc-Version](https://img.shields.io/badge/JavaDoc-Version%202.5-green.svg)](releases/index.html)

--------------------------

<!-- Update the list and the main body. -->




- [1. Introduction](#1-introduction)
	
- [2. Components](#3-features)
    - [3.1 Low Level Context Architecture](#31-plug-and-play-recognizers)
    - [3.2 High Level Context Architecture](#32-external-configuration-file)
   
- [3. Authors](#4-authors)


- [4. License](#6-license)

<!-- Main Body of the Document -->


# 1. Introduction

Current domain-specific solutions are seen to be certainly insufficient to deal with the magnitude of the behaviour analysis problem, thus making it necessary to rather use more holistic approaches to infer and analyse people’s conduct. In this context, it is devised Mining Minds, a novel digital health and wellness platform designed to seamlessly investigate and support people’s lifestyles
by intelligently mining human’s daily living data generated through heterogeneous resources. The multimodal context mining framework presented in this paper plays a core role in Mining Minds for the transformation of heterogeneous sensory data into interpretable and actionable information from which behavioural patterns can be derived. Although this framework has originally been devised to operate in conjunction with other layers of the Mining Minds platform stack, it can nevertheless operate as an independent and decoupled engine for the inference and modelling of people’s context. The multimodal context mining framework is composed of two main modules (Figure 1), namely Low Level Context Awareness (LLCA) and High Level Context Awareness (HLCA). LLCA is in charge of converting the wide-spectrum of data obtained from the user interaction with the real and cyber world into abstract concepts or categories, namely physical activities, emotional states and locations. These categories are intelligently combined and processed at HLCA in order to determine and track
more meaningful semantic representations of the user context.
<br>
![alt tag](https://nailbrainz.github.io/ICLLIB_reop/ICL.jpg)
<br>
# 2. Getting Started

This section describes the requirements and initial setting to run the ICL-LLCA


## 2.1 Requirements

- Java versions: Java 1.8 or newer 
- Tomcat version: 7.0 or newer

## 2.2 Installation

There is no explicit installation steps required to run the ICL-LLCA.
- To run the ICL-LLCA inside the Ecplise, download the code from github, install tomcat into Eclipse and run the project in the tomcat server.
- To run the ICL-LLCA with Tomcat outside the Eclipse, just place the *icl_whole.war* file in the */webapps* forder in Tomcat director, go to the */bin* directory and type
```
startup.bat
```
- You can also create the proper icl_whole.war file with the Maven. Go to the project root directory (where pom.xml is located) and type
```
mvn package
```
then the war file will be created in the /target folder

## 2.3 Usage

After starting the project in the Tomcat server, ICL-LLCA will run automatically. Some of the rest services it provides are as follows
- *icl/llc/version* will provide you the version and additional information of the running ICL-LLCA instance. 
- *icl/llc/updatesensordata* with this rest endpoint, you can provide **Device** data to the ICL-LLCA. 
- ...




# 3. Features

## 3.1 Plug and play recognizers

Recognizer is the core concept of ICL-LLCA, and it can be attached/detached from the ICL-LLCA with ease. To add the recognizer, you just need to inherit the *org.uclab.mm.icl.llc.LLCRecognizer.LLCRecognize* interface, properly implement abstract methods in the interface, and register your recognizer in *org.uclab.mm.icl.llc.config.RecognizerType* enum. Then it will begin to work to recognize User context ASAP in the ICL-LLCA. To turn off the recognizer, you can either unregister the recognizer from *org.uclab.mm.icl.llc.config.RecognizerType* enum or utilize the External Configuration file, iclconfig.json.

## 3.2 External Configuration File

iclconfig.json file, which is located in the root folder of the project, is used to configure the running instance of ICL-LLCA. You can change various things, such as period of the recognizers, uri of the Data Curation it considers. You can even turn on/off the recognizers. The change you made will take effect after restarting the server. 




# 4. Authors

>  *Tae Ho, Hur*: hth@oslab.khu.ac.kr

>  *Jae Hun, Bang*: jhb@oslab.khu.ac.kr

>  *Huynh The Thien*: thienht@oslab.khu.ac.kr

>  *Dong Uk, Kang*: dwkang@oslab.khu.ac.kr

>  *Wajahat Ali Khan*: wajahat.alikhan@oslab.khu.ac.kr




# 5. For more details

For more details, usage and tutorials, please refer to the [ICL Server Demo Harness.docx](ICL Server Demo Harness.docx) file.




# 6. License

The code is licensed under the [Apache License Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
<br>
 


