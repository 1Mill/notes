# How Kubernetes And Kafka Will Get You Fired

<https://medium.com/@jankammerath/how-kubernetes-and-kafka-will-get-you-fired-a6dccbd36c77>

## Key takeaways

* Sometimes engineers strive to be "cloud agnostic" to avoid vendor lock in. But, this usually only increases operating costs with no real benefit to the business. For example, what is the cost to build a "cloud agnostic" solution versus a non-"cloud agnostic" solution? If the latter is only hypothetical it means it isn't a real business concern yet.

* Use off the shelf solutions as much as possible until they are either (a) not cost effective or (b) missing functionality important to the business. Off the self solutions trade vendor lock in for working, relability, scalable, and cost effective infastructure which are more valuable to startups than trying create an agnostic solution.

* It takes people, time, and money to manage infastructure. Sometimes these costs are easy to see like the cost of running an ECS Service in AWS. But other times they are more indirect like updating the ECS Service configuration to a new version. Infastructure maintinance which requires people. Working hours which cost the business money.

* All of the above points apply just as much to infastructure as they do working software.

## Notes

* AWS SQS is a better serverless alternative to Kafka until you start hitting it's limits.
* Using off the shelf solution is usually more cost effective until the service can (a) is not effective at new operating sizes or (b) is missing some sort of functionality important to the business.
* Serverless is almost always better than managing it yourself until you get to a certain size.
* Sometimes engineers try to be "cloud agnostic" to avoid vendor lock in by over engineering their server infastructure for a risk that is often meaningless to the business
  * How often do you migrate between SQL to NoSQL databases?
  * How often do you migrate from AWS to Azure?
  * How often do you migrate from GitHub to Bitbucket?
  * How often do you migrate from Node to Python?
* Often, infastructure is releatively static and only an single API call away if you start migrating in tiny batches.
* When doing an ADR provide alternative solutions and why they aren't as good
* Offload SLA to vendors through serverless / off-the-shelf infastructure as much as possible
* "Managers trying to solve problems by replacing a number of people around the problems" if things do not improve with enough time
* Infastructure becomes an economic problem for the business when not implemented in a way that aligns with the needs of the business
  * Avoid over engineering - only respond to real market signals
* [Total Cost of Ownership (TOC)](https://www.techtarget.com/searchdatacenter/definition/TCO): "an estimation of the expenses associated with purchasing, deploying, using and retiring a product or piece of equipment."
  * ((Money Gained - Money Spent) / Money Spent) * 100
  * An example of a "direct cost" is the upfront cost to purchase something
  * An example of an "indirect cost" is the sometimes hidden cost to support something over time (e.g. using team capacity to perform updates)
* "It takes people, time and budget to operate a Kubernetes cluster."
  * This is true of any server infastructure
* If TOC is 2 to 4 times more expensive than the next best alternative go with the next best alternative.
