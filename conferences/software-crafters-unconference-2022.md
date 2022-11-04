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
  * "If you can only pick 1 agile practice make it retro spectives so you can improve"

* Simulators over mocks + contract testing
  * Test the flow of data through the system
  * Do not write tests for things in the middle - test inputs and outputs. 
  * Mock external APIs, not middle-man classes. 
    * When we call `Rudderstack.track()`, test that that the Rudderstack API is called. 

* Boring infrastructure
  * Infastructure is not a differentiator in business
  * Wardley mapping - https://learnwardleymapping.com/landscape/
    * K8 and VM are product space, Serverless in Commodity space
    * https://twitter.com/swardley/status/1376930531976306699?lang=en
  * Docker containers make it easier to manage infastructure
    * Don't have to worry about what package is running in production versus development
  * K8 is the new legacy softweare, serverless is argued to be the new standard (I definitely agree haha)
  * Severs as pets to servers to cattle metaphore to describe infastructure
    * Infastructure as code (cattle) affords differnt deployment strataegies
  * Most K8 Docker containers have known vulnerability because building the docker container is an engineering problem and engineers typically don't usually handle security updates until there is a problem.
  * https://www.npmjs.com/package/forever restarts node on any sort or error
  * https://www.cloudfoundry.org/
    * Makes developers jobs very easy
    * Top down driven (K8 is bottom up)
    * Small number of OPs people to manage
  * Borning infastructure lets developers focus on customer value versus managing infastructure.
  * https://aws.amazon.com/ecs/
  * https://netflix.github.io/chaosmonkey/
    * Build resilience through terminating instances in production to ensure code works as expected (nothing is to big to fail)
  * Developers get paid for delivering customer value and only get punished for security flaws. Punishment is infrequent and therefore there is little incentive to be proactive about.
    * Very similar argument for technical debt
  * The type of deployment strategy an organization has is reflective of cultural practices
  * Rent an OPs is a growing trend since maintaining an OPs team is expensive 
  * OPs is firefighting and improving infastructure
  * Borning does not mean primative
    * Focus seems to be a simplicity, more turn-key
  * Google has a philosophy that they won't do anything that requires a help desk, out sources this to 3rd parties, which makes GCP difficult (definitely been my experience)

* Communicating technical debt
  * 1-5 stars of technical debt per story / ticket
  * https://www.youtube.com/watch?v=TQ9rng6YFeY&ab_channel=DevTernityConference
  * Trust influence loop: build trust, influence change, repeat
  * Quality Views by Colin Breck

* Software developer habits
  * https://jamesclear.com/habits - The Habits Guide: How to Build Good Habits and Break Bad Ones
  * https://retrotool.io/ - https://retrotool.io/p_VwOMfEUZZXcrCdsRi9P
  * Good habits
    * Kanban hygieng - Ensuring that the stat of tasks is properly reflected / updated on the board
    * Ensure things deployed successfully
    * Be mindful of WIP limits
    * Regular refactoring
    * Breaking work down into smaller pieces
    * Merging to main severl times a day
    * Automated testing, infastructure, etc.
    * Teaking breaks
    * Learning frequently
    * Blameless retros
    * Declaring "backlog bankruptcy" to trash everything (bugs, ideas, ..., everything!); make work about doing not managing a list.
    * Keeping dependencies up to date (try to automate as much as possible)
  * Bad habits
    * Giving fixed timelines because usually other stuff comes up
    * Waiting to long to get feedback
    * Not being conscientious of terminology, initialisms, etc. - try to make sure everybody is on the same page
    * Big commits - bigger risks
    * Not taking breaks to process through problems
    * Not running tests before pushing
    * Status meetings - status should be viewable through tool (e.g. JIRA) 
    * Blaming - people do the best with the knowledge they have at the time
    * Large batches
    * No WIP
    * Estimations - the act of estimations is waste, you never know what is going to come up between now and done
      * Estimates are just (informed) guess that people take to seriously
      * Estimates should not be treated as a promise
      * Estimates traditionally translate into scope + date
        * What day (Y) will we have feature X (scope)?
      * Work on the most valuable stuff first, pivot only when it is done or becomes not the most valuable.
      * Agile product developmen fits more into a Kanban style than a Waterfall style
    * Not asking clarifiying questions
    * Ignoring failing tests
    * Conflating "refactoring" with "rewriting" - refactoring means it does not change the current behavior
    * Creating complex solutions when simple ones suffice
  * Desired habits
    * Continous retros
      * Do retros very frequently and regularly
      * Some people do multiple retros a day (works best when mobbing)
      * The most important thing is being addressing what is not working and amplifying what is working
      * Add ideas to retro board async as ideas are generated rather than trying to remember them all on the day of
      * Give feedback at the right time - training a pet requires instant feedback to relate action to consequence. 
      * "I have this feeling about this ..."
    * Having difficult conversations
      * Use a friend (somebody with psychological saftey, trust) to moderate
      * Use Situation Behavior Impact (SBI) to help frame the conversations to make it more productive
    * Thin slicing
    * Giving better feedback
    * Fearlessly examining our ways of working to find improvements
    * Learn as a team
    * Batching questions for team lead / product owner

* Why can't we have nice things?
  * Limiting WIP forces the team to focus on delivery versus the number of incomplete things - done is better than started
  * Async PRs increase WIP because of queueing and delays between feedback and reaction
    * Mob programming eliminates async PRs - they happen sync
    * Permit people to merge straight into main
  * Mob programming
    * https://collaboration.csc.ncsu.edu/laurie/Papers/ieeeSoftware.PDF
  * https://www.amazon.com/Nine-Lies-about-Work-Freethinking-ebook/dp/B07C3ZT28C
    * Best way to evaluate employees is to ask employees "who would you want to work with on a critical project?"
  
* Overcoming communication barriers with remote work
  * Try to schedule messages, emails, etc. for the person's working hours 
  * The larger the power differenctial, the more cautious you need to be with when you send things. If the CEO sends you a message at 9pm you might feel the need to reply. 
  * Social connection is difficult / different in fully remote life
  * Timezone (e.g. east vs west coast) and lifestyle differences (children vs no children) are a challange when trying to establish core working hours in a time
  * Lots of channels to monitor (e.g. email, slack, meetings, calls, etc.)
  * Cross polination from co-located teams is missing in remote work. How to get it back?
    * Try to recreate doing remote movie parties, jackbox party games
    * Intentionally bring people together for social activities
    * Over communicate
  * Remote work is isolated, mob programming adds a few more people but still does not capture co-located life. 
  * Remote lunchs
  * You have to be intentional with social hang outs

* Experiences with mob programming
  * https://fearlesschangepatterns.com/
  * Eliminate waste in the process because handoffs are significantly reduced
  * Large steps cost most because larger steps usually have more risk and so more work is put into mitigating that risk. 
  
  
