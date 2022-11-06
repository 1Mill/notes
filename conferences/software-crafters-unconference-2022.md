# Software Crafters Unconference 2022

<https://miro.com/app/board/uXjVPHkRum4=/>

## Key takways

* Influence organizational change through informal communication channels. Host informal "Dailies" or other low committment events with the intent of getting people together to share ideas. These ideas can be on technical practicies, software design patterns, or anything that is relevant to your organization.

* When trying to experiment with a new practice, seek out others who would enjoy failing at that practice with the intent to learn. What people enjoy failing at, and learning from, is different from person to person. So when you want to experiment with something new, over communicate your intent to gauge interest and alignment on what you hope to learn.

* Once a new practice is showing promise, Diffusion of Innovation Theory suggest courting early adopters in leadership positions to evangelize and create success stories. Success stories encourage further adoption. To court early adopters, your new practice needs how-to guides.

* Mob / ensemble programming is a powerful practice because it reduces waste across the board. One example is PRs. PRs traditionally serve as a gatekeeper to enforce software design, architecture, code readability, and other in-house technical practicies in an async fashion. This async fashion inflates WIP limits because the delay of feedback encourages people to start new, less important work. Mobbing produces the same outcomes of traditional async PRs but without delay, without context switching, and with a focus on done over started.

* Borning infastructure lets developers focus on producing customer value over managing complex infastructure. Boring infastructure is best characterised by is simplicity to adopt, maintain, and deploy to by developers. Infastructure as code tools like Terraform make infastructure less mystical. Sometimes it also makes sense to have a dedicated infastructure / OPs team to make complex infastructure simpler for others. Also, the type of infastructure you have says a lot about your organization's structure (i.e. Conway's Law). But rarely is innovative infastructure (e.g. K8) a differentiator in producing customer value, particularly for startups.

* Estimates are just (hopefully informed) guesses that should not be treated as promises or plugged into any `F(S-X) -> D` functions where `S` is scope, `X` is removed scope, and `D` is a deadline with any sense of certainty. Sometimes deadlines are real. But real deadlines should only be communication with transparency and an explination of the opportunity the business is trying not to miss.

* When mobbing / ensambleing, take a break every hour. This will help keep people focused. Also, have retrospectives just as regularly; experiment for best results: every mob is different.

* In remote-first orgs, you have to be extremely intentional to build social connections with peers when compaired to co-located organizations. This means deliberately plannings hang outs, 1-1s, clubs events, etc. to build social connections. Social connections drive psychological saftey so that people can safely share feedback, ideas, fail, learn, and navigate difficult conversations within the organization.

## Notes

* Spreading technical practicies
  * <https://sammancoaching.org/>
    * Dedicated learning hours
    * Two phases: (1) expert presents on a good technical practice and then (2) ensemble / mobs works with expert to practice this technical practice in code (akin to Kata)
  * Hunter Industries has 7 dedicated learning hours per week.
    * Use Microsoft Teams to host group learning sessions - like Katas on design patterns.
    * Hunter Industries is an innovator in agile practicies
  * Found success with regular Katas to level up everybody in the organization
  * Find a piece of legacy to refactor as a mob on a regular basis to (1) share knowledge on how the code works and (2) establish software design patterns like a Kata.
    * One person did it 15 minutes every day and recorded the session to build a repository of practicies to reference in the future
  * If you teach something, you learn it better
  * Weekly mob refactor on production code
  * Stuggle to communicate practicies between teams because every team is so siloed.
    * Remote work makes this even more difficult because less hallway conversations to get the bigger picture
    * <https://www.fluentcpp.com/2017/04/04/the-dailies-a-new-way-to-learn-at-work/> - host dailies to have conversations with others in the organization
      * Give a presentation once a day at the same time every day - be consistent and persistent!
      * Present for only 10 minutes. Everybody has 10 minutes to spare.
      * Keep it internal to the company; mission: "by people of the company, for people of the company"
      * Film and upload it. Making a transcript akin to a blog post also helps.
      * Rotate every month between every interested department.
      * Make as easy to follow for an audience.
      * Keep a theme for all dailies for that one month such as "Dailies C++", "Dailies Service Objects", Dailies Ruby", "Dailies ..." and only talk about that theme ever day for that 1 month period for that 1 department.
    * Not enough slack in the system to focus on anything except for output (e.g. coding features)
  * Diffusion of innovation theory
    * <https://sphweb.bumc.bu.edu/otlt/mph-modules/sb/behavioralchangetheories/behavioralchangetheories4.html>
    * 5 types of adopters
      1. Innovators - like to try new things / experiment
      2. Early adopters - leaders who embrase change opportunities. Need how-to manuals.
      3. Early majority - rarely leaders who embrase change. Need proof-of-concept to adaopt.
      4. Late majority - Skeptical of change. Need successful adoption stories.
      5. Laggards - Bound by tradition and very conservative. Need data and preasure from leaders.
    * Get buy-in from early adopters to then evangelize the practice to then effect change and build success stories.
    * <https://www.youtube.com/watch?v=yZzVzNovBNg>
      * Innovation is the bleeding edge - lots of experiments, early adopters like some stability before adoption
      * Everybody is an innovator in some cases and a laggard in others
      * If you are defensive about a practice, you are thinking about it the wrong way. Get people who want to participate to join to prove it out - lead by example, don't force it.
      * Don't try boiling the ocean to change everybody
  * <https://wallabyjs.com/> - get faster feedback on JS tests
  * "Never stop learning" - Art Bergquist

* What practicies are "non-negotiable" at various org scales?
  * CICD
  * Infastructure as Code so that you can focus on business value rather than taking care of pet infastructure
    * Pets versus cattle infastructure. Pets you have to take care of, cattle are more "replacable".
    * Terraform
  * Running tests as part of CICD so that tests never diverge from intended system behavior.
  * Automation can be expensive (e.g. running preview / staging environments), so find that balance between when it is or is not needed. Be sure everybody in the org is on the same page to keep costs down!
  * 7 CTOs - <https://7ctos.com/>
    * Trunk based development (i.e. no PRs reviews, straight to main) is a fundemental requirement
      * Need more context: what else is required like TDD, mob programming, etc. to hedge against broken code?
  * What is the value of PRs? Burocracy, control, or that the code is reviewed and knowledge is shared?
    * Mobbing eliminates the need for async reviews and knowledge is shared instantaneously because everybody is working in the same context.
    * What value is being produced by the PR process?
    * You can add multiple authors to commits in Git if tracking work history is valuable to organization
    * MobShell.sh - <https://mob.sh/>, does git handoffs using a temporary branch. Adds all authors on merge.
  * TDD
    * Useful for preventing regressions
    * TDD is a design tool
      * -> Michael Feathers: if something is difficult to test then that is likely a software design issue. Listen to the feedback your test is giving you and break it down into smaller problems that are hopefully easier to test.
    * Useful for tackling legacy code in terms of understanding how it works and how to safely refactor it.
    * Approval testing
      * <https://www.youtube.com/watch?v=fCyu2ebXA8o>
      * <https://approvaltests.com/>
      * <https://github.com/approvals/Approvals.NodeJS>
    * Working effectively with legacy code - <https://www.amazon.com/Working-Effectively-Legacy-Michael-Feathers/dp/0131177052>
  * Sometimes you have to clean the campground without cleaning the entire forest. Focus on refactoring the immediately important stuff to continoue deliver customer value.
  * People really like JetBrains
  * Small steps with Source Control
    * 2 minute Kata: every 2 minutes commit if tests pass or revert - forces you to really break down problems

* Driving change from below
  * Artificial deadlines promote cutting corners - every organization runs into this same problem
  * How do you communicate the impact of technical debt on flow?
    * Create working agreements: every 2 feature tickets is 1 technical debt ticket
    * As you cook dinner you are making a mess, if you clean as you go it doesn't look messey. If you don't clean, eventually you are forced to clean and stop all cooking.
    * A fear of stakeholders is that a focus on refactoring will stop outputtings.
      * -> Fred George: Some organizations see that a focus on technical excellence (ruthless refactoring) allows organizations to move and deliver faster.
    * Bugs take away from outputting / inhibit flow but that impact is rarely measured.
  * Need regression level testing so that corner cutting doesn't break existing features
  * "Microservices are like agile: it doesn't solve problems but reveals them more quickly." - Dave Adsit
  * How do you change the initera of the past?
    * Lead through example to demonstrate what change looks like and how they improve KPIs - a lighthouse team.
    * Share ideas through informal channels (e.g. learning sessions, paired programming, be in the same room together)
  * Working in a collaborative open space is better than in isolated spaces
    * Open office concepts do not mean collaborative. You need to be having meaningful and productive conversations.
  * If the team supports remote working, then the entire team should be remote. Hybrid in-person and remote meetings are clunky (e.g. table phones rarely work well, remote works cut out from side conversations).

* Microservice architectures
  * Use shared library to standardize communication between microservices which includes logging, etc.
  * Each microservice is a cell in an organization. Each cell is connected to the central nervous system but reacts differently.
    * How do we do sync and async requests for every microservice? Need to be the same for every microservice.

* How do you remote mob?
  * Agree on core working hours where everybody is online at the same time
  * Do not create PRs outside of the mob, use that time for investigating but not comitting to decisions. Discuss and commit as a mob / team only.
  * Do a break about every hour, mini retros just as frequently (experiment to find what works best)
    * Retro question: "What good can we turn up?"
    * Mobster timer - <http://mobster.cc/>
    * Everyone should feel safe enough to take breaks
  Mobbing tools:
    * <https://mob.sh/>
    * <https://mobti.me/>
    * <https://pop.com/>
  * One year of Remote Mob Programming - <https://www.youtube.com/watch?v=2jxO8RYvmso>, <https://www.agilealliance.org/resources/experience-reports/one-year-of-remote-mob-programming/>
  * Try to build a culture of Open Space concepts for mobbing.
    * Whomever is present is the right people.
  * How to counter act "divide and conquere" mentality with the intent of siloing work?
    * Some people prefer to work solo
    * Divide and conquer does not mean divide people but instead divide problems
      * Run multiple mobs around those smaller problems.
        * -> FLUID Scrum, FAST Agile
      * A single person dividing their attention on multiple problems is a war on all fronts - not divide and conquering
  * Cycling between solo and mobbing is an akward state to navigate because of the uncertainty around when either is appropriate.
    * Uncertain working agreements.
    * Commit to one.
  * The cost of communication is significantly reduced when everybody is in the same "room" / mob because people are constantly have conversations on everything form software design to functionality.
  * How do you find core working hours when people have different scheduled (e.g. pick kids up from school, morning birds, night owls, etc.)
    * Morning birds and night owls find overlap time everyday to transition mob from morning to night crew. Works also for international teams.
      * Acts as handover to discuss decisions or discoveres that were made.
    * Whoever is present are the right people to keep things flexible
    * Do a write up at the end of the day to facilitate async hand off for the next mob or your future self.
  * As part of mini retro when closing out the mob: "Where do we pick up next?"
  * "If you can only pick 1 agile practice make it retro spectives so you can improve"

* Simulators over mocks + contract testing
  * Test the flow of data through the system
  * Do not write tests for things in the middle - test inputs and outputs.
  * Mock external APIs, not middle-man classes.
    * When we call `Rudderstack.track()`, test that that the Rudderstack API is called.

* Boring infrastructure
  * Infastructure is not a differentiator in business
  * Wardley mapping - <https://learnwardleymapping.com/landscape/>
    * K8 and VM are product space, Serverless in Commodity space
    * <https://twitter.com/swardley/status/1376930531976306699?lang=en>
  * Docker containers make it easier to manage infastructure
    * Don't have to worry about what package is running in production versus development
  * K8 is the new legacy software, serverless is argued to be the new standard
    * -> I definitely agree haha - severless, plug-and-play vendors for the win; more and more offerings every day from databases, event streams, etc. Just need a serverless orchistrator... (AWS Step Functions are clunky)
  * Severs as pets to servers as cattle metaphore to describe infastructure
    * Infastructure as code (cattle) affords different deployment strategies than manual provisioning and manual maintinance (pet)
  * Most K8 Docker containers have known vulnerability because building the docker container is a developer problem and developers typically don't handle security updates until there is a problem.
  * <https://www.npmjs.com/package/forever> restarts node on any sort or error
  * <https://www.cloudfoundry.org/>
    * Makes developers jobs very easy
    * Top down driven (K8 is bottom up)
    * Small number of OPs people to manage
  * Borning infastructure lets developers focus on customer value versus managing infastructure.
  * <https://aws.amazon.com/ecs/>
  * <https://netflix.github.io/chaosmonkey/>
    * Build resilience through terminating instances in production to ensure code works as expected (nothing should be to big to fail)
  * Developers get paid for delivering customer value and only get punished for security flaws. Punishment is infrequent and therefore there is little incentive to be proactive about.
    * Very similar argument for technical debt
  * The type of deployment strategy an organization has is reflective of its cultural practices
  * "Rent an OPs" is a growing trend since maintaining an OPs team is expensive
  * OPs is all about firefighting and improving infastructure
  * Borning does not mean primative
    * Focus seems to be a simplicity, more turn-key, more plug-and-play
  * Google has a philosophy that they won't do anything that requires a help desk, they out-source all of that to 3rd parties, which makes GCP difficult to user (definitely agree by my experience)

* Communicating technical debt
  * 1-5 stars of technical debt per story / ticket
  * <https://www.youtube.com/watch?v=TQ9rng6YFeY&ab_channel=DevTernityConference>
  * Trust influence loop: (1) build trust, (2) influence change, (3) repeat
  * Quality Views by Colin Breck

* Software developer habits
  * <https://jamesclear.com/habits> - The Habits Guide: How to Build Good Habits and Break Bad Ones
  * <https://retrotool.io/> - <https://retrotool.io/p_VwOMfEUZZXcrCdsRi9P>
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
    * Giving fixed timelines because usually other stuff comes up that pushes those timelines out
    * Waiting to long to get feedback on anything
    * Not being conscientious of terminology, initialisms, etc. - try to make sure everybody is on the same page when having a conversation
    * Big commits - bigger risks
    * Not taking breaks, walking away from the computer, to process through problems
    * Not running tests before pushing
    * Status meetings - status should be viewable through tool (e.g. JIRA)
    * Blaming - people do the best with the knowledge they have at the time
    * Large batches
    * No WIP
    * Estimations - the act of estimations is waste, you never know what is going to come up between now and done
      * Estimates are just (informed) guess that people take to seriously
      * Estimates should not be treated as a promise
      * Estimates traditionally translate into some sort of scope + date calculation
        * What day (Y) will we have feature X (scope)?
        * If we eliminate requirements Z, can get get feature (X-Z) by date Y?
      * Work on the most valuable stuff first, pivot only when it is done or becomes not the most valuable.
      * Agile product developmen fits more into a Kanban style than a Waterfall style (e.g. Scrum)
    * Not asking clarifiying questions
    * Ignoring failing tests
    * Conflating "refactoring" with "rewriting" - refactoring means it does not change the current behavior
    * Creating complex solutions when simple ones suffice
  * Desired habits
    * Continous retros
      * Do retros very frequently and regularly
      * Some people do multiple retros a day (works best when mobbing)
      * The most important thing is addressing (1) what is not working and (2) amplifying what is working
      * Add ideas to retro board async as ideas are generated rather than trying to remember them all in the moment
      * Give feedback at the right time - training a pet requires instant feedback to relate action to consequence.
      * "I have this feeling about this ..."
    * Having difficult conversations
      * Use a friend (somebody with psychological saftey, trust) to moderate
      * Use Situation Behavior Impact (SBI) to help frame the conversations to make it more productive
    * Thin slicing feateures
    * Giving better feedback
    * Fearlessly examining our ways of working to find improvements - fearless experimentaion
    * Learn as a team
    * Batching questions for team lead / product owner

* Why can't we have nice things?
  * Limiting WIP forces the team to focus on delivery versus the number of incomplete things - done is better than started
  * Async PRs increase WIP because of queueing and delays between feedback and reaction
    * Mob programming eliminates async PRs - they happen sync
    * Permit people to merge straight into main
  * Mob programming
    * <https://collaboration.csc.ncsu.edu/laurie/Papers/ieeeSoftware.PDF>
  * <https://www.amazon.com/Nine-Lies-about-Work-Freethinking-ebook/dp/B07C3ZT28C>
    * Best way to evaluate employees is to ask employees "who would you want to work with on a critical project?"

* Overcoming communication barriers with remote work
  * Try to schedule messages, emails, etc. for the person's working hours
  * The larger the power differential, the more cautious you need to be with when you send things. If the CEO sends you a message at 9pm you might feel the need to reply versus a peer because you value the CEO's time more than your own: you don't want to be a blocker.
  * Social connection is difficult and different in fully remote life
  * Timezone (e.g. east vs west coast) and lifestyle differences (e.g. picking up children from school) are a challange when trying to establish core working hours
  * Lots of channels to monitor (e.g. email, slack, meetings, calls, etc.)
  * Cross pollination from co-located teams is missing in remote work. How to get it back?
    * Try to recreate doing remote movie parties, jackbox party games
    * Intentionally bring people together for social activities
    * Over communicate
  * Remote work is isolated, mob programming adds a few more people but still does not capture co-located life.
  * Remote lunches
  * You have to be intentional with social hang outs

* Experiences with mob programming
  * <https://fearlesschangepatterns.com/>
  * Eliminate waste in the process because handoffs are significantly reduced
  * Large steps cost most because larger steps usually have more risk and so more work is put into mitigating that risk (e.g. manual QA).

* Closing circle
  * People like eye-candy, translate your proposal or innovation into something that is catchy and gets people interested
  * We can always iterate on anything
  * Facilitate inclusion by getting everybody involved in the conversation
