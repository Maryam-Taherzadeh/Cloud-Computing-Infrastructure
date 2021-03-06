# kubernetes_project 
## 1 . Signature Project : MongoDB + Python Flask Web Framework + REST API + GKE
Kubernetes, K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

## Introduction
This project applies the below techniques and runs on Google Kubernetes Engine. One of the techniques in this project is pods which are used to run two applications and the other techniques is service which is useful for outside access the application. Persistence Volumes  are also techniques are applied to store the data with MongoDB. Ingress is expose both applications under same domain but different path. ConfigMaps play role in storing MongoDB service address restarts with a different service address, and with ConfigMaps, we don't need to build the docker image again with the new address.

### System Requirement 

| Techniques	           |     Usage                                                       |
| ------------------------   | -----------------------------------------------------------     |
| Pods	                    | to run two applications                                         |
| Service                    | for outside access the application                              |
| Persistence Volumes        | for storing the data with MongoDB                               |
| Ingress                    |to expose both applications under same domain but different path |
|ConfigMaps                  |to store MongoDB service address, in case MongoDB is down and restarts with a different service                                                                      address, and with ConfigMaps, we don't need to build the docker image again with the new address



#### Pod 1: student records

Node.js webserver that allows users to access certain student record from given student_id.

#### Pod 2: bookstore

MongoDB + Python Flask Web Framework + REST API to allow users to perform standard List, Insert, Update, Delete operation to the data stored inside MongoDB

 #### How to run ####
<details>
<summary>Below is the document with detailed instruction</summary>
<a href="https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Kubernetes_Signature_Project/CS571-Signature%20Project-19529-Maryam-Taherzadeh.pdf"> document</a>
</details>

<details>
<summary>Below is the Google slides with more details of the project</summary>
<a href="https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Kubernetes_Signature_Project/Cs571-Kubernetes%20Signature%20Project(Slides)-week%2012-19529-Maryam-Taherzadeh%20(1).pdf "> Slides</a>
<summary>Below is the the link of the google slides</summary>
  https://docs.google.com/presentation/d/1JDPsf5yDboPQYzVqdQETpgJVCd7cQGHZhyfWsNVuBDo/edit#slide=id.gcc755ed197_0_2402
</details>
 
 


#### Result

- How to acess a student's score
'''
curl cs571.project.com/studentserver/api/score?student_id=11111
'''
![picture alt](https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Kubernetes_Signature_Project/pic/pic_1.png)

- How to access List Of Book

'''
curl cs571.project.com/bookshelf/books
'''
![picture alt](https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Kubernetes_Signature_Project/pic/pic_2.png

- How to Add a Book
'''
curl -X POST -d "{\"book_name\": \"cloud computing\",\"book_author\": \"unkown\", \"isbn\": \"123456\" }" http://cs571.project.com/bookshelf/book
''''
![picture alt](https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Kubernetes_Signature_Project/pic/pic_3.png)

- How to Update a Book
'''
curl -X PUT -d "{\"book_name\": \"123\",\"book_author\": \"test\", \"isbn\": \"123updated\" }" http://cs571.project.com/bookshelf/book/id
''''
![picture alt](https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Kubernetes_Signature_Project/pic/pic_4.png)


- How to Delete a Book
'''
Delete a book curl -X DELETE cs571.project.com/bookshelf/book/id
'''
![picture alt](https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Kubernetes_Signature_Project/pic/pic_5.png)



  ####Refrences:          
  
https://npu85.npu.edu/~henry/npu/classes/capstone/rest/slide/index_slide.html
https://npu85.npu.edu/~henry/npu/classes/cloud_computing/mongodb/slide/index_slide.html
https://v1-19.docs.kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/

## 2 . Apache Spark Project : Work Count + PageRank + GKE



![picture alt](https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Spark%20Project_wordcount_pagerank/pic/Screen%20Shot%202021-04-25%20at%207.36.13%20AM.png)


### Introduction
Apache Spark is a general-purpose cluster in-memory computing system Provides high level APIs in Java, Scala and Python, and an optimized engine that supports general execution graphs. Provides various high level tool like Spark SQL for structured data processing, Mlib for Machine Learning and more
In this project, with the help of  PySpark (which is an open-source cluster-computing framework)  we want to  implement Word Count on Apache Spark running on Kubernetes and Using PySpark to implement PageRank on Apache Spark running on Kubernetes.

#### How to run ####
<details>
<summary>Below is the document with detailed instruction</summary>
<a href="https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Spark%20Project_wordcount_pagerank/CS571-ApacheSpark_on%20Kubernetes-19529-Maryam-Taherzadeh%20(1).pdf"> document</a>
</details>

<details>
<summary>Below is the Google slides with more details of the project</summary>
<a href="https://github.com/Maryam-Taherzadeh/Cloud-Computing-Infrastructure/blob/main/Spark%20Project_wordcount_pagerank/CS571-ApacheSpark_on%20Kubernetes_GoogleSlides-19529-Maryam-Taherazadeh.pdf..pdf "> Slides</a>
<summary>Below is the the link of the google slides</summary>
  https://docs.google.com/presentation/d/1tI9B2_Y5JQeQSuSUhthAuFMwhqlBIVef3I_FrnS4f6Q/edit#slide=id.p
</details>
 
#### Refrences

https://www.datamechanics.co/blog-post/pros-and-cons-of-running-apache-spark-on-kubernetes
https://towardsdatascience.com/how-to-guide-set-up-manage-monitor-spark-on-kubernetes-with-code-examples-c5364ad3aba2
https://www.datamechanics.co/apache-spark-on-kubernetes
https://spark.apache.org/docs/latest/running-on-kubernetes.html
https://npu85.npu.edu/~henry/npu/classes/master_apache_spark/kubernetes/slide/exercise_kubernetes.html
https://npu85.npu.edu/~henry/npu/classes/master_apache_spark/kubernetes/slide/index_slide.html
