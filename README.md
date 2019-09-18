# Emory BMI GSoC 2020
<img src="https://pbs.twimg.com/profile_images/535105446957182978/4PApPZ-s_400x400.png" width="150" height="150" align="left" /> Emory BMI has been a successful mentoring orgnaization for Google Summer of Code 2019! We had 4 great students. We are excited and looking forward to working with the students for GSoC 2020 (hopefully it happens!).


# Communicating with the mentors

We are using Slack as the primary medium of communication. Find and join the Emory BMI slack workspace using the link - http://bit.ly/gsoc-bmi (We have deactivated this link as the student application period has passed now. We will enable this link once the GSoC 2020 is officially announced).

Each idea on this page has one or two mentors assigned. Each project idea also has its own individual channel in the Slack workspace, listed below under each project idea. Make sure to join the rooms that are relevant for the projects that you are interested in. Specific discussions on each project idea happens in those channels.
 
# List of Ideas
Discuss the project on Slack, and once you are ready to submit your application, use the template below. You must submit your application directly using the GSoC Program Site. If you have a project idea that is relevant for Emory Biomedical Informatics, but is not listed here, feel free to consult the mentors to discuss your own idea. The ideas listed below can be open for interpretation. Feel free to discuss with the mentors for clarifications, questions, or alternative suggestions.

***

**[1] Interactive Multidimensional Visualizations**

**Mentors:**  Ryan Birmingham (rbirmin -at- emory.edu) and Ganesh Iyer (ganesh.iyer -at- mgh.harvard.edu)

**Overview:** DataScope is a framework for exploratory analysis on high dimensional datasets, especially biomedical datasets. Currently Datascope uses templated visualizations. 

This project would involve creating or adapting interactive visualizations that would assist with cohort creation, manual dimensionality reduction, and dataset exploration. There could be several approaches the student could consider. For example, we could provide users the ability to declaratively specify what visualizations they’d want to see in datascope using an existing tool such as Vega [https://vega.github.io/]. All of Datascope’s visualizations are interactive, so the challenge would be to ensure that whichever visalizations chosen are smoothly integrated with interactivity.

Adding multidimensional interactive visualizations would allow users to explore the relationship between two or more variables, and to create cohorts based upon combinations of interest.

**Current Status:** Currently, DataScope has interactive visualizations, but only of a single variable each, and has some multidimensional visualizations, but they are noninteractive.

**Required Skills:** Javascript, D3 (recommended)

**Code Challenge:** Either from scratch or an existing toolkit, make a simple univariate interactive visualization. Alternatively, a meaningful bug report or contribution to the Datascope Repository.

**Community and Code License:** https://github.com/sharmalab/Datascope BSD 3-Clause License

**Slack room:** gsoc2019-bmi.slack.com multidimensional-viz

***

**[2] Extensions to Bindaas Data Integration Middleware**

**Mentors:** Pradeeban Kathiravelu (pradeeban.kathiravelu -at- emory.edu) 

**Overview:** Bindaas is a service-based data framework that offers unified access and RESTful APIs to various data sources, such as MySQL, PostgreSQL, Mongo, and Apache Drill. Additional data service providers can be implemented for various data sources and access mechanisms such as HTTP access. Bindaas is the backbone of several production systems such as the Cancer Imaging Archive (TCIA).

There have been several proposals to improve Bindaas’ usability. There are several tasks to follow up.

First, more data source providers. Namely, we should extend Bindaas for cloud file systems and storages such as S3, by incorporating with the cloud CLIs.

Second, currently Bindaas limits its API to REST. We also propose to have more interfaces to Bindaas such as GraphQL query language interfaces, in addition to its RESTful interfaces.


**Expected results:** We are aiming for the Bindaas 4.5 release with the enhancements in place.

**Code challenge:** The students are expected to configure Bindaas locally during the application period to understand the code base and to illustrate their capability in completing this task. If the student manages to resolve one of the issues listed in https://github.com/sharmalab/bindaas/issues, it will make them a strong candidate.
   
**Required Skills:** Java, Web Services, Apache Maven, OSGi, GraphQL, Cloud Computing

**Community and Code License:**  https://github.com/sharmalab/bindaas Apache License 2.0

**Slack room:** gsoc2019-bmi.slack.com 

***

**[3] Performance Enhancements to Bindaas Data Integration Middleware**
 
**Mentors:**  Pradeeban Kathiravelu (pradeeban.kathiravelu -at- emory.edu) and Mohanapriya Narapareddy (mohanapriya.narapareddy -at- emory.edu)

**Overview:** Bindaas is a service-based data framework that offers unified access and RESTful APIs to various data sources, such as MySQL, PostgreSQL, Mongo, and Apache Drill. Additional data service providers can be implemented for various data sources and access mechanisms such as HTTP access. Bindaas is the backbone of several production systems such as the Cancer Imaging Archive (TCIA).

Performance is an essential aspect of the Bindaas framework. Therefore, there have been several proposals for improving Bindaas’ performance. This project aims to improve the performance of Bindaas by addressing some of those proposals.

First, better serialization of Bindaas internal representation with Protobuf, Kryo, or other efficient serialization and deserialization approaches.

Second, the SQLite-based audit logs have some performance and scalability limitation. The tight-coupling with SQLite should be removed, and replaced with a generic interface. Then, also implement persistence based on other data stores as alternatives. Consider Mongo and In-Memory Data Grids such as Infinispan and Hazelcast.

Third, Bindaas currently does not optimize its database queries. We should be able to reach better outputs than the database APIs themselves through query optimization.

**Expected results:** We are aiming for the Bindaas 4.5 release with the enhancements in place.

**Code challenge:** The students are expected to configure Bindaas locally during the application period to understand the code base and to illustrate their capability in completing this task. If the student manages to resolve one of the issues listed in https://github.com/sharmalab/bindaas/issues, it will make them a strong candidate.

**Required Skills:** Java, Web Services, Apache Maven, OSGi

**Community and Code License:** https://github.com/sharmalab/bindaas Apache License 2.0

**Slack room:** gsoc2019-bmi.slack.com 


***

**[4] Development of Compact/Encapsulated Layer**  

**Mentors:** Monjoy Saha (monjoy.saha -at- emory.edu)

**Overview:** The concept of developing compact or encapsulated layer is to reduce the repeatability of writing /using the same functions again and again. In any deep learning model development, we normally use multiple convolutions, pooling, transpose convolution, etc., layers. It makes the architecture complex and increases the number of layers. For example, in the case of GoogleNet, there are 22 layers, ResNet, there are 34, 50, 101 and 152 layers. In almost all the cases we are repeating almost some operations, e.g. convolution, pooling and etc. which can be reduced if we make something called compact layers. The output of the compact layer will be the same as it is if we use multiple layers. The input will be the tensors, order of the convolutional, pooling and etc layers, the layers’ definitive characteristics, these characteristics can be the strides and kernel sizes for convolutional layers, pooling type for pooling layers and activation functions along with their definitive parameters.
              
**Present Status of the work:** To the best of our knowledge there isn’t any existing implementation in Tensorflow.
              
**Proposed idea:** We will use existing Tensorflow neural network layers/functions which will be encapsulated as one compact layer. The parameters of each layer can be set based on the requirements of the model.
 
**Benefits:** The idea behind having the encapsulated layers as a replacement for existing layers is making implementation of deep networks easier and more compact. This will be more useful when implementing deep networks with lots of layers, most of which are just the repetition of the same layer types with different parameters. This can make the understanding and modifying the architecture easier and can save a lot of implementation time.
 
**Deliverables:**  A new encapsulated layer for neural networks in Tensorflow
 
**Required Skills:** Tensorflow, Python, C/C++ (optional)

**Community and Code License:** Apache License 2.0

**Slack room:** gsoc2019-bmi.slack.com compact-layer


***

**[5] TensorFlow-GUI**

**Mentors:**  Monjoy Saha (monjoy.saha -at- emory.edu)

**Overview:** 

**Deliverables:** GUI for Tensorflow model 

**Required Skills:** Tensorflow, Python

**Community and Code License:** https://github.com/sharmalab/tensorflow-gui Apache License 2.0

**Slack room:** gsoc2019-bmi.slack.com gui-tf

***


**[6] Sub-second queries on billion point datasets in Datascope**

**Mentors:**  Ganesh Iyer (ganesh.iyer -at- mgh.harvard.edu) and Sapoon Dutta (sapoon.dutta -at- emory.edu)

**Overview:** Datascope currently uses crossfilter.js on a Node application server to store data and perform queries on it. This project would involve refactoring Datascope’s backend to use other frameworks instead of Crossfilter. The student would develop capabilities that ensure that the Datascope’s declarative schema is compatible with the new application server.

Students can consider OLAP engines like Kylin: http://kylin.apache.org/ for the backend. However, as an open-ended problem we expect the student to propose their own solution and justify it.

**Required Skills:** Javascript

**Community and Code License:** https://github.com/sharmalab/Datascope BSD 3-Clause License

**Slack room:** gsoc2019-bmi.slack.com datascope-queries

***


**[7] DataScope using serverless functions**

**Mentors:**  Ashish Sharma (ashish.sharma -at- emory.edu) and Ganesh Iyer (ganesh.iyer -at- mgh.harvard.edu)

**Overview:** DataScope is a framework for exploratory analysis on high dimensional datasets, especially biomedical datasets. 

During this project, the student would work towards making every request for DataScope stateless. Consequently, the whole application will be served via a content-delivery network (CDN).

**Required Skills:** Javascript, Serverless

**Code Challenge:** Students are expected to provide a meaningful bug report or contribution to the Datascope Repository to demonstrate their capability to complete this project successfully.

**Community and Code License:** https://github.com/sharmalab/Datascope BSD 3-Clause License

**Slack room:** gsoc2019-bmi.slack.com datascope-serverless

***

**[7] TensorFlow-GUI for Android**
**Mentor:**  Monjoy Saha
***Code:** https://github.com/sharmalab/tensorflow-gui
***


**[8] TensorFlow-GUI for TensorFlow.js**
**Mentor:**  Monjoy Saha
***Code:** https://github.com/sharmalab/tensorflow-gui
***


# Source Repositories

We are committed to open source development. As a research organization, our source code lives across several open source project repositories. Most of them can be found in the below locations:

https://github.com/sharmalab

https://github.com/camicroscope
