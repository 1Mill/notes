# An Elegant Puzzle: Systems of Software Engineering Management

## Article

Culture and software craftsmanship are the levers to effective leadership. In "An Elegant Puzzle", author Will Larson shares his learnings from Uber and Stripe. Hypergrowth startups where he discovered the importance of metrics, opinionated policies, and peer-first learning to achieve business outcomes. Characteristics cultured by engineering leaders that align people and code with goals. Goals that afford business agility for long term business success.

### Leading through metrics

Metrics generated by goals are the cornerstone of effective leadership. Metrics make organizational flows measurable and cause-and-effect known. To improve the flow of work, Larson recommends using investment goals. Investment goals are aspirational, answer the question "Where do we want to be?", and must come from first-principles. Investment goals demand experimentation with organizational policies, processes, or teams dynamics. To guard against undesired outcomes, Larson introduces baseline goals to counterbalance investment goals. Baseline goals answer the question "Where are we now?" to alert leaders to undesired regressive behavior. Using investment and baseline goals, leaders can drive behavioral changes that improve flow.

### Making change easy

After goal settings, Larson emphasizes the importance of leading by example. In his past, when leading without authority, Larson found success in

  1. Implementing a change within a single team
  2. Measuring the impact of that change on baseline and investment goals
  3. Model and document how another team may adopt that change into their own team
  4. Share the above with the wider organization

Decentralized leadership coupled with change evangelism encourages progressive organizational adoption. Meaning that teams will adopt changes if and when the team thinks those changes will improve their flow. However, Larson points out that not every change can be optional.

Writing new code is sometimes the only path forward when paying technical debt. For example, if a third-party API is being deprecated the only option is to replace it. To make technical migrations successful, Larson recommends organizations derisk and afford change by:

  1. Do user testing on engineering teams to discover common use cases
  2. Write how-to documentation that are searchable and easy to follow
  3. Always allow engineering to revert back to a working state

After establishing this new standard, Larson then enforces adoption through two new policies:

  1. Complete all new work using the new standard
  2. Prioritize "done"

Larson places special emphasis on the definition of "done" for technical migrations. According to Larson, "done" is the adoption of the new standard in the entire code base: even in old code. These migrations act to avoid the the real infrastructure and cognitive costs of competing standards. Costs that inhibit the flow of work.

### Use policies to focus

Larson views effective managers as those who write opinionated policies that focus people. From a pragmatic perspective, concrete policies solve problems to prevent personal interruptions. Likewise, concrete policies avoid real (or perceived) bias in value judgements. Like goals, policies serve to focus people on the companies current strategy. More so than goals, policies must be more frequently reevaluated to ensure they are having the desired impact. Larson recommends collecting any policy exceptions to make informed policy changes. An old or bad policy left unchecked may artificially impede the flow of work.

### Culture of learning

A focus on short-term value usually leads to specialists who are a single point of failure. Specialists act as a silo of knowledge

---

One policy recommended by Larson is to avoid specialists. Specialists are a single point of failure that manifest themselves in cultures that prioritize short-term individual value over long-term team growth. Larson suggests establishing a culture of peer-first learning. A growth mindset that avoids siloing knowledge through specialization. As a manager, Larson recommend pairing junior and senior in roles together to facilitate that learning and knowledge transfer. Larson also recommend focusing on succession planning so that managers are actively working to be replaced, ideally as they are being promoted in the organization.

### Improving flow

Keep innovation and technical debt as 1 team
Systems are usually self-healing: look for slow downs or bottle necks to determin where to otpimize your flow
You only get value when something is finished.
Organizational debt, like technical debt, eixts from old/legacy processes that limit flow.
Succession planning is important for long term organizational success
Migrations are often the only meaningful solutions to debt
Make technical migrations and people reorganizations cheap for long term organizational success and market fit.
Do not optimize for the individual - they are a single point of culture
Accidental versus essential complexity

### Peer-first learning

High performing teams know how to best elevate each other skills
Gelling factor
De cenralize decisoing making
Build sociall networks
Culture only changes through persistent and consistent effort
foster a culture of growth in others

## Key takways

Larson suggest that for any system, keep the responsibility of innovation (e.g. features) and technical debt (e.g. bugs) the responsibility of a single team. This will avoid the creation of a two class culture in which one class builds new things and then throws those things over a wall for the other class to maintain.

You only get value when something is finished.

Organizational debt exists from old/legacy processes and limit value flow.

Model the product development lifecycle from team structures to code reviews in order to discover bottle necks or other flow limiters.

There are 2 types of goals: investement goals and baseline goals. Both types of goals are measurable. But investements goals answer the question "where do we want to be?" and should be limited to 3. Whereas baseline goals ask "where are we now?" to guard against regressive behavior.

Migrations are often the only meaningful solutions to technical debt.

Making technical migrations and reorganizing people cheap is the key to long term organizational growth and market fit.

Do not prioritize the individual - individuals are single points of failure.

People do not process information well in large groups. Break large groups into smaller groups to gain more meaingful insight or feedback.

To lead without authority: (1) measure, (2) model, (3) document, and (4) share how your recommended improvement impacted yourself or your team.

Focus on building a learning community with peers by facilitating conversations to nuture long-term relationships.

Culture is only changed through persistent and consistent effort.

You cannot improve a flow without being able to observe and measure it.

Remove accidental complexity from bad code, process, team, etc. design so that everybody can focus on essential complexity found in the economic market.

## All notes

* Manager should support at most 6 - 8 engineers
* **Keep innovation and technical debt (e.g. bugs) as 1 team**
  * Avoid 2 teired system by keeping innovationg and learning in the same team
* High performing teams know how to best elevate each other skills
  * I speculate this is from strong social connections and established psychological saftey
* "Gelling factor": How people learn to work with each other
  * Takes time to adjust / create
* Systems are usually self healing
  * A database slows down
  * People take more time on tasks
* **You only get value when something is finished**
* Write discoverable documentation
* Do not write code that enforces policies to keep code flexible for as long as possible in the future
* Avoid gatekeeping as much as possible as to not inhibit innovation
* **Organizational debt exists from old/legacy processes that impede value flow**
* Succession planning is important for long term success of an organization
  * Create list of high to low risk areas that you do and work one-by-one to elimintate
* Leaders act like glue when gaps form in the system
  * I assume this is more based on credibility in horizontal or formal authority in heriartical structures
* Measurements
  * Label every flow (rate)
  * Label every stock (quantity)
* **Model systems from code reviews to team structures to value streams to find out where the blottle necks / blockers / flow limiters are**
* Stratagies: Grounded documents that outline the actions and tradeoffs to address a specific challange
* Visions: Aspirational documents taht enable people who do not work closey together to make decisions that fit together
* Recommended reading: [Nudge](https://www.amazon.com/Nudge-Improving-Decisions-Health-Happiness/dp/014311526X); [Good Stratagies and Bad Stratagies](https://www.amazon.com/Good-Strategy-Bad-Strategy-audiobook/dp/B07R6XQ8YP)
* How to write stratagies:
  1. Problem statement
  2. Identify policies
  3. Guiding actions (focus on X at the dismay of Y)
* Visions
  * Allow distributed coordination with little overhead communication costs
  * Reiterate constantly to reinforce and cut through communcation noise
  * Include value proposition/impact on end users
  * Use present tense
  * Write simply: no buzz words
* **Goals**
  * Investement goals: where do you want to be?
    * Limit to 3
  * Baseline goals: where are we currently so that we do not regress?
* **Migrations are often the only meannigful solutions to technical debt.**
  1. Derisk migration
  2. Enable/afford through ...
      * Good documentation
      * Automate as much as possible
      * Always revertable to working state
  3. Finish the migration with 100% adoption
      * Stop the bleeding by enforcing new standard/policy for new work
      * Prioritize finishing the migration
* **Making technical migrations and reorganizing people cheap is the key to long term organizational growth and market fit**
* Put teams as close together as possible to facilitate shared context
  * Most poor relationships are information gaps that can be fixed with closer proximity
* **Do not optimize for the individual - individuals are single points of failure**
* **People do not process well in large groups - break into smaller groups (e.g. one-on-ones) for more meaningful feedback**
* Career narratives: How you can facilitate career growth in others
  * Discover the intersection of business value and personal passion
* **Model, document, and share to lead without authoirty**
  1. Build metrics to measure change
  2. Do personally / at the team level (experiment)
  3. Document how another team could adopt this process
  4. Share to the wider organization
* Decentralized decision making but create centralized advisory groups for consistancy across the organization (e.g. Node vs Python)
  * Watch out for status hunters, bottlenecks, etc. that may artifically limit flow
* When giving a presentation start with the conclusion
  * Frame the topic with relavant and short historical context
  * Derive actions from principles and know your data for adhoc questions
  * Preparing (understanding) > practice (parroting)
  * Steps
      1. Tie topic to business value (1-2 sentences)
      2. Establish historical narrative (2-4)
      3. Explicit ask (1-2)
      4. Data driven diagnosis
      5. Decision making principles
      6. What next and when it will be done
      7. Return to explicit ask
* In time mangement, always prioritize long term success
* **Focus on building a learning community with peers**
  * Be a facilitator not lecturer
  * Short presentations with long discussions
  * Break out groups vs large groups
* Exceptions to policies are bias and inefficient: keep consistent
* Good policies are opinionated and constrain behavior
* Norms inform behavior, policies enforce it
* Consistently enforce policy constraints
* Use requested policy exceptions to inform and rethink policy
* Commit to reevaluating policy at regular inervals (e.g. X weeks)
* Do the hard thing now, do not postpone it
* Build social networks to get work done effectively
* Authority is a weak way to work that limits innovation and is usually far from the information
* Prioritize your time to work on impactful things and not things that just show up on your calendar
* Professional growth comes from scope of work being done in the orgnization, not the number of people reporting to you
  * Look for gaps in the curent org to fill
* When work comes your way, do one of the following:
  1. Close out and quickly and permanently as possible
  2. Solve: Design a solution so that you do not have to handle it again within 6 months (e.g. policies)
  3. Delegate to somebody else
* **Culture only changes through persistent and consistent effort**
* Inclusive Cultures: everybody has access to opportunity and membership
* Make policies explicit
  * You have $X per year in education
* Membership is the precursor to belonging
  * Facilitate conversations across people to nurture relationships
* Let people apply for opportunities to lead secretly (i.e. non-public facing) and give 3 days time to get new people in
* Attach a mentor to every new leader
* **Foster a culture that focuses on the growth of others**, not yourself
  1. Know about peers work
  2. Evolve perception of character into a living person
  3. Referee defection to ensure good faith between everybody
  4. Avoid 0-sum games
  5. Make principle of peer-first explicit
* Only change 1 thing per projcet (e.g. database A with framework A to database B with framework A) to effectively observe changes on outcomes
* Working harder when already working hard eliminates and burns out people
* Hero programming are a sign of bad culture and policy to focus on the very short term
  * Let these systems fail fast to then "reset" and change fast
  * Fail -> Lean -> Try again
* Focus on career transitions/events (e.g. your boss leaving) and what skills were required to work in that new environment
  * Transitions let you build new skills
  * Stability lets you master skills
  * Growth only comes from change
* Mentor-mentee relationshp are important from project leads to canidate interviews
* Hire beyond personal networks to avoid hegemony by using cold sourcing
* Build networks through cold coffees
* Enthusiasm != passion
* Make career ladders concrete like policies
  * Start with 3 rungs, iterate as needed
  * Compare people to the ladder, not each other for promotions
* As an effective leader you need to explain simply to leadership how your goals (e.g. cold coffee, group chats, etc.) drive business or culture outcomes
* Crisis designations to retain "important" people should be used rarely and all implications to the ladder sould be considered
* Specialists are single points of failure
* Ensure there is career growth for every role as best as possible in your organization to retain people
* **You cannot improve a flow without being able to observe and measure it**
* Avoid design by committee in favor of small working groups to iterate faster
  * Committee results in bike shedding
* Management is about staying out of the details but keeping the work aligned to business value
* Keep roadmap and backlog small to remain flexible (agile)
  * Roadmap is a view for stakeholders
  * Backlog is a view for team
* Read: [No Silver Bullet](https://en.wikipedia.org/wiki/No_Silver_Bullet)
* Teams need clear goals they can visually look at to better focus/align on those outcomes as a team
* Add constraints to the system to discover optimizations
* **Accidental vs essential complexity**
  * Remove accidental complexity from bad code, organization, etc. design so that we can focus on essential complexity in our business domain/market
* Source code rejuvination: migrate old code to current standards using automated scripts
