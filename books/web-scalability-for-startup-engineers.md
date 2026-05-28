# Web Scalability for Startup Engineers

LINK

## Key Takeaways

* TODO

## Notes

### Core Concepts

* "*Scalability* is an ability to adjust the capacity of the system to cost-efficiently fulfill the demands. ... scaling should be relatively cheap and quick to do." - p 3
* "Growing a single engineering team abouve 8 - 15 people becomes inefficient, as the communication overhead grows exponentially as the team size grows." - p 4
* "'What are the constraints that could prevent our business from growing?'" - p 4
* "Avoid full application rewrite at all costs, especially if you work in a startup. Rewrites always take much longer than you initially expect and are much more difficult than initially anticipated. Based on my experience, you end up with a similar mess just two years later." - p 5
* "*Shared hosting* is the cheapest hosting solution ..." - p 7
* "There are two different types of scaling: vertical and horizontal." - p 7
* "*Vertical scalability* is accomplished by upgrading the hardware and/or network throughput." - p 8
* "Memory size is especially important for efficiency of database servers." - p 9
* "The more CPUs and virtual cores, the more processes that can be executing at the same time." - p 9
* "Vertical scalability becomes extremely expensive beyond a certain point." - p 9
* "The second biggest issue with vertical scalability is that it actually has hard limits. No matter how much money you maay be willing to spend, it is not possible to continually add memory. Similar limits apply to CPU speed, number of cores per server, and hard drive speed. Simply put, at a certain point, no hardware is available that could support further growth." - p 9
* "*Locks* are used to synchronize access between execution threads to shared resources like memory or files. ... Operations perform very often should have fine-grained locks; otherwise your application may spend most of its time waiting for locks to be released." - p 10
* "... adding more cores yield no benefit at all if the application was not designed with high concurrency in mind." - p 10
* "The core concept behind isolation of services is that y ou should try to split your monolithic web application into a set of distinct function parts and host them independently. The process of dividing a system based on functionality to scale it independently is called functional partitioning." - p 13
* "Clients that need to download images, JavaScript, CSS, or videos connect to one of the servers owned by the CDN provider instead of your servers. If the CDN server does not have the requested content yet, it asks your server for it and caches it from then on." - p 14
* "Systems that are truely horizontally scalable do not need strong servers - quite the opposite; they usually run on lots and lots of cheap 'commodity' servers rather than a few powerful machines." - p 16
* "Horizontal scalability is considered the holy grail of scalability ..." - p 16
* "... once you pass a certain point of necessary capacity, horizontal scalability becomes a better strategy." - p 17
* "Web application servers are usually easy to scale since they should be completely stateless. If developed in a stateless manner, adding more capacity is as simple as adding more servers to the load balancer pool." - p 24
* "We keep front-end servers simple and free of business logic since we ewant to decouple the presentation layer from the business logic. By creating web services, we aalso make it easier to create functional partitions." - p 24
* "The communication protocol used between front-end applications and web services is usually Representational State Transfer (REST) or Simple Object Access Protocal (SOAP) over HTTP." - p 25
* "Instead, use as few technologies as possible, because adding each new technology adds complexity and increases maintenance costs. Having more components may be more exciting, but it makes releases, maintenance, and recovery procedures much more difficult." - p 26
* "Architecture is not about Java, PHP, PostgreSQL, or even database schema. Architecture should evolve around the business model. ... Without the right model and the right business logic, our databases, messages queues, and web frameworks are useless." - p 27
* "A *domain model* is created to represent the core functionality of the application in the words of business people, not technical people. The domain model explains key terms, actors, and operations, without caring about technical implementation. ... The domain model is a tool to create our mental picture of the business problems that our application is supposed to solve." - p 27
* "The front end should have a single responsibility of being the user interface. ... In general, the front end should stay as 'dumb' as possible." - p 29
* "Event-driven architecture, as the name implies, is about reacting to events that have already ahppened. Traditional architecture is about responding to requests and requesting work to be done. ... In the event-driven model, we don't wait for things to be done. Whenever we have to interact with other components, we announce things that have already happened and proceed with our own processing." - p 32

* **Key takeaways**
  * Scaling vertically is adding more resources to a server, such as RAM, CPU, Storage, etc. so you can do more with more. Scaling vertically is adding more servers so you can do more with more but often at a cost-per-unit that is more economically beneficial. At the end of the day, scaling is about meeting demand needs in a cost-efficient way and horizontal scaling is considered the holy grail.
  * Domain models represent business problem that need to be solved by technology without needing to worry about the underlying technology. A bank transfering funds from one another to another shouldn't care what happens under the hood: it only cares that the appropriate business rules are being applied and followed.
  * Event-driven architecture is about reacting to events that have already happened (e.g. facts). This is mind-shift from traditional request-response architectures because the system is eventually consistent - not always consistent. So, you can never assume something has happened - you must build extremely resilient business rules.

### Principles of Good Software Design

* TODO

* **Key takeaways**
  * TODO

### Building the Front-end Layer

* TODO

* **Key takeaways**
  * TODO

### Web Services

* TODO

* **Key takeaways**
  * TODO

### Data Layer

* TODO

* **Key takeaways**
  * TODO

### Caching

* TODO

* **Key takeaways**
  * TODO

### Asynchronous Processing

* TODO

* **Key takeaways**
  * TODO

### Searching for Data

* TODO

* **Key takeaways**
  * TODO

### Other Dimensions of Scalability

* TODO

* **Key takeaways**
  * TODO
