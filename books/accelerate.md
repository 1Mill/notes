# Accelerate

## Book

<https://www.amazon.com/Accelerate-Software-Performing-Technology-Organizations/dp/1942788339>

## Article

TODO

## Notes

* Work is work: don't have have a backlog for technical debt versus features versus ...
* People are an organizations #1 asset.
* You need leadership support in action, not only words.
* Teams must be able to fail to learn
* Use external examples to influence change (i.e. working examples versus theory)

* Authors studied many organizations across different industries
* Improvement is possible as long as leadership commits the resources and members commit to improve
* Used snowball sampling
  * "...existing study subjects recruit future subjects from among their acquaintances."
* Key research questions:
  * What does it mean to deliver software and can it be measured?
  * Does software delivery impact organizations?
  * Does culture matter and how do you measure it?
  * What technical practicies appear to be important?

* Technology is the tool used by companies to serve people more effectively: making their business more competitive in the market.

* Focus on capabilities, not maturity.
* Maturity models helps organizations get to a mature state and then are considered "done" whereas capability models help companies to consciously focus on improving.
* Capability models are dynamic and customizable which let teams, departments, etc. adjust them to their needs.
* Capabilities set a big picture from leadership for teams to work towards
* Focusing on capability teams can continously focus on improvement and focusing on the right capabilities companies drive improvements in their outcomes

### Chapter 2: Measuring Performance

* Most measures focus on outputs rather than outcomes (e.g. lines of code vs improved customer experience)
* Velocity is often misused for capacity planning or compairing how must "faster" one team is versus another
* Velocity is often misused to maximize utilization, which means there is no slack in the system to adjust or handle unplanned work (e.g. fix unexpected edge cases, improve readability of existing code)
* As utilization nears 100% then lead time trends towards infinity
* Measures must focus on outcomes, not outputs - avoid meaningless busy work

* Key metrics for measuring performance
  1. Delivery lead time
  2. Deployment frequency
  3. Time to restore service
  4. Change fail rate

* Delivery lead time
  * Lead Time is the amount of time between a customer making a request and a customer being satisfied.
    * Cycle Time is the amount of time between the work moving from In Progress to Done, which is a subset of Lead Time.
  * Lead Time is composed of both Discovery (i.e. figuring out how to satisfy the customer) and Delivery work (i.e. doing something to actually satisfy the customer).
  * Short Lead Time lets companies get feedback sooner if the customer was satisfied or not.

* Deployment frequency is a stand in for reduced batch size
  * A deployment is pushing code to production so that it is used by customers
  * A deployment may consist of multiple releases which are new features, changes, etc. deployed together to customers

* A common misconception is that moving faster must mean trade offs with these other metrics (e.g. "move fast and break things")
* High tempo comes from discipline around these metrics

* Working and delivering in small batches lets teams get customer feedback more frequently to ensure they are building the right thing.

* [Wardly Mapping](https://learnwardleymapping.com/)

* Make evidence based decisions to improve teams (e.g. does X improve, hinder, or maintain Y?)

* In learning cultures metrics help drive improvement, but in non-learning cultures they are used to control.

### Chapter 3: Measuring and Changing Culture

* Company culture has 3 levels:
  1. Basic Assumptions - Norms (very invisible, hard to put in writing)
  1. Values - Lense to interpret events
  1. Artifacts - Written mission statements, standard operating procedures, etc. (very visible)

* Good information flow is critical to successful companies
* Generative companies encourage collaboration through shared vision
* Burocrative companies encourage efficiency
* Trust is needed for open communication so problems are identified and solved quickly

* Change failure rate was not found to be valid in their construct so they excluded it from their analyses

* Who is on a team matters less than how a team works together
* Accidents are rarely one peron's fault: instead they are emergent from many actions taken by many different people, so, working together to create a big picture is important to avoid and or accidents.
* Human error should be a chance to improve how companies communicate.

### Chapter 4: Technical Practices

* Continously delivery
* Build quality in to eliminate the need for inspection
* Work in small batches with target outcomes / metrics
* Automate repetative work
* Relentlessly pursue continous improvement

* Goal of management is to make the above system-level outcomes extremely apparent

* Keep Git branches sort lived and merge into trunk frequently
* Write automated tests so engineers are confident in their changes
* Continously delivery so that it becomes non-event and not a special event

* If you want to improve culture do CICD because it is a shift in mindset

* Rework and un-planned work was significantly differnt between high and low performers indicating code quality is important to being effective

* Failure Demand: rework caused by not doing the right thing the first time.

* To be effective use ...
  * Version Control (e.g. GitHub)
  * Reliable Test Automation - flaky test erode trust
  * Test Data Management
  * Trunk Based Development - most branches live less than 1 day
    * Speculated multiple long-lived branches discourages refactoring and communication - people go live off in their own world for too long without feedback
  * Information Security
  * Continuous Delivery
    * Improve quality, culture, etc.

### Chapter 5: Architecture

* TODO
