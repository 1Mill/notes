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
    
