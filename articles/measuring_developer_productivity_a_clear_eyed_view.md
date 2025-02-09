# Measuring developer productivity: A clear-eyed view

<https://www.linkedin.com/pulse/developer-productivity-metrics-challenging-parts-abi-noda-3fmgc/>

## Key Takeaways

* Developer Expeirence (DX) is mostly about developer efficiency. The biggest lever companies have in developer efficiency is eliminating waste in the development process: something every developer has first-hand experience with. Friction like long wait times (e.g. long PR review cycles), slow deployments, and untimely meetings are a few examples of efficiency dampers. Others may be like constant context switching as a result of WIP limits set to high. Developers are customers of the development process. So work with developers like any other product-customer group to reduce or outright eliminate waste so developers can do more with less.

* DX in many ways mirrors Maslow's Hierarchy of Needs: stability in one heriarchy enables growth in the next. Making CI and CD effortless frees more time for developers to think crtiically about problems and reduce barries to changing bad domain models. Once developers get good at delivery, they can jump up another layer to more business orientated thinking.

* Extreme Programming (XP) is deliberably divided into values, principles, and then practicies because a focus on practice can get twisted in intent. Drawing from many SCRUM implementations, many teams do daily standups as a means to report status instead of as an opportunity for the team to sync and re-organize around the work to be done more efficiently. This focus on the practice over the values or principles leads to dysfunction and in turn eats away at developer efficiency.

* Kent Beck believes most developers survive and only expeirnece the Desert of agile practicies. Organizations there there is little learning, little helping others, and mostly just do do do do do do (e.g. capability trap). On the other hand, XP is more like a Forest in which learning is paramount from software practicies to what customers really think about your product. Desert developers only know the Desert, so they don't think about or think it possible to live in a Forest.

* There are four core DX metrics: speed, effectiveness, quality, and impact. These core-four all counter balance each other, so being out of balance leads to issues in the others. For example, being extremely speedy by cutting corners kills quailty. Being extremely efficient at delivering the wrong things kills impact. Measure and balance these core-four at the team or higher level. But do not pit developers or even teams against each other. If people are competing, Goodhart's Law kicks into effect and people will game the system in order to win.

## Notes

* Gusto uses Developer Experience (DX) as internal KPIs for their CI / platform team, not something developers are actively aware of and striving to get better at through personal efforts.
* "One thing that we give as guidance to companies - and I stole this from Google, they've said this best - is that Goodhart's Law is 100% true. As soon as these measures become something folks are incentivized to game and manipulate, the very signal you worked so hard and paid for becomes useless or inaccurate."
* People will degrate systems to game numbers.
* Frame DX metrics as removing friction from a process, not trying to output more work.
* Reference: DX Core Four

* Three levers for buildling trust
  1. Communicate and follow through on allyship with developers
  2. Never measure metrics at the individual level - this only encourages gaming.
  3. Use metrics only in the context of other metrics - never standalone (e.g. balance speed vs quality)

* The four pillars: speed, effectiveness, quality, and impact, all counter balance each other.

* "Extreme programming (XP) is deliberately divided into values, principles, and [then] practicies... because ... focus on practice [can] be twisted." - Kent Beck
* "We're here to have fun. You know what's fun? Winning. If that means we have to practice extra hard or do more drills so you're more capable of winning, and you don't like doing more drills - well, we're aimed at a higher level of joy than whether you have happy-clappy fun today."
  * Focus on the value and principles, then figure out the practices which work within the context of those values and principles.
  * For example, a pee wee football team might be more focused on having fun and building team work than winning - values and principles which focuses on a different set practicies.
  * Values and principles influene the practicies which should or shouldn't work within a compny - principles first thinking.

* Reframe DX as "developer effectiveness" and it changes the tone of the conversation / frame of reference from "happiness" to "effectiveness"
* Example survey questions using a Likert-like scale with options Never, Rarely, Sometimes, Very often, Always, Unsuer (N/A)
  1. "When I investigate production issues, its easy for me to debug."
  2. "For the product areas I work on, production issues and incidents are handled effectively."
  3. "When I need a code review, I receive one in a timely fashion."
  4. "Its easy for me to understand and modify the code that I work with."
  5. "When developing, I can quickly verify that my changes work."

* Reference: "Anti-productivity" by John Cutler
  * Measure anti-productivity instead of productivity metrics
  * Where are developers waisting their time?
  * Eliminating waste makes people go faster without asking individuals to work faster through all the waste - focus on eliminating friction.
  * Let people move faster by eliminating waste rather than telling people to move faster through all the waste.

* Kent Beck believe most developers survive in the Desert (little learning, little helping others, just do do do do) vs the Forest where lack of friction to learning, helping, doing is non-existant. So, people who have only lived in the Desert don't know what they are missing, and so they don't know the Forest even exists and is worth working towards.

* Developers have first hand experience with what makes them frustrated (e.g. flaky tests, slow PR rewviews, slow deployments, etc.) so start there to improve DX.

* Benchmarks help frame metrics, but each environment is unique so take benchmarking with a grain of salt.

* Selling a productivity dashboard without the expert knowledge to interpret it is like a doctor handing you your results and saying "go figure it out yourself". Don't do this. Knowing what the numbers mean and more critically what levers to use to improve them.
