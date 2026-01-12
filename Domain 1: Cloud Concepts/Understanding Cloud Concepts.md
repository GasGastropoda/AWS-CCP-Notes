# Domain 1: Cloud Concepts

## Cloud Computing Requirements

- in order to be considered cloud computing, the service needs to offer the following:
    - ***On-Demand Computing*** = the ability to provision computing features or capabilities (ex. servers, databases, network capabilities, storage) whenever needed
        - these capabilities need to be provisioned with minimal human intervention to be considered on-demand and self-serviceable.
    - ***Network Access*** = must be connected to a network in order to access and provision any required resources
        - this capability allows building via __AWS Console__ , HTTP(S), VPN, SSH, and other remote options
    - ***Resource Pooling*** = used to serve multiple customers via many servers and databases to offer on-demand provisioning and environment building. Pooled resources are available to all users. 
        - the exact location of resources should not be made known
        - when spinning up an instance, the user selects the region where the servers are located in. AWS chooses any server within a datacenter located in the chosen region. The user is granted the right to select their availability zone.
        - ***economies of scale*** = cost advanttages that cloud providers can achieve as their operations expand. This allows them to reduce the cost per unit of service. AWS can pass savings to their customers  while providing resources needed for them to scale and grow. 
    - ***Elasticity*** = services need to be able to automatically scale its resources according to demand. Whenever those demands decrease, the service should efficiently scale back down.
    - ***Resource Monitoring and Billing*** = removes the need to pre-assign resources and reduces the worries of demand estimates. AWS's greatest benefit is their pay-what-you-use model.
- AWS has __global Infrastructure__, which are a collection of smaller infrastructure groupings connected to their global high-speed network.
***- for the exam, make sure you understand regions, availability zones, and edge locations.***
- To make sure you have a secure and tolerant system, you need the following:
    - ***High Availability (HA)*** = requires a design with ***minimal downtime***
    - ***Fault Tolerance (FT)*** = requires a design with ***zero downtime***
    - ***Disaster Recovery (DR)*** = requires designs resilient enough to operate during a disaster
- HA and FT tend to get confused.

### High Availability
- keeps systems up and running
- main goal is to keep services accessible as often as possible 
- if a system component fails, the failure can be replaced or fixed as soon as possible
- maximizes a system's online time
- HA does not stop failures
- HA doesn't exclude downtime or stoppages
- it's meant to respond when there's a failure and fixes ASAP

EXAMPLE:
there's an app running in a server within AWS for a company's employees to be able to do their work.

- if the server goes down, employees cannot complete work and experience an outage
- if the server was designed with HA in mind, the company should be able to:
    - spin up a new server to act as a failover
    - run two concurrent servers for the application (one server acts as an active instance, while the other remains on standby)

- ***HA's Main Goal*** = reduce outages and remain operational. Designing system recovery to be fast and automatic is best. Does not concern itself too much with system downtime and should be expected in its design.

### Fault Tolerance
- a system's ability to keep operating in the event of a failure

EXAMPLE:
Once again, we have an app running in a server within AWS for a company's employees to do their tasks.

- this time, with FT in mind, the company deploys two servers. If one server goes down, the other server takes over with virtually no downtime, and the service continues to function.
- instead of one active and one passive instance, there are two active instances deployed.

- FT designs prevent failures and operate through failures
- it's considered to be more expensive than HA

### Elasticity
- ***Scaling*** = a system's ability to increase and decrease its load. Systems scale based on whether or not they need to shrink or grow.
    - when you're scaling a system, you're ***adding or removing resources.***
    - there are two forms of scaling:
        - ***Vertical*** = the resizing of __EC2 instances__ by adding or removing memory and CPU resources to best handle demand. This form of scaling may require a reboot in order to apply changes, resulting in service disruption.
            - scaling to a larger size results in higher costs
            - this form of scaling does not require any modifications to applications
        - ***Horizontal*** = known to fix some of the issues that vertical scaling introduces. This form of scaling adds on instances of the same size.
            - apps are duplicated into each newly added instance
            - a load balancer can be used to distribute service load across all instances
            - ***something to consider when using horizontal scaling:***
                - ***Sessions*** = when deploying horizontal scaling, you don't want to disrupt a user's session. Instead of having an instance being stored on one server, horizontal scaling has the session spread amongst multiple instances to manage service load.
                    - ***Sticky Sessions*** = to ensure that users do not lose their sessions, it prevents switching between servers. When implemented, it generates a cookie which identifies the backend instance to save the session state.
            - horizontal scaling is considered cheaper since it involves deploying multiple, smaller instances. These instances can be cheaper than larger instances. 
- ***Elasticity*** = the act of using automation with horizontal scaling to match an instance's capacity and supply with current service demands.
    - demand is rarely linear
    - AWS allows launch configurations and autoscaling to scale systems and automize costs. This applies to the pillars of AWS's Well-Architected Framework (AWS WAF)

## AWS Well-Architected Framework
- considered to be AWS's ***best practices and core strategies to architect systems in the cloud***.
- these are meant to assist with designing and building reliable, efficient, secure, and cost efficient systems.
- ***the WAF consists of 6 pillars:***
    1. Operational Excellence
    2. Security
    3. Reliability
    4. Performance Efficiency
    5. Cost Optimization
    6. Sustainability
- some of these considerations include:
    - stop guessing your cloud capacity
    - use auto-scaling to ensure supply meets demands
    - test systems at production scale
    - automate architecture to allow easier experimentation
    - allow evolutionary changes in your architecture
    - use architectural data to make necessary changes
    - schedule game days to improve your overall infrastructure
    - run tests to see how your system responds at production level
- understanding WAF gives a solid basis into understanding how AWS functions
- AWS ***offers as well-architected tool and best practices. This tool reviews and compares your workloads to latest best AWS practices for architectual design, using the WAf as a point of reference.***

### Operational Excellence
- **defined as the capability to:** 
    - support development and run workloads efficiently
    - gain insight into operations
    - continuously improving supporting procedures and processes to deliver business value
- **the five design principles to achieve operational excellence are:**
    1. Perform your operations as code
    2. Make frequent and small changes
    3. refine operations and procedures frequently
    4. anticipate failures
    5. learn from operational failures

### Security
- defined as **the ability to proterct data, systems, and assets** within the cloud
- **the seven design principles to design a secure system are:**
    1. implement a strong identity foundation
    2. maintain traceability
    3. apply security at all layers
    4. automate security practices
    5. protect data in transit and at rest
    6. keep people away from data
    7. prepare for security events

### Reliability
- defined as **the ability of a workload to perform intended functions correctly and consistently when expected**. This also includes **the ability to test and operate throughout its entire lifecycle in the workload**
- **the five design principles to design a reliable system are:**
    1. automatic failure recovery
    2. testing recovery procedures
    3. the capability to scale horizontally to increase the availability of a workload
    4. stop guessing your capacity
    5. manage changes by using automation to deploy them

### Performance Efficiency
- defined as **the ability to use computing resources efficiently to meet system requiremenbts and maintain that efficiency as demands and technologies evolve**
- **the five design principles to maximize performance efficiency are:**
    1. democratize advanced technologies
    2. go global in just minutes
    3. use serverless architecture
    4. experiment often
    5. consider mechanical empathy

### Cost Optimization
- defined as **the ability to run systems to delivery business value at the lowest cost point**; maximizing performance while minimizing costs
- further covered in Domain 4.

### Sustainability
- defined as **the practice of focusing on environmental impacts and placing emphasis on energy consumption and hardware/software efficiency**; being environmentally aware helps set limits to reduce the impact that cloud computing has on the environment
- **the six design principles to design a sustainable cloud environment:**
    1. understand your impact
    2. establish sustainability goals
    3. maximize utilization
    4. anticipating and adopting new technologies that provide more efficient hardware and software
    5. using managed services
    6. reducing downstream impact of cloud workloads


***there may be questions on the exam asking which design principles are best for each situation, so make sure to understand them!***

## Other things to know
- ensure you understand:
    - how to read and design solutions
    - know how to design for the future
    - know how to decouple components (this reinforces the architectual design principle)
    - know how to implement elasticity via auto-scaling
    - know what security and parallelization looks like in AWS (necessary for building highly-scalable services)
        - **Parallelization** = similar to the process of decoupling; divides a job into its simplest form and distributes the load to multiple components to handle demand
            EXAMPLE: breaking down datasets into smalle chunks to allow them to be processed simultaneously. This provides faster processing tiems
    - how AWS gives the advantage of **being able to focus on services and designs without the concerns of managing the underlying hardware. This gives the benefit of fast implementation and resource launching**
