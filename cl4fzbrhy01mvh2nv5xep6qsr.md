## Introduction to Container Orchestration

Containerization made an entrance in the DevOps landscape when Docker was launched in 2013. Even though the fundamental concept of containerization existed before Docker, it was the first time people on a large scale were introduced to the idea of running applications inside a container.
 
If you have a number of apps to run, as you likely do if you have migrated to the cloud, containers come in handy. They make it easy to turn apps on and off to meet changing demands. They also let you move apps seamlessly between different servers. But at the same time, containers come with their own set of complexities which can get out of hand without proper management.

To do all of this you need a management platform which can spin containers up, suspend them or shut them down when needed. Ideally, they should also control how the containers access resources like network and data storage. This is where orchestration platforms provide us with a solution to this piece of the puzzle. Orchestration provides us with a number of features like provisioning hosts, instantiating a set of containers, rescheduling failed containers, linking them together through agreed interfaces, exposing services to the outside world and of course, scaling up or down by adding or removing the containers.  

In this article, you will learn in-depth about 
* What is Container Orchestration? And why is it needed?
* History of Container Orchestration
* How does it work? 
* Benefits and Drawbacks
* What are the top container orchestration tools available today?

## What is Container Orchestration?

Container orchestration is an automated and simplified process of managing every aspect of individual containers and their dynamic environments. It is nothing but an automated approach to the deployment, scaling and networking of the containers.

### Why do you need container orchestration?

Let's assume you have a web application and a database running on two different containers. With time, the traffic to your web app increases, and it is not able to manage this load. As a response to this, you decide to scale the web-app server by adding a few more container instances of the web app across multiple hosts. Similarly, the database container will also be needed to scale accordingly. Adding new containers seems reasonable if the amount is small, but what happens when you have to deal with the addition of a much higher container count, like in hundreds or more?

Also, how do you decide which container goes on which host? Or how do you determine the number of containers you need to run per host? What happens if a container is using too much memory? How do you identify the health of each container? In case some container turns out to be unhealthy, how do you replace the failed container?  Do you want a mechanism to replace this container automatically?
Last but not the least, how do you ensure security and access for these containers?

This is where Container Orchestration platforms come into the picture.

## History of Container Orchestration - how did we get here and why?
There has been a huge shift in trend from using monolithic architecture to microservices in recent years. This rise of microservices-based architecture caused increased usage of container technologies. Containers act as the perfect host for small independent applications like microservices. This led to applications having hundreds or sometimes even thousands of containers running at the same time. Managing these loads of containers across multiple environments using scripts and self-made tools can be complex and time-consuming. This demand for a proper way of managing these hundreds of containers caused the need for container orchestration technologies.

## How Does Container Orchestration Work? 
Depending on the orchestration platform being used, there can be different techniques to implement container orchestration. Generally, these platforms work based upon the user-created JSON or YAML files which describe the configuration of the application. Most orchestration platforms support declarative configurations.

These configuration files prompt the orchestration platform on how to pull the container images, how to link containers through a network, how to mount storage volumes and where to store log data. 

Container orchestration tools also help with the deployment scheduling of containers into clusters and can detect the most appropriate host for the deployment. This host is selected on the basis of guidelines, labels or metadata provided in the configuration files. Once selected, the container orchestration platforms use predefined guidelines to look after the container throughout its lifecycle.

## Benefits

Container orchestration aid in managing the container lifecycles in large environments. They simplify container management. Container Orchestration can provide software teams with the following capabilities - 

* **Improved application deployment** - 
Container orchestration tools can scale applications up and down with minimal manual intervention. This results in high performing applications. Container orchestration tools can also help in spreading application load evenly across the containers.

* **Improved Productivity** - 
With container orchestration in place, software teams can rapidly test, deploy, patch and scale as and when needed.

* **Better Security** -
As applications in containers run in an isolated environment, it ensures better security. Besides with container orchestration tools, communication between different services can be set restrictively, allowing only certain services to communicate to and fro as well as, only specific types of services to be exposed to the outside world.

* **Monitoring** - 


* **Reduced costs and resource needs** - 
Multiple containers can be provisioned inside the same host. Containers are lightweight and do take up much space as an OS image normally would. Besides, container orchestration tools can be used to manage these resources more efficiently, ultimately reducing the overall cost to be incurred by the organization.

* **Microservices** - 
Each microservice can be provisioned on different containers and with the help of container orchestration tools they can be scaled or modified independently, as and when needed. With the help of orchestration platforms, microservices can communicate more fluidly with each other within the cluster.

These are some of the benefits that container orchestration platforms offer.

## Drawbacks
Container Orchestration tools have turned out to be a boon for many organizations but they come with their set of cons as well. Here are some of them - 

* **Overkill for simple applications** - 
Container orchestration can be an overkill for simple applications. If you do not intend to build anything complex which will be accessed by thousands of users at the same time or deploy an app with high computing resource needs, container orchestration would be highly unideal.
* **Complexity** - 
Container orchestration platforms come with their own level of complexities. Developers, who do not come from an infrastructure background, can have a tough time figuring out stuff with the orchestration platforms. 
* **Transition to orchestration platforms can be challenging** - 
Adoption of orchestration platforms can require some effort. It can be difficult to gauge this effort as use-cases for every organization would be different. It also depends on various other factors like - which programming language is being used and what is the desired environment for that application to run? Or is the application already containerized?
* **Expensive compared to other methods** - 
Container orchestration can be quite cheaper if used correctly but it can turn out to be quite expensive as well if the above-mentioned drawbacks are not taken care of. As discussed, migrating or deploying small applications to these orchestration platforms may not be wise and will take up a lot of your engineering time. So besides the infrastructure cost, you will also incur this indirect cost.

## Top Orchestrators present in the Market
The top 3 widely used options for Container Orchestration vary in implementation and how you interact with them. Here are some brief descriptions of the platforms and a list of top companies that have adopted them - 

### Kubernetes
Kubernetes or also known as K8S is an open-source container orchestration tool, which was originally developed by Google. It is by far one of the most popular open-source projects to take the IT world by storm. It seems like almost everywhere you go, every news article you read, or blog you encounter, tells a story of how Kubernetes has revolutionized the way DevOps and IT infrastructure work, like no other platform before it. 

Started as an internal project by Google at first, Kubernetes has the capability of deploying, managing, configuring, and orchestrating at both small and large scales. Kubernetes, one can easily run containerized applications across multiple clustered
nodes, automatically maintaining the desired number of replicas, service endpoints,
and load-balancing across the cluster.

Some top companies using Kubernetes - 
* Google
* Spotify
* Pinterest

### Docker Swarm
Docker Swarm is Docker's very own container orchestration tool. It gives you the easiest route for orchestrating a cluster of Docker hosts. Docker Swarm comes packaged with Docker which makes it simplest to configure. Docker Swarm has a low learning curve and is very simple to use, making it the best choice for the deployment of smaller applications.

Those wanting to leverage extensive features of Kubernetes while using Docker Swarm can opt for the Docker Enterprise Edition which offers a bundle of both the tools. Docker Swarm supports Windows and Mac OS X but uses VMs to run on non-Linux systems. So if an application is deployed on a Windows container, it won't be able to run on a Linux system. Kubernetes has an upper hand in this as it is not operating system specific.

Some top companies using Docker Swarm -
* Apple
* Mozilla
* Wells Fargo

### Apache Mesos
Developed at UC Berkeley, Mesos has gained huge popularity among large organizations like Twitter, eBay, Airbnb and Paypal. It has a very lightweight interface and can provide support for multiple programming languages. Mesos is known for providing flexible architectures and high scalability, owing to the ability to scale to a large number of nodes within the infrastructure. 

Ironically, Mesos is not a `container orchestration` tool. It is in fact a cluster management tool. Mesos, when combined with a framework called `Marathon`, can work as a proper container orchestrator. Although Mesos promises a lot of scale, it comes with a lot of complexity. It has a steep learning curve and requires high technical expertise. This is the reason why Mesos is only widely adopted by large-scale organizations and may be unideal for small companies that have a limited number of resources.

Some top companies using Apache Mesos -
* Airbnb
* Twitter
* eBay

In the end, which container orchestration tool you use will depend on the scalability that you want to achieve and in which ecosystem you and your organization feel the most comfortable.

## Conclusion

To sum up, container orchestration helps us automate the process of deploying and managing containers in bulk. It simplifies container lifecycle management in large environments, offering developers improved agility with their systems and helping them deploy applications to the cloud much faster and with more efficiency. For organizations which reply on the deployment of their applications on containers and require them to scale, container orchestration is very valuable and of the utmost importance.

<hr/>

**If you liked what you read, do consider sharing the article with a friend and connect with me on Twitter - [@afraz_momin](https://twitter.com/afraz_momin). Also, subscribe to my newsletter and stay up-to-date with my latest blog posts.**







