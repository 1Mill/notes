https://miro.com/app/board/uXjVPHkRum4=/

* Spreading technical practicies
  * https://sammancoaching.org/
    * Dedicated learning hours
  * Hunter Industries has 7 dedicated learning hours per week. Use Microsoft Teams to host group learning sessions - like Katas on design patterns.
  * Found success with regularl Katas to level up everybody in the org
  * Find a peice of legacy to refactor as a mob on a regular basis to (1) share knowledge on how the code works and (2) establish software design patterns like a Kata.
    * One person did it 15 minutes every day and recorded the session to build a repositiroy of practicies to reference in the future
  * If you teach something you learn it better
  * Weekly mob refactor on production code
  * Stuggle to communicate practicies between teams because every team is so siloed. 
    * Remote work makes this even more difficult because less hall-way conversations to get the bigger picture
    * https://www.fluentcpp.com/2017/04/04/the-dailies-a-new-way-to-learn-at-work/ - host dailies to have conversations with others in the organization
    * Not enough slack in the system to focus on anything except for output (e.g. coding features)
  * Diffusion of innovation theory
    * Get buy-in from early adopters to then evangelize it to effect change. 
    * https://sphweb.bumc.bu.edu/otlt/mph-modules/sb/behavioralchangetheories/behavioralchangetheories4.html
    * https://www.youtube.com/watch?v=yZzVzNovBNg
  * https://wallabyjs.com/ - get faster feedback on JS tests
  * "Never stop learning" - Art Bergquist
 
* What practicies are "non-negotiable" at various org scales?
  * CICD
  * Infastructure as Code so that you can focus on business value rather than taking care of pets
    * Pets versus cattle infastructure. Pets you have to take care of, cattle are more replacable.
    * Terraform
  * Running tests as part of CICD so that tests never diverge from intented system behavior. 
  * Automation can be expensive (e.g. running preview environments), so find that balance between when it is needed when and be sure everybody is on the same page to keep costs down!
  * 7 CTOs - https://7ctos.com/
    * Trunk based development is a fundemental requirement
  * What is the value of PRs? Burocracy, control, or that the code is reviewed?
    * Mobbing eleminitates the need for async reviews.
    * What value is being produced by the PR process?
    * You can add multiple authors to commits in Git
    * MobShell.sh - https://mob.sh/, does git handoffs using a temporary branch. Adds all authors on merge. 
  * TDD
    * Useful for preventing regressions
    * TDD is a design tool
    * Useful for tackling legacy code by (1) writing 
    * Approval testing - https://www.youtube.com/watch?v=fCyu2ebXA8o, https://approvaltests.com/
    * Working effectively with legacy code - https://www.amazon.com/Working-Effectively-Legacy-Michael-Feathers/dp/0131177052
  * Sometiems you have to clean the campground without cleaning the entire forest. Focus on refactoring the immediately important stuff to deliver customer value. 
  * People really like JetBrains
  * Small steps with Source Control
    * 2 minute Kata: every 2 minutes commit if tests pass or revert

* Driving change from below
  * Artificial deadlines promote cutting corners
  * How do you communicate the impact of technical debt on flow?
    * Create working agreements: every 2 feature tickets is 1 technical debt ticket
    * As you cook dinner you are making a mess, if you clean as you go it doesn't look messey. If you don't clean, eventually you are forced to clean. 
    * Fear of stakeholders is that a focus on refacotiring will stop outputting.
    * Bugs take away from outputting
  * Need regression level testing so that corner cutting doesn't break existing features
  * "Microservices are like agile: it doesn't solve problems but reveals them more quickly." - Dave Adsit
  * How do you change the initera of the past? 
    * Lead through example to demonstrate what change looks like and how they improve KPIs - a lighthouse team.
    * Share ideas through informal channels (e.g. learning sessions, paired programming, be in the same room together) 
  * Working in a collaborative open space is better than in isolated spaces
    * Open office concepts do not mean collaborative.
  * If the team supports remote, the entire team should be remote. Hybrid in-person and remote meetings are clunky. 

* Microservice architectures
  * Use shared library to standardize communication between microservices which includes logging, etc.
  * Each microservice is a cell in an organization. Each cell is connected to the central nervus system but reacts differently. 
    * How do we do sync and async requests for every microservice? Need to be the same for every microservice.
  
* How do you remote mob?
  * Agree on core working hours where everybody is online at the same time
  * Do not create PRs outside of the mob, use that time for investigating but not comitting to decisions. Discuss and commit as a mob / team.
  * Break and mini retros about every hour
    * "What good can we turn up?"
    * Mobster timer - http://mobster.cc/
    * Everyone should feel safe enough to take breaks
  * https://mob.sh/
  * https://mobti.me/
  * https://pop.com/
  * One year of Remote Mob Programming - https://www.youtube.com/watch?v=2jxO8RYvmso, https://www.agilealliance.org/resources/experience-reports/one-year-of-remote-mob-programming/
  * Try to build a culture of Open Space concepts for mobbing. 
    * Whomever is present is the right people. 
  * How to counter act "divide and conquere" mentality with the intent of siloing work?
    * Some people prefere to work solo
    * Divide and conqurue does not mean divide people but instead divide problems - run multiple mobs around those smaller problems.
  * Cylcing between solo and mobbing is an akward state to navigate because of the uncertainty around team working agreements. 
  * The cost of communication is significantly reduced when everybody is in the same "room" / mob because people are constantly have conversations on everything form software design to functionality. 
  * How do you find core working hours when people have different scheduled (e.g. pick kids up from school, morning birds, night owls, etc.)
    * Morning birds and night owls find overlap time everyday to transition mob from morning to night crew. Works also for international teams.
      * Acts as handover to discuss decisions that were made or discoveres. 
    * Whoever is present are the right people to keep things flexible
    * Do a write up at the end of the day to facilitate async hand off for the next mob or your future self. 
  * As part of mini retro when clousing out the mob: "Where do we pick up next?"
  
