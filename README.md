# kubernetes_project

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

#### Result

- How to acess a student's score
'''
curl cs571.project.com/studentserver/api/score?student_id=11111
'''
![picture alt](https://github.com/Maryam-Taherzadeh/Kubernetes-project/blob/main/pic/pic_1.png)

- How to access List Of Book

'''
curl cs571.project.com/bookshelf/books
'''
![picture alt](https://github.com/Maryam-Taherzadeh/Kubernetes-project/blob/main/pic/pic_2.png)

- How to Add a Book
'''
curl -X POST -d "{\"book_name\": \"cloud computing\",\"book_author\": \"unkown\", \"isbn\": \"123456\" }" http://cs571.project.com/bookshelf/book
''''
![picture alt](https://github.com/Maryam-Taherzadeh/Kubernetes-project/blob/main/pic/pic_3.png)

- How to Update a Book
'''
curl -X PUT -d "{\"book_name\": \"123\",\"book_author\": \"test\", \"isbn\": \"123updated\" }" http://cs571.project.com/bookshelf/book/id
''''
![picture alt](https://github.com/Maryam-Taherzadeh/Kubernetes-project/blob/main/pic/pic_4.png)


- How to Delete a Book
'''
Delete a book curl -X DELETE cs571.project.com/bookshelf/book/id
'''
![picture alt](https://github.com/Maryam-Taherzadeh/Kubernetes-project/blob/main/pic/pic_5.png)



  ####Refrences:          
  
https://npu85.npu.edu/~henry/npu/classes/capstone/rest/slide/index_slide.html
https://npu85.npu.edu/~henry/npu/classes/cloud_computing/mongodb/slide/index_slide.html
https://v1-19.docs.kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/

