# Dockerize-with-IBM
In this tutorial we will learn how contaniers are different from the perivous architectures and how IBM contianer registry make our development lifecycle easier.

Steps :
1. [History of different architectures before Docker Platform](#1-history-of-different-architectures-before-docker-platform)
2. [Docker Architecture](#2-docker-architecture)
3. [IBM Container Registry & Docker together](#3-IBM-Container-Registry-Architecture)
4. [Demo](#4-demo)

## 1. History of different architectures before Docker Platform

[image]


Before going through these architecutre let me clear you all architectures practices are good and it totally depends on your infrastructure usecase.

### Traditional architecture  :
In early ages, there was a concept of physical servers and on top of it, there's OS  ofcourse to bootup the settings for us. Once our server is up we can deploy our applications there. Now, what's the constraint here?  There is no proper way to limit my resources. Example: Suppose I am running my "A" application after 5 years, I added a new "B" application to the same server. Now "A" application started receiving a lot of traffic due to this my complete server will slow down or even crash and all the other applications attached to it will be affected.  One solution for this would be, I can setup another server and deploy my new application there but trust me it would be really costly.

### Virtualized architecture:
Before going into the virtualized architecture let add here 
IBM has done the first virtualization in 1960 on System 370. How it works? We have one physical server on the top of its OS and then installed "Hypervisor ". Hypervisor can be considered as a middleware defined software that takes all the resources from the physical server (CPU,RAM, FILESYSTEM) and help in allocating to multiple virtual machines. For more about Hypervisors checkout( https://vapour-apps.com/what-is-hypervisor/). Now as compared to Traditional deployment, virtualized deployment has the power in resource allocation. What means by resource allocation? Now it's possible to create multiple VM's with different resource configurations with reduce hardware costs. Each VM will have its own OS and on the top of it, there will be an application running.  Example: Now I can run my "A" application on VM1 and "B" application on VM2, in the future if my application "A" goes down it will not affect my other applications nor my physical server as both apps are running on different VM's.

### Container architecture:
Containers are one of the latest approaches in which when we install a container platform it directly uses the host OS. Therefore, containers are considered lightweight because a container has its own filesystem, CPU, memory, process space, and more but no OS defined in it.  As they are decoupled from the underlying infrastructure, they are portable across clouds and OS distributions. Now we can run thousands of applications as containers without worrying about if some containers go down what happens? Within a second container can get up without causing any problems to other containers running.



## 2. Docker Architecture


Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. 

There are three main components in Docker Architecture :

Docker Daemon :
When the client install Docker, on the top of its OS and  docker daemon is installed and run directly within the host machine’s kernel which is actually responsible for all the major API calls between containers and registries.

Client :
Once Docker is initialized on the client's platform they have the power of three simple commands to control the complete development life cycle.

Docker build : This will help us to execute the steps of how our application will execute, bypassing Dockerfile. The final result through this command will be a newly created image(instructions for creating a Docker container)

What are containers? Actually, containers are running an instance of an image.

Docker pull: The image is already available on some registry, and you just need to pull that image on the local machine. 

IBM Container Registry & Docker together
What is registry ?
A Docker registry stores Docker images. Docker Hub is a public registry that anyone can use. 

Docker run: Once the image is available on the local machine we can run the image as a container using the run command and can create as many containers of that image as required.

## 4. Demo
### Pre-requisites:
1. Create IBM Cloud Account [Here](http://ibm.biz/dockerize)

2. Install docker on your local machine :
[Mac](https://docs.docker.com/docker-for-mac/install/)
[Windows](https://docs.docker.com/docker-for-windows/install/)


### Steps:
1. [Install IBM Cloud CLI](#1-install-ibm-cloud-cli)
2. [Let's Dockerize the application](#2-let's-dockerizr-the-application)
3. [Log in to IBM Cloud](#3-log-in-to-ibm- cloud)
4. [Setup a Namespace](#4-setup-a-namespace)
5. [Push Docker image to your namespace](#5-push-docker-image-to-your-namespace)
6. [Pull and Run the image](#6-pull-and-run-the-image)



#### 1. Install IBM Cloud CLI
1. For Mac and Linux™, run the following command: `curl -sL https://ibm.biz/idt-installer | bash`

2. For Windows™ 10 Pro, run the following command as an administrator:
`[Net.ServicePointManager]::SecurityProtocol = "Tls12, Tls11, Tls, Ssl3"; iex(New-Object   Net.WebClient).DownloadString('https://ibm.biz/idt-win-installer')`

3. To verify that the CLI installed successfully, run the help command: `ibmcloud dev help`

#### 2.Log in to IBM Cloud 

1. Open your terminal and run the command `ibmcloud login` 
2. Enter Email and Password of your IBM account that you setup while creating the account.
3. Once successfully login, you will able to see **Authenticating...OK**
4. If you have multiple accounts then kindly select your preferred account from the option. Example Muhammad Ahsan Khan's Account (ae4eed79ad174e76882b8e52f525b38e)
5. Now in **Select a region** section you can skip for now.
6. This is a major upgrade that may have potential breaking changes. Do you want to update? [y/N]. Select **Y**
 



 




