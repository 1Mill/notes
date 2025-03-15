# Agile Open Northwest 2025

LINK

## Key Takeaways

* TODO

## Notes

### Opening Circle - Day 1

* You have to be efficient before you can be effective; get good at doing and then working doing the right thing. Make feedback loops as cost effective as possible.
* What are super connectors? Why are they important and how to support?
* Arlos committ notation - <https://github.com/RefactoringCombos/ArlosCommitNotation>; used to annotate commits for easy scanability in the history and encourage tiny commits
* Don't set yourself on fire to keep others warm; put on your own mask first before helping others with theirs on an airplane.
Utilize FizzBuzz to learn new languages.

### MicroObjects

* Author: Quin Gill
* 75% more productive than other teams not using MicroObjects pattern
* Have to apply rigously, if you falter lose all the benefits
* No Enums
* No primatives (e.g. no null, no string, no integrate) - everything is a domain object and the primitive is just an implementation detail of the data layer within the domain (e.g. `age` could be a float, string, number, etc. depending on how that domain wanted to implement it)
  * A password shouldn't support `.uppercase`
  * An ID shouldn't support `+`
  * Primities leak functionality into domain objects which makes them more difficult to work with
* Domains objects are the what, the data / primitives are just the how (i.e. an private implementation detail)
* Similar to SmallTalk Style, emphazises functional programming practices
* No getters, no setters
  * Gettings are often used to measure and then answer a question - instead make that question and interface which returns an answer on the domain object
  * Accept questions, return answers
  * Don't let other people reach into your data layer
* Services ending in "-er" or "-or" know too much about another class - refactor or bring into domain object (e.g. validator, manager)

### IC to EM

* As an IC (individual contributor), you foucs on one (i.e. yourself); as an EM (engineering manager), you focus on many
* Being a good IC does not mean you will be a good EM, they require different skill sets and focuses

* Book: It is the manager
* Book: Connect to the manager
  * EM focus on career growth of others, being a connector, not doing the work itself - manage the people and environment for those doing the work
  * How to listen
  * How to give feedback
  * Point direct reports in the right direction, do not give solutions so they can grow / learn / try new things
* Be coachable and know how to coach, bring the ___ (indecipherable)
* Have a wide perspective to see patterns across the org, don't be the tech lead
* Third level listening: knowing what is and what is not being said in a conversation
* Managers need different skills than IC
* Book: One To Many training
  * Talk less, ask more questions
* Bad managers often fallback to technical requirements / task management than career development
* EM must delegate work so people can grow
* Feedback if factual and outcome based
* EM shouldn't know how to do it better than the team
  * Hire smart people, get out of their way
  * Shouldn't be as familiar with the code as ICs because they should be focused elsewhere
* "What can I do to make your job easier?" - Mary
* EM should focus on the work an IC cannot do
* EM represent the company to ICs - so make sure what you say is consistent and aligned with the organization so there is less chance for miscommunication.

* Leadership is measured by looking at the quality of the practice exhibited by those around directly or indirectly around them./
* Leadership is all about facilitating the (ideally effective) outputs of others

* Build relationships to widen perview - strive to become a superconnector.
* Invite in support / growth in others - "I am going to work on X, want to join?"
  * Be intentional to invite others in, as others won't ask for social or other reasons much of the time.
* For delegation, there is a difference between "I can't ..." vs "I don't want ..."
  * "I can't ..." means a lack of capacity / capability
  * "I don't ..." means control - which an EM should strive to avoid
* Know boots on the ground / ICs, ensure they know what is expected but do not instruct how they should do it
* EM should be focused on business outcomes, not sweating the small IC details, coding styles, etc.
* "Can I make it not harder for IC to do their jobs?"
* Create opportunities for people to try in a safe way (e.g. spike early on whan cheap to fail / try something different)

### Brain as a battery

* Use pomodoro for focus work as timeboxes to reevaluate and look at what the next more valuable thing to do is
* Don't use pomodoro for non-focus work - just do that work until it is done
* Remain teachable

### The forest and the desert

* Innovator Accounting: a system for measuring and tracking the performance of innovation initiatives, particularly in early stages when traditional financial metrics (like revenue, ROI, and market share) are not yet relevant. It's about understanding the value creation potential of new ideas and projects.
* Meet people where they are
  * How to people like to learn? Email, book, article podcast?
  * What do people trust? Certain organizations, certain people?

### Lunch - Day 1

* Book: 2 Second Lean
* Ice breakers must serer a purpose and explian that to participants
* Reference: Liberating Structures (e.g. 1-2-4-all)

### What is in a name?

* Rename a variable any time a better name is discovered
* Names communicate intent and understanding
* Help reduce cognitive load
* Bad names are misleading, which then grows cognitive load because we hold that gotcha in working memory

* Tips and tricks
  * Look for cognitive dissonence - where things don't line up
  * Avoid duplication of names when they mean different things
  * Look for near duplicatoin for hidden domain models (e.g. HTTPClient.send, WSClient.send -> Client(config).send; Resume.upload, Picture.upload -> File.upload(document))
* Reference: 7 stages of naming (Arlo Belshee)
  1. Missing
  2. Nonsense
  3. Honest
  4. Honest & complete
  5. Does the right thing
  6. Intent
  7. Domain Abstraction
* Names are emergent - give it the best name you can right now at this moment and rename as new insights are discovered / learned.

* Provessional naming (best name at the moment), but frequently iterations
  * Start with Foo and see how things evolve
* Don't be procedural with the name, describe the domain
* Short names are better, but meaning is more valuable than vaguness
* If you are needing a prefix to differentiate actions there may be a hidden abstraction (e.g. HTTPClient, WSClient -> Client(config))
* Prefixes may be better communicated via foldering or other abstractions (e.g. HTTPClient -> /clients/http)

* Strive to avoid using comments, instead, strive to make the code say what the comment would have said

* For boolean values, prefix with `is`, `has`, etc. to make it clear it is a Boolean

* Be consistent

* Don't name classes ending in `-er` or `-or` (e.g. `MyDomainManager`, `MyClassValidator`) because it means the class is too tightly coupled to some other domain model it doesn't control.
* Okay to have tightly coupled transformation layers (e.g. `DomainA` -> `TransformationAToB` -> `DomainB`)
* Use the domain language to make classes
  * Represent the domain concept as an object in the code.
  * Use the language the customer uses
* Avoid over generalizing or premature naming - start specific and let generalizations emerge (if needed at all)

* Public Interfaces (e.g. APIs, modules, etc.) can randomly change, so try to future proof with reasonable constraints

### Super connectors

* People connect people to other people to drive effectiveness (doing and building the righ thing) through collaboration
* Super connectors (SC) are an informal role
* SC are often the glue which keeps the team or project together
* SC thrive from community building, which in turn builds strong informal working relationships
* Book: Developer Hegemony
  * Working outside of your role is a risky, but more risk more reward, so may be a way of getting ahead instead of focusing on normally assigned work.
* Know what is going on across the org to centralize decision making or reuse existing solutions - very context dependent.
* SC are effective, even if not playing by the book - they are very pragmatic
* Want to help, so many take on too much work trying to help others
* SC enjoy community / connecting with other SC so they can work together instead of in isolation
  * SC often don't know other SC at work
* SC are culture carriers, so great for onboarding new folks and leveraging to change company culture
* Reference: Social Resume
  * Strength of relationships
  * Connecting people to make them more efficient
* Ask people "Who do y ou go to for X?" to try and discover SC
* SC are often SC in work and in life outside of work

* "Not my job" is not something a SC says frequently
* SC are known as the "fixer" - the person who knows how to get something done
* Book: Peopleware

### Micro-kickoffs, micro-retros, and learning loops

* Micro-kikoffs
  * What were we last doing?
  * What problem were we trying to solve?
  * What was the very next step?
* Micro-retros
  * What did we notice?
  * TRIPE: Tools, Resources, Interactions, Processes, and Environment

* Mobbing (3+ people) emphasize bottlenecks because of reduced WIP
* Devil's Pom Poms: Skip retro because we are already good enough or didn't notice anything we could do better.

### Couching four sustainability

* You must demonstrate your value tot he company via transparency and advocacy - metrics help a lot
* Key metrics to communicate
  1. Cycle time
  2. Defects count
  3. Team happiness
  4. Planned to done (delivery time)

* People willingly and wantingly join good working environments - so make working environment great to attract and retain people.
* Build systems and culture so you can eventually leave / retire
* Ask emotional questions to get emotional answers, then ask "Why?" to get at how to fix, change, enhance, etc.

### Closing Circle - Day 1

* Good to hear other people having the same problems and sharing their experiences trying to or solving the problem
* Good to get feedback / validation that others are thinking in the same direction or running into the same problems across the industry
* 3 presentation styles
  1. Expert -> Learner (coaching model)
  2. Conversation (facilitator, casual)
  3. Experience (game)
* "Many impossible choices" is a good sign of good topics in a Open Space marketplace

### Board Game Design

* Get something physical, not just theory, to get a real feel for what works and what doesn't work
* Listen to fedback, but ignore solutions - solve your own way
* Feedback, feedback, feedback (!!!) is critical to good game (and product) design
* Find the core "fun", and then add on layers of complexity from there

### FizzBuzz

* Cognitive load of else vs early returns
* Use FizzBuzz, a familiar and easy problem, to learn new things - too often people try learning too many new things at once (e.g. new code, new framework, new problem) which makes learning slow and difficult.

### Lean Coffee - Day 2

* Book: Tiny Habits
* Book: Atomic Habits
* Changing clothes for start vs end of work is like a "communite" for remote workers to help turn brain off from work mode.

### Opening Circle - Day 2

* Book: How to solve it?
* Habits is how you change, and people may follow which is how you influence without authority
* Reference: Windlow's Awww Research
* How do we get more people involved in Open Space?
* Deployment pipeline Inverse Conway Menuver - If Team A is blocked by Team B's deployment pipeline, then Team A must conform to Team B or build their own.

### Built in Quality

* Quality of the process pedicts quality of the product
* Don't focus on mass inspection in hightsight, build quality upfront into practicies

* TDD doesn't just have to be unit tests, it can be accessibility, end-to-end, contracts, etc.

* Waste a lot of time mass inspecting at the end vs doing it as part of the development process.
* Integration tests ar emore valuable then unit tests because they test the product expierence from a customers perspective, so integration gaps are less likely to happen
  * Can a customer purchase something on an e-commerce product page?
  * Can a customer log in successfully?

* Focus on quality of delivery to make great work inevibitle
* High trust and high skilled people

### Random note

* Familiarity creates space for psychological safety

### The wisdom of the clown

* Humor is a good way to connect
* Avoid mean jokes as it makes people feel unsafe because they may be the next target and so act defensive
  * What is considered "mean" varies group to group
* Clowns can ware many faces to adapt to people

### Career rough road

* Careers require a plan / path outline so you can check in to know if you are heading in the right direction, have the right support, resources, etc.
* Connections / networking / community building are valuable for finding new or hidden opportunities
  * Others know if your grabbag of skills would be a good fit
  * Use LinkedIn to find 2nd degree connections to get a leg up / foot in the door
* Always be building community - not networking
  * Be mutually beneficial
  * Have shared passions, interests, etc.
* Be introspective
  * What recharges your battery? Look for opportunities, communities, etc. which leverage those recharges
* Book: Squiggly careers
  * Strengths give energy, weaknesses drain energy
* Find / pair with those who complement your weaknesses - pairing career trails
* What problems need interactive solutions? Many product minded people may have many transferable skills to other areas outside of online products (e.g. board games)

### Facilitation dojo

* Be adaptible vs following a plan when facilitating
* Have an outcome of the facilitation in mind
* Try to get everybody learning / participating in the same space / collaboratively
* Difficulties
  * Getting people to participate
  * People disengaged
* What you hope participations to do after the facilitation influences the type of structure, style, visuals, tools, etc. you should use
* Practicies
  * Orgnize around shared interests
  * Try something different, reframing

* Only things facilitator needs to know:
  1. Just the goal(s)
  2. Just the topic
  3. Just the working agreement
  4. Just the constraints
* Everybody should be participating in the facilitation to achieve the goal

### DevOps for dummies

* Create slack in the sytem for engineers to refactor before tech debt becomes an issue
* Best practicies
  * Automated and actionable alerts
  * Keep high performing teams together
  * Be patient with engineers - they are trying their best in the environment they are working in
  * Be able to deploy any time of the day - it is always middle-of-the-workday somewhere (at Disney)
* Give the team guidliness / goals, but don't dictate the how - make expectations clear and then get out of the way

* "If teams are given the opportunity, they will tell you where the friction is." - Former Disney EM
* Deploy during normal working day, not after hours, so if something goes wrong it is easy to fix because everybody is still there working.

### Open Space in Other Places

* Fast Agile
  * Marketplace is composed of all the work to be done
  * Leverages dynamic re-teaming via self-organization to ensure squads have right skills to get work done
* World Cafe
  * People rotate between tables and each table has a specific topic
* When is Open Space not a good fit?
  * When the group is too small - Lean Coffee may be a better fit
  * Too time constrainted (< 2 hours) - need enough time to build community

* Open Space Phases for Strategy Planning
  1. What do we see?
  2. From what we see, do we see any patterns?
  3. What do we need to change?
* This sounds very similar to [what-so-whate-now-what](https://www.liberatingstructures.com/9-what-so-what-now-what-w/) from Liberating Structures just in Open Space format

* Themse are important to make people feel invited and frame what the Open Space will be about.
* Make the theme comple interest but not overly structured in mind
* Find people who want to try something different as they are more likely to participate

* When running an Open Space, voting on topics is setting some people up for failure by design which may drive down participation of topic ideas
* Open Space is the default operating system unless prevented, often by some other social constructs.
* "Open space is the operating system of life"
* Reference: World Open Space on Open Space - <https://openspaceworld.org/wp2/>

### How to solve it?

* How to solve it framework:
  1. Understand or define the problem
  2. Devise a plan for a solutions
  3. Execute the plan
  4. Check if the solution works and reflect

* Questions to ask:
  * Do I have enough information?
  * How do I get more information?
  * Can I break it down into smaller problems?
  * Am I solving the real problem or a wishful problem?
  * How expensive is it to learn / go through a cycle?
  * What is the incentive or ROI to fix vs not fix?

### Inverse Conway Maneuver

* Conways Law: Your code reflects your organization.
* The more people in the know, the more chance for miscommunication

* "We have to talk to each other because you blocked the delivery pipeline"
* Team A owns the delivery pipeline, every other team is low priority customer
* If another team wants to deploy independent of Team A, build your own independent pipeline.
* Some important context is that each micro-frontend was rather independent already, so the Team A deployment pipeline was being used more because of initeria than necessity.

* Sometimes people get FOMO (fear of missing out) and so attend meetings / standups they don't need to be at causing communication complexity to grow
  * Define clear owners, have clear wedges between teams
* Teams owning their own deployment pipeline made it easier for them to deploy their own code
  * Faster bux fixes
  * Infastructure updates (e.g. React v1 vs v18)

* Being able to run experiments on your process is a sign of agility - foster a culture experimentation

* Hunter users micro-frontends so each prduct is sperate code bases that originally deployed through the monlith.

### Linking Technical Debt to Features

* As technical debt is created, create technical debt backlog items so that product and engineers are using the same language
* Link tech debt items to their feature areas
* Tech debt must be paid before continuing feature development in that area but it isn't prioritized until the feature is prioritized
* Add to backlog and link to feature to preserve historical context
* Helps visualize amount of tech debt in the system because it is in the backlog

### Developer Expeirence (DX)

* Big problem with legacy code at OpenSesame
* Try to improve in place, but Druple tightly coupled to database
  * 200 SQL quries run just to create a single user
* Need ability to safely and confidently refactor <- means need to be able to do TDD <- means need for 5 second feedback loops

* 3 areas of focus: bundle / build DX, pairing DX, deployment DX

* Build ([Automatopia](https://github.com/jamesshore/automatopia))
  * Automatically install most tools via script
  * Runs all tests automatically
  * Hot-rerun tests for files wich changes on file save because it looks at dependency tree
  * Reference: Argo Test Frameworking
  * Reference: [AvaJS](https://github.com/avajs/ava)
    * Has an API that is easy for other tools like Automatopia to hook into versus other libraries
  * Tests run fast (e.g. 10 tests -> 20ms)
  * Test success and failure play sound
    * Enable engineers to not have to visually look at test terminal: can just listen for success / failure like a video game

* Fast feedback
  * Fast tests
  * Test segmentation
  * No flaky test -> No uncertainty
  * Not touching database makes tests faster - James Shore uses [Nullable Pattern](https://www.jamesshore.com/v2/projects/nullables)
  * Get every developer the best hardware you can get
    * Faster is better, but expensive
    * How much is a dev second? Does that outweight cost of above expense? Often yes

* Pairing / Mobbing DX
  * Working in 15 minute commites on tasks branches (not feature branches)
  * Hand off -> commit to temp branch -> pick up on new computer

* Fast and deterministic builds more important than deploy
  * Deploy cant take a bit of time because it can happen in the background while developers do their work
  * Confidence contained from TDD
* Regulated to get 2 approvals
  * Use Git Signed committs to authenticate commits authors
  * Do sign-off commits as replacements for traditional PR approvals.
  * Can merge task branch to main only if last two commits are sign-off commits
  * Remote CI double checks build, commit signatures, etc. before deploy
  * Pair programming reduces PR wait to 0 seconds
* Do tiny commits, squashing just blows away information so don't do it
* Rolling forward on failure is easier with tiny commits because the surface area for trouble shooting is much smaller

* Reference: Test Nullable Strategy

### Closing Circle - Day 2

* Embrace the disruptors, don't manage them down
  * Often they need guard railes but highly motivated to do good and effective work
* Reference: [Liberating Structure](https://www.liberatingstructures.com/)
* Reference: AgileSEA on Slack

### Lean Coffee - Day 3

* As an experiment, collect all questions asked in a week, then look to automate these areas
* Make security a partner and teacher, not just an enforcer - help teams level up so they can self-manage.
  * Make security findings, not security blockers - not every security thing may be worth fixing immediately

### Opening Circle - Day 3

* Reference: Wardly mapping
* Reference: Liberating Structures
* Refernece: Hackathon for Social Good

### XP and Agile with a House

* Reference: Design Charrette
  * Phase 1: Sketch raw ideas on a shared sheet of paper
  * Phase 2: Sketch the best ideas / new ideas collaboratively on a new sheet of shared paper, write notes about why these are the best ideas
  * Phase 3: Refine sketches into something more practical
  * Phase N+: Continue phase 2 and 3 cycle until final design is completed
  * Creates a history of decisions you can look back up

* Wanted to build house out of COB (clay, straw, sand) so it is easy to refactor / change, but it easily disolved in water
* Can only be built in batches of 18 inches, which means every 18 inches a decision point around where to put a pipe, outlet, door, etc.

* While sketching the layout of the house, ask "What do I want to do here?"
  * Informs ammenitites, spaces, single purpose rooms (e.g. kitchen), multi-use rooms (e.g. dinner table is a bed), etc.
* Paper prototypes help understand spacing / room flow within structure foot print

* How do you keep independence with high cohesion? Have anchor points to orientate yourself. Need at least 3 anchor points.
  * 1 anchor point can be orientated form any direction
  * 2 anchor points can be orientated from only 2 directoins
  * 3+ anchor points can only be orientated in one direction

* What specifications must be tiple checks because they are critical? E.g. wrong trees chopped down because of miss communication.
* What backup plans do you have?
* Minimum viable documentation - proof you followed industriy standards in case anybody asks
* What areas can you resuse?
  * Dinner table: food, board games, sleeping space?

* What things prevent you from building? E.g. COB must try in heat, so can't build during the winter causing 6 month freeze in building time
* Worth doing something different to anti-freeze / avoid blockers?

### Open Space and Everything Else

* "What does everybody ohpe to get out of this session?"

* Reference: Fast Agile - leveraging Open Space to build and maintain multiple products efficiently
* Open Space Workshops
  * Employees choose skills to level up / participate with
  * Reference: [Wijnands Scrum in Education](https://scrumsummit.org/2020/speaker/willy-wijnands/)
  * Aunthonomy in educational pursuits helps drive participation

* Open Space is extremely social, builds trust between folks because of frequent social interactions

* Use Open Space for strategic planning sessions
* Do Open Space as a way to rapidaly share relevant information to team members (e.g. onboarding)
* Book: Open Space (Ownes)
* Book: Open Space Guide - 5 pages on how to run an Open Space
* Book: Open Space Agility Handbook - coming soon from April and Kilby

* Two part Open Spaces where part 1 is formulating experiments to run and part 2 is reporting back on those learning is critically effective.
  * People who participate in part 2 are probably emergent leaders
  * Have an outcome / experiment to run from part 1

* You need a reason to gather
  * Community buildling
  * Achieving a mission
  * Spreading information

* When running a session, pick one:
  * "I want to learn about ..."
  * "I want to teach about ..."
  * "I want to have a conversation with others about ..."
* New Open Space principle: "Every langauge is the right language."

* Must have management buy-in to hold the Open Space Container.
* To combat fearfullness with management:
  1. Build a theme
  2. Reeinforce reason for holding the Open Space
  3. Show and tell / demonstrate how to show up and support participants
* Figure out if Open Space is the right container
  * If you hold Open Space, and nother gets done, may hurt morale more than doing nothing

* Open Space is often very vulnerable for participants, so must get management buy-in
* Lean Coffee is a stepping stone to Open Space and doing Lean Coffee may help managers buy into the ideas of Open Space
* Not following up / following through with goals derived collaboratively from Open Space may do more harm than good

* What are the outcomes / goals form an Open Space?
  * Strategic -> Top 3 bets
  * Community -> More super connectors
  * Work -> More tasks completed because of efficiency gains
* Book: Dynamic Reteaming

* Trust but verify to make managers gain confidence and trust the Open Space process - did we really see performance improvements by adopting Fast Agile?

### Resilient High Performing Teams (RHPTs)

* Traits of RHPTs
  * Happy
  * Fast code delivery rate
  * Highly effective collaboration / flow
  * Psyhological safety
  * Autonomous
  * Stable container / buttle
    * Stable way of working
    * 2 people in mob level up new member

* Know what capabilities the people have (e.g. React, DB, etc.) and how to leverage that as a team to work effctively as a team to own a value stream.

* Reference: Discovery Trees
* How do orgs define high performance and how do we optimize our processes for those performance characteristics?
  * Lots of success with Fast Agile
* Work done must pay for itself unless an investment. Short vs long term investments have different break-even horizons but should be factored in

* Efficiency > Effectiveness - get very good at delivering the wrong then and then jump up a level to getting very good at discoverying the right bets
* Engineering hours > managers hours - engineers output tangible value, but managers like to optimize making their own work easier which often gets in the way of engineers doing
* Doing > talking about doing

* Every process is optimized for a who and what. Knowing the who and what can help understand or eliminate waste.
* Add rules for when meetings may be scheduled
  * Must have agenda
  * Must be more valuable then output work
  * Must visualize costs of process (e.g. if each engineer minute is $1, then a 1 hour meeting with 10 engineers is $600)
  * Must have an outcome and no stop time until outcome is achieved
    * Meeting take as much time as given, so start with 10 minutes and every 10 minutes to thumbs up or down to continue

* Working agreement
  * Core hours
  * Heads down hours / focus hours
  * Learning hours
  * Experimentation hours
* Continous improvement hours (e.g. learning hours) are seperate hours from delivery hours so they happen regularly - not occassionally.

* Make environments
  * Safe to fail
  * Build slack into the delivery system so the system can easily absorb the unexpected / unplanned
  * Teams are self-sufficent
  * Has a super connection on the team to get the right pulse of the org and reusing existing solutions when appropriate
  * Work goes to a team, not a person

### Lunch - Day 3

* Book: The Hard Thing About Hard Things
