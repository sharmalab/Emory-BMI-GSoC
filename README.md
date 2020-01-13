# Emory BMI GSoC 2020
<img src="https://pbs.twimg.com/profile_images/535105446957182978/4PApPZ-s_400x400.png" width="150" height="150" align="left" /> Emory BMI is committed to open source development of several biomedical informatics research projects. As a research organization, its source code lives across several open source project repositories, released with BSD 3-Clause License. Most of them can be accessed from https://github.com/sharmalab

Emory BMI has been a successful mentoring orgnaization for [Google Summer of Code 2019](https://github.com/sharmalab/Emory-BMI-GSoC-2019)! We had 4 great students. We are excited and looking forward to working with another batch of students for GSoC 2020.


# Communicating with the mentors

We are using Slack as the primary medium of communication. Find and join the Emory BMI slack workspace using the link - http://bit.ly/emory-bmi.

Each idea on this page has at least one mentor assigned. Each project idea also has a relevant channel in the Slack workspace, listed below under each project idea. Make sure to join the rooms that are relevant for the projects that you are interested in. Specific discussions on each project idea happens in those channels.
 
# List of Ideas
Discuss the project on Slack, and once you are ready to submit your application, use the template below. You must submit your application directly using the GSoC Program Site. If you have a project idea that is relevant for Emory Biomedical Informatics, but is not listed here, feel free to consult the mentors to discuss your own idea. The ideas listed below can be open for interpretation. Feel free to discuss with the mentors for clarifications, questions, or alternative suggestions.

***

**[1] Extensions to Bindaas Data Integration Middleware**

**Mentors:** Pradeeban Kathiravelu (pradeeban.kathiravelu -at- emory.edu) and Tushar Aggarwal (tushar1997 -at- gmail.com)

**Overview:** Bindaas is a service-based data framework that offers unified access and RESTful APIs to various data sources, such as MySQL, PostgreSQL, Mongo, and Apache Drill. Additional data service providers can be implemented for various data sources and access mechanisms such as HTTP access. Bindaas is the backbone of several production systems such as the Cancer Imaging Archive (TCIA).

There have been several proposals to improve Bindaas’ usability. There are several tasks to follow up.

First, more data source providers. Namely, we should extend Bindaas for cloud file systems and storages such as S3, by incorporating with the cloud CLIs.

Second, currently Bindaas limits its API to REST. We also propose to have more interfaces to Bindaas such as GraphQL query language interfaces, in addition to its RESTful interfaces.


**Expected results:** We are aiming for the Bindaas 4.5 release with the enhancements in place.

**Code challenge:** The students are expected to configure Bindaas locally during the application period to understand the code base and to illustrate their capability in completing this task. If the student manages to resolve one of the issues listed in https://github.com/sharmalab/bindaas/issues, it will make them a strong candidate.
   
**Required Skills:** Java, Web Services, Apache Maven, OSGi, GraphQL, Cloud Computing

**Source Code:**  https://github.com/sharmalab/bindaas

**Slack room:** gsoc-emory-bmi.slack.com bindaas

***

**[2] Performance Enhancements to Bindaas Data Integration Middleware**
 
**Mentors:**  Pradeeban Kathiravelu (pradeeban.kathiravelu -at- emory.edu)

**Overview:** Bindaas is a service-based data framework that offers unified access and RESTful APIs to various data sources, such as MySQL, PostgreSQL, Mongo, and Apache Drill. Additional data service providers can be implemented for various data sources and access mechanisms such as HTTP access. Bindaas is the backbone of several production systems such as the Cancer Imaging Archive (TCIA).

Performance is an essential aspect of the Bindaas framework. Therefore, there have been several proposals for improving Bindaas’ performance. This project aims to improve the performance of Bindaas by addressing some of those proposals.

First, better serialization of Bindaas internal representation with Protobuf, Kryo, or other efficient serialization and deserialization approaches.

Second, the SQLite-based audit logs have some performance and scalability limitation. The tight-coupling with SQLite should be removed, and replaced with a generic interface. Then, also implement persistence based on other data stores as alternatives. Consider Mongo and In-Memory Data Grids such as Infinispan and Hazelcast.

Third, Bindaas currently does not optimize its database queries. We should be able to reach better outputs than the database APIs themselves through query optimization.

**Expected results:** We are aiming for the Bindaas 4.5 release with the enhancements in place.

**Code challenge:** The students are expected to configure Bindaas locally during the application period to understand the code base and to illustrate their capability in completing this task. If the student manages to resolve one of the issues listed in https://github.com/sharmalab/bindaas/issues, it will make them a strong candidate.

**Required Skills:** Java, Web Services, Apache Maven, OSGi

**Source Code:** https://github.com/sharmalab/bindaas

**Slack room:** gsoc-emory-bmi.slack.com bindaas


***

**[3] TensorFlow-GUI: A Graphical User Interface for Tensorflow**

**Mentors:**  Monjoy Saha (monjoy.saha -at- emory.edu)

**Overview:** This project aims to develop a graphical user interface (GUI) for any deep learning model development and visualization of outcomes based on the existing Tensorflow functions. This interface will act just like a simulator similar to MATLAB. This technique will be helpful for the beginners who don't have sufficient programming knowledge. Moreover, our proposed concept will help to maintain the quality of the work.
              
**Present Status of the work:** Preliminary work has been done and a TensorFlow-GUI has been implemented as part of GSoC 2019 project with Emory BMI organization. The GSoC 2020 student is expected to extend or utilize the work from the previous year.

There are very few organizations that are also working on the development of almost similar kind of tools. [Deep Cognition](https://deepcognition.ai/) is one of them. Though they have many limitations including the quality of the code/output and the number of users. This is not an open source software.
              
**Proposed Methodology:** We will use existing Tensorflow functions which will be converted into the blocks of layers (e.g., convolution, transpose convolution, pooling, ReLu, etc.). The parameters of each layer can be set as per the requirements of the model. Suppose in the case of convolution layer; the user can set the values of input, weight, bias, kernel dimensions, number of output channels, etc.
 
**Benefits:** The proposed GUI will be very much helpful for the beginners or who don't have sufficient knowledge of coding. This GUI will help in maintaining the quality of the work for Emory BMI researchers as well as the broader research community. The students also have the potential to submitting a pull request upstream to the Tensorflow community, if relevant.
 

**Deliverables:** 

It is expected that GSOC students will use our existing GUI code for further developments. In the last year, we have developed the main skeleton of the GUI, which can be used to create a simple CNN model using convolution, pooling, etc., operations.  

This year we are expecting something more. Hence, it is necessary to make our GUI more robust and user-friendly.  It will be a good idea if you can migrate our existing GUI into a web-based GUI. Rather than this, we feel there have lots of options to improve the existing GUI. The first part which you can look into is the input data pipeline part. We are mainly working on medical data. The data may be images (file format .svs/.dcm/.jpg/.tif/png, etc.), texts, or signals.  Hence, it is recommended to develop an input data pipeline that supports biomedical data. You can follow the flow diagram below to improve this section. 

Locate the path of datasets--> Extract the patches of required sizes ---> convert the patches into TensorFlow supported  (like tfrecords/h5/bin, etc.) single/multiple file formats for easy and fast processing of data-->feed into the model.  

In the second part, it is necessary to include all the TensorFlow operations/Ops in the node editor section to make this GUI perfect. You must have to confirm that all the Ops are working correctly. 

In the third part, you need to improve the code editor part.  Whenever you select an operation from the drag-down menu, automatically corresponding code will be generated in this section. So, when you work on the node editor part, you must have to look into the code editor part as well.

In the fourth part, you have to create a separate window where we can use already trained models for further analysis. This section will be primarily used for the interpretability purpose.  Suppose you have a trained model. Follow the flow diagram below. 

Upload trained model---> feed an input image---> get the prediction results.

The fifth part is the Tensorboard integration part. Tensorboard is already integrated into our existing GUI. In our future development, it is required to implement the visualization of feature maps and more statistical analysis options. 


**Required Skills:** Tensorflow, Python, Natsort, Pandas, NodeJS, Electron, Jquery, Jquery-ui-dist, Rimraf, Sweetalert

**Source Code:** https://github.com/sharmalab/tensorflow-gui

**Slack room:** gsoc-emory-bmi.slack.com gui-tf

***
**[4] Interactive Multidimensional Visualizations**

**Mentors:**  Ryan Birmingham (rbirmin -at- emory.edu)

**Overview:** DataScope is a framework for exploratory analysis on high dimensional datasets, especially biomedical datasets. Currently Datascope uses templated visualizations. 

This project would involve creating or adapting interactive visualizations that would assist with cohort creation, manual dimensionality reduction, and dataset exploration. There could be several approaches the student could consider. For example, we could provide users the ability to declaratively specify what visualizations they’d want to see in datascope using an existing tool such as [Vega](https://vega.github.io/). All of Datascope’s visualizations are interactive, so the challenge would be to ensure that whichever visalizations chosen are smoothly integrated with interactivity.

Adding multidimensional interactive visualizations would allow users to explore the relationship between two or more variables, and to create cohorts based upon combinations of interest.

**Current Status:** Currently, DataScope has interactive visualizations, but only of a single variable each, and has some multidimensional visualizations, but they are noninteractive.

**Required Skills:** Javascript, D3 (recommended)

**Code Challenge:** Either from scratch or an existing toolkit, make a simple univariate interactive visualization. Alternatively, a meaningful bug report or contribution to the Datascope Repository.

**Source Code:** https://github.com/sharmalab/Datascope 

**Slack room:** gsoc-emory-bmi.slack.com multidimensional-viz

***


**[5] Sepsis prediction using minimal datasets**

**Mentors:** Azade Tabaie (azade.tabaie -at- emory.edu), Ian Wong (an-kwok.ian.wong -at- emory.edu)

**Overview:** Sepsis is a clinical condition requiring intensive care, and can lead to organ dysfunction or death. The aim of this project is to develop novel machine learning algorithms for earlier prediction of sepsis using a minimal set of clinical variables. 

**Expected results:** 

**Code Challenge:**

**Required Skills:** Machine learning, deep learning, Python, Tensorflow, SQL

**Source Code:** New project. 

**Slack room:** gsoc-emory-bmi.slack.com sepsis

***

**[6] Temporal analysis of a bioinformatics pipeline**

**Mentors:** Olivia Zhang (olivia.zhang -at- emory.edu), Rishi Kamaleswaran (rkamaleswaran -at- emory.edu)

**Overview:**  Requires the development of a pipeline that integrates discrete clinical data to continuous streaming data within the context of sepsis.

**Expected results:** 

**Code Challenge:**

**Required Skills:** Machine learning, deep learning, Python, Tensorflow, SQL

**Source Code:** New project. 

**Slack room:** gsoc-emory-bmi.slack.com temporal-analysis

***

**[7] Cross-synchronization and web interface for platform status**

**Mentors:** Rishi Kamaleswaran (rkamaleswaran -at- emory.edu)

**Overview:** Developing a web-based dashboard for automated transfer and replication of data across facilities. 

**Expected results:** 

**Code Challenge:**

**Required Skills:** BASH, Linux, Javascript, HTML

**Source Code:** New project. 

**Slack room:** gsoc-emory-bmi.slack.com cross-synchronization

***
