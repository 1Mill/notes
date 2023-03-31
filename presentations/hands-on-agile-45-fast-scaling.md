# Hands-on Agile 45: FAST Scaling — James Shore

<https://www.youtube.com/watch?v=WbPLjuvyCUA>

## Key takeaways

* There are two ways to scale agile: horizontally or vertically. Horiziontally is when a company increases the number of interdependent teams required to deliver customer value. Vertically is when a company increases the number of people in a team so that the team can deliver customer value independently.

* A horiziontally scaled agile company usually partitions people along capabilities. Examples include a company have a design team, a database team, a security team, and so forth that work together to deliver value. The issue with single responsibility teams is that work and people to not fit nicely into auto scaling boxes. Additionally, these teams are often over utilized forcing dependent teams to wait: incrasing the cycel tiem

* A vertically scaled agile company disolves these design, database, and security teams and embedded these people into each end-to-end team. This ways, teams get all the needed skills to deliver customer value independently but without dependencies. A trait which eliminates waiting from the cycle time.

* How to adopt Fast Agile:
  1. Start with two willing teams that work closely together
  2. Teach collective ownership and collaborative skills (i.e. working agreements) if needed
  3. Implement FAST
  4. Wait for collective to stabalize
  5. Include another team into the collective (3 - 5 people at a time) - do not expand too fast
  6. Repeat steps 4 and 5 until collective feels strained from size (e.g. Dunbar's Number).
  7. Repeat step 1 with new collective.

## Notes

* Book: The Art of Agile Development, 2nd edition
* Reference: Agile fluenceny model

* James Shore helps companies scale agile
* Scaling when you increase the number of interdependent teams required to work together to deliver value.
* To deliver sooner:
  1. Reduce scope
  2. Eliminate waste
  3. Improve technical capacity
  4. ... several other options - what are these other options?
  5. Scale
* Scaling is the last lever to pull to deliver value faster.
* Scaling can tank productivity because of how complex scaling is
* Adding a bunch of people too quickly to a team loses tribal knowledge and existing culture.
* Most common scaling strategy is component teams - each team is focused on a specific technical component like a database, frontend, etc.
* Value stream mapping helps companies identify waste in their process, such as bottlenecks
* Some companies have large waiting periods in their processes because of hand offs, so teams start new work to fill those gaps which causes a cascade of waiting across the entire company.
* Each hand off increase the chance of erros - such as miscommmunications
* Use a sepegetti diagram to visualize dependecies - team X cannot get a project done without team Y also doing something

* Full ownership team - Stream aligned teams from Team Topologies.
  * This team "... can completely own a segment of the market".
  * Sometimes called feature teams - these teams focus on featurs instead of technology / components
* A Stream Aligned Team (SAT) "... focuses on a continous flow of work aligned to a business domain or organizaitonal capability".
* A SAT must still be pizza sized teams which makes covering all domains of a market difficult such as security, UX, etc.
  * This causes copmanies to form teams around capabilities, such as the design team, the SEO team, etc.
  * This still causes dependencies between teams just like component teams which create wait in the sytem.
* An SAT structure is difficult to change / is inflexible to changing market demands.
* SAT lead to silos because people optimize locally for their specific team: not wholistically across the entire company.
  * If I want to increase the conversation for my feature, I can make the button take up half the screen.

* FAST - Fluid Scaling Technology (FAST)
* "A group of people who self-organize into teams on a frequent cadence"
* SAT scale horizontally by adding more teams - FAST scales vertically by adding more people to one team
* Horizontal teams require huge alignment and are usually implemented from the top down in a big way
* FAST scaling is incremental and bottom up.
* In FAST People self organize based on skill, passion, personal relationships around the work to be done within the company
  * This project needs security questions answered: great, lets ask Joe who I worked with on my last security problem with.
* FAST is "a light weigh, simple to understand, and simple to master method for organizing peopel around work - that scales".
* High level overview
  1. Bring everybody to work together as one team called the "collective"
  2. Visually represent business goals on a single wall (the marketplace from Open Space)
  3. Let the collective self-organize into teams to break down and do the work
  4. On a short cadence (usually every 2 days), sync and repeat these steps
* Reorganize teams every 2 days.
* James held FAST meeting on Monday and Thursday mornings
  * Other companies from FAST community do Monday and Wednesday with Friday as continous improvement days
* People have the opportunity to change teams but in practice people usually stick with the same team until the work the team is working on is complete.
* Outline of FAST meeting
  1. Each team summarizes what has been learned and done since the last FAST meeting
  2. Product managers review current business goals for the collective
      * Business goals do not change frequently
      * Usually this is communicating what is coming up next after a current peice of work is done
  3. People volunteer to lead teams called "stewards" for the next 2 day sprint
      * Anybody can volunteer to be a steward but watch out for one role or person dominating these positions
      * In Jame's example the company limited these positions to engineers because they were otherwise dominated by product managers.
  4. Stewards say "I want to form a team around X"
      * X can be anything - often this includes technical debt, automation, spiking on something, or work from the wall.
      * X can be anything that moves the organization forward
  5. Everybody self-organizes onto the teams they want to be on for the next 2 days
      * Motivated and aligned people know what is intricically best for the organization
      * With the constant sharing of business goals / context by product managers at start of meeting, everybody is working in the same context when teams are formed - weighing what to work on is clear.
  6. Each team starts working however they see fit
      * James mentioned using Discovery Trees but did not go into details
* A 2 day cycle is not the same as a sprint which requires a type of committment or release of some sort. It is a good faith timebox to learn or do something that will benefit the company.
* A team is committed to making as much progress as they can within that 2 day cycle - nothing more.

* James uses Team boxes in MIRO
  * Communicate who the steward is
  * Communicate who is working on what team
  * Communicate the team's focus
* James uses a Business organization area in MIRO
  * Similar to swimlanes about what is in progress, what is done, what is next, etc.
  * Pull based
  * Recommends: "Done", "In progress" with WIP limits, and "Next" with WIP limits
* Recommends a ratio of 1 team per 4 engineers if not using paired programming
  * What is the recommended ratio if using paired programming?

* Communicate state of work though color, icons, etc. in MIRO
* In the 2 day cycles teams learn quickly if work is feasible or not - maximizing the work not done and minimizing waste.
* After people learned how the framework worked, people formed and stayed on teams for a while. Only swapping to a new team when a feature was finished or blocked.
* Company started to be deliver more quickly because of eliminating wait from the system

* FAST has a low overhead - about 20 minutes per FAST meeting which comes out to about probably around 1 hour of overhead per week.
  * SCRUM standups alone require more per week without other SCRUM events
* People fluidily allocated themselves around the work to be done
* It is a culture shift to move from 2 week spints to 2 day cycles - you must clearly communicate expecations so that people aren't stressed about delivering something in those 2 days like a normal sprint.
* FAST is a continuous flow of work

* Idea Flow (not FAST specific)
  1. Chartering: everyone works to clarify purpose and context
  2. Visual planning: PMs and Execs identify valuable increments / business opportunities
  3. Prioritization: Execs decide which increment to build next
  4. Getting ready: Execs identify a PM who prepares the increment for development
  5. Ready to Start: The increment waits for a team to choose it from the wall / marketplace
  6. In progress: Self selected team(s) build out the increment
  7. Complete: The increment is released and is delivering customer value
* This "idea flow" is in conflict with Continous Discovery where the Product Trio "charters" what to work on next.
* This "idea flow" is still very heavily RED versus TEAL - reducing engineering ownership
* Execs had total transparency and control over priorities

* FAST "created a high degree of transparency" so that everybody understood the context the business was working in.
  * This makes aligning around the work to be done easy
  * This makes weigning the pros and cons of technical versus product work easier for engineers
* Just-in-time allocation of people
* High agility so company can easily pivot as higher priority work comes up
* Stewards have improved leadership skills
* Onboarding new people is very easy
* Pitfalls of FAST seem unique to the company and their culture from James' perspective - not the FAST framework itself.
* FAST is extremely agile
* FAST is extremely resilitent to people onboarding and offboarding
* How a team operates may be an issue - ensure roles such as steward are shared

* How to adopt FAST incrementally
  1. Start with two willing teams that work closely together
  2. Teach collective ownership and collaborative skills (i.e. working agreements) if needed
  3. Implement FAST
  4. Wait for collective to stabalize
  5. Include another team into the collective (3 - 5 people at a time) - do not expand too fast
  6. Repeat steps 4 and 5 until collective feels strained from size.
      * Other companeis have scalled this to 100 people and speciulate the upper limit is 150 - 250 people, some think it can be much larger (i.e. TEAL).
  7. Repeat step 1 with new collective.

* A FAST Collective contains all the right people with all the right skills to deliver end-to-end value from ideation to done.
  * You don't need platform teams to enable other teams - collectives should be self sufficient.
* FAST Teams are self-organized which means they can be of all different sizes - there is no need to make them equal in size.
* Need to clearly communicate expecations from 2 day cycles
* FAST is such a different way of working that most people are not familiar with so there is a learning curve / adjustment period before a collective enters a flow state.
* Dynamic reteaming really helps knowledge sharing
* No practical experience that people slack off because they are not being micromanaged.
