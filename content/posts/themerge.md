+++
title = "Ethereum, The Merge, and how software development is hard"
date = "2022-10-07"
description = "Ethereum's Merge happened recently. I wrote about it. So I suppose this is a crypto essay"

+++

DISCLAIMER: I own zero cryptocurrencies. I am a "no-coin *****".

With that disclaimer out of the way, let's talk about crypto!

More specifically though, let's take a look at one of the biggest events in the wasteland of tech, Ethereum's transition from proof of work to proof of stake aka The Merge. However, this take will not come from the perspective of the blockchain, cryptocurrencies, or anything very technical, but instead at how development teams work together. A lot has been said about the what and the why of this event, but I've been struck by the how. Specifically, how these developers from all over the world (who don't work for the same company or organization mind you) managed to pull of such a complex feat on what is basically a world wide production build WITH ECOSYSTEMS BUILT ON TOP. Basically, making software things is hard usually because of people (not the technology itself), so what this team // collection of teams did is honestly insane when you really think about it. 

**HOW IS THIS HARD FOR ANYBODY**

Software development in a team is hard. I don't think that's too crazy of a take. Now, some of you might say "learning how to code is easier than it's ever been" or that no-code platforms make software easy enough for anybody to create or something something Github Co-Pilot or some other reply that doesn't actually negate what I'm saying.

- Is the information to learn how to write software code more accessible than it's ever been? Yes
- Are there now more tools for developers including AI to help you write code? Also, yes
- Is it now possible for people to collaborate across physical and time constraints to an almost comical extent? Also, also, yes

But none of this takes away from the fact that software development from the perspective of teams working together is extremly hard. We have entire cottage industies and cults dedicated to the one way to make this easier. 

Perhaps you've heard of Agile? Scrum? Waterfall? 

I assume you've also maybe heard some of the discourse around working from home? Perhaps the middle managers screeching about how teams must be in the same room at the same time to "foster creativity". Or the individual contributors yelling back about how productivity is up actually and that they can't hear them over the sound of their kids in the background. (Disclaimer: I am on the side of remote work...middle managers are silly)

The point is that making software things together with other people is hard. And it's not an exact science (as seen by the fact that there is no one perfect answer or method). There's an art to it. Communicating between people is hard, collaborating even more so. Think about literally any group project you've ever been a part of. There's always a natural tendecy to slide into entropy (it is really easy to not work well in a team is what I'm saying). So with that point hammered home. Let's move on.

**HOW IS THIS HARD FOR REMOTE DISTRIBUTED TEAMS**

Okay so at this point, everyone gets it right? Software development in a team is hard, as a general rule. Drilling down even further into the specific case of remote teams, we can see that there's even more issues specific to the case of people working remotely together. 

Let's start with the obvious: scheduling

On the face of it, not too challenging right? When can we all sit down for x amount of time? 

This is where the lovely idea of timezones comes into play. While this is not always the case for a remote team, in the case of the team that implemented the Merge, it is applicable. The team was composed of people from all over the world. One woman's 3 PM is another one's 3 AM (or something like that). The point is, after a certain amount of people (let's say n+5), scheduling is hard. 

Then, the next issues are the tools used to work together as a distributed team. Now, there are definitely some great ones out there. Github & Gitlab, Miro, Google docs, Discord and a slew of others are quite good. But then there's the not so good ones (whichever one popped into your head when reading that is the one I mean). And while not always showstoppers, tools that make already hard things even harder are like not good (yep, that's my offical stance on that). So not only are you working to schedule everything...there is a good chance you're also troubleshooting the very things that will allow you to do the thing that you are trying to schedule so that you can then do the actual thing you want to do. So that sucks (again, that's my official stance). 

Working remotely opens up its own can of worms as noted above. Making a hard thing...potentially even harder.

**HOW IS THIS HARD FOR REMOTE DISTRIBUTED TEAMS WHO ARE NOT LEGALLY NOR CONTRACTUALLY TEAMMATES**

So the section above might not seem like a big deal right? Scheduling, fixing Microsoft teams, etc is not like the hardest obstacles in the world. I tend to agree. After all, for all its negatives, working remotely beats having to arrange for a team of people stationed all over the world to come into the same physical space. The complication comes when we look at the people side of things. Specifically, the relationships, incentives, and other factors that play into how people work together. 

I don't think its too bold to say that it is easier to work with someone who is legally, contractually, and like explictly your teammate // coworker. You are inclined to be collaborative since you are literally being given a salary, company resources, and other incentives (i.e promotion) to do so. Your goals (for the most part) are aligned. You want your teammate to succeed, so the team can succeed, so the project can succeed, so the company can succeed so they can in turn, give you more salary and so goes the lovely flywheel of employment in a capitalist system. Now, I'm not saying this always happens (I am quite aware of the intricancies of politics inside corporations and how different teams can be antagonistic even if they are part of the same org), but for the most part, it works better than the other scenario. 

That scenario is the one that the Ethereum teams found themselves in. What is the alternative to working with only your legally and fiscally mandated teammates? Well, working with teams from other orgs. This can be seen when a company hires consultants or a contractor works alongside an in-house team. This can also be seen when two companies partner on a joint venture or initiative. This can also happen when your public project is governed by a variety of factions and individuals with wildly different priorities, incentives, and goals. To give you an idea of what I mean, here's an unofficial look at the different parties involved in the Merge and the wider Ethereum ecosystem (note: there were literally hundreds of developers that played a role in this multi-year project so this is by no means comprehensive):

- Vitalik (I don't think I have to expand on who he is) & The Ethereum Foundation (as the nominal stewards of the community, they have a large amount of teams that contributed to the shift to proof of stake)
- ConsenSys (one of the factions from the original launch of Ethereum and a major team in the space, one of their researchers published a paper in 2020 on what ended up becoming the mechanisms behind the Merge and they continued to actively contribute at a code and leadership level)
- Prysmatic Labs (a team originating from Prysm, one of Ethereum’s most popular software clients, their developers have been recognized for their importance in the PoS shift and its implications in the wider ecosystem)
- ChainSafe (another firm with deep relevance in the ecosystem, one of their projects plays a pivotal piece as a validator in the new proof of stake model)
- SigmaPrime (similar story as ChainSafe, one of their projects is a client that plays a key role for the concept of "consensus" in Ethereum)
- Ethereum Cat Herders (a group dedicated to supporting all those involved in the project by taking care of project management, coordiantion, etc)

As you can imagine, each of these groups represent a rather large amount of teams and developers that led to such a large base of contributors. I don't believe they were all the best of friends with perfectly aligned processes, methodologies and general ways of working.

**HOW IS THIS HARD FOR REMOTE DISTRIBUTED TEAMS WHO ARE NOT LEGALLY NOR CONTRACTUALLY TEAMMATES WHO CONTRIBUTE TO A WORLD WIDE ACTIVE NETWORK OF USERS**

Okay so I think at this point we might be getting an idea of the difficulty of software development by teams at this scale. From the get go, software development is hard. It can be even harder in teams that are sitting in different places on our lovely planet. It is even harder when these teams are made up of a multitude of organizations, individuals, and interests that are not contractually enforced or governed by a central legal authority.  I'm about to mention another wrinkle in all this:

- The project they were working on is a globally de-centralized programmatic platform with communities, businesses, and other protocols built on top of it and relying on it to exist.

Think about the ramifications of what I said earlier. What happens if you fail in one feature or commit? Boom! there goes entire companies that are now dead in the water since their business relies on the platform you just messed up on. I mean, the amount of pressure is immense when you put it into perspective and unlike other projects, the safety net of centralized responsibility and governance is gone. It is literally like building the rocket ship as you fly it...except it's more like a flying city with a noninsignifcant amount of people relying on you not to royally f*** up the building of the thing otherwise they uhhh will be very very very not happy and likely out of a job, money, etc.


**HOW DID THE MERGE ACTUALLY HAPPEN THEN IF ITS SO F@@@*@*@ HARD TO DO THIS STUFF**

Reading about the inside baseball and the anecdotes from those who were active in the project or who spoke with contributors, a couple things jumped out to me:

- While the various factions and items were not part of the same company or contractually considered teammates, their interests were aligned due to an almost reverent desire to make this go well (another hot take: the crypto community has a tendency to create zealots) and because for most of them, the success of the project was inherently existential (i.e. their products, communities, etc relied on it going well to surive)

- Willingness to adapt: every single piece that I read mentioned how people were willing to meet at odd hours or off days. If all parties involved are willing to make concessions when it comes to coordinating things, things go a lot smoother. I definitely don't like being the one that gets up really early or stays on really late, but if everyone takes turns having to be the one willing to sacrifice, it can make it go a lot easier. This goes past scheduling. Willingness to adapt to a particular tool or organizational style or anything else really seems to be a key factor in the success of the project. It signals the intent to collaborate and meet others halfaway. Some could call that earning trust.

- Variety of plans of attack: there was no one set path forward. While the original idea for the how to make the merge happen from a technology perspective was published and all the technical aspects had to be agree upon and executed, there was no concrete roadmap created on Day 1 and followed to th letter. It was an evolving plan that had to be adapted and reshaped and reexamined, continually. While teams worked in traditional project formats (formal sprints with stands ups and all the usual agile side stuff), they were also hosting hackathons, workshops, and IRL meet-ups. They were having debates and publishing papers and sharing knowledge through non traditional means. I imagine that the nontraditional events and nature of the plan helped create some sort of bonding between all the parties as well as helped foster a wide variety of contributions that may not have come from doing things the modern, traditional, sdlc type of way.


Overall, I picked up on a general vibe from all the people involved in the work: a larger mission. For some, it was the mission of "Ethereum" aka the continual growth and development of the technology because it was the future of society and financial systems (see zealots). For others, it was a desire to rectify a key weakness in the platform, its energy use and effect on the environment (see climate change). For others, it was their magnus opus, their scream into the void, their greatest work, etc etc (see the futility of human life and our attempts at a legacy). The mission might not have been exactly the same...but they all had one. 

**CONCLUSION**

You'll notice I didn't mention a specific set of tools or technologies when looking at how they managed to get it done. Everything I mentioned was a people thing, not a technology thing. At the end of the day, the hardest things in tech tend to be those that deal with people and their interactions. Something I've found in my experience and from researching this project is that for people to go the extra mile for one another, it has to go beyond contracts or money. There needs to be higher purpose to the work because that is what gets people through the hard moments. There's a lot of ways to mitigate the issues that arise in distributed software develpment (IRL meet-ups, rotation of duties, staggered schedules, asynch knowledge transfer), but to truly get the hard things done, people need a mission to strive for. I'm not saying everyone should frame work as "we're saving the world", but we should definitely try to find the higher level values and drivers that motivate people to work well together and strive for more than just the basics. It could be as simple as "we're all trying to get this done so that we can make enough money to live without financial stress and enjoy life outside of work". That may not be as inspiring as revolutionizing the global financial system, but a mission that everyone aligns with and can use to drive them forward might be the only true way to make the hard things of software development a little bit easier.

Cool Stuff about the Merge:

- As seen on twitter (credit to @0xmts),

https://twitter.com/0xmts/status/1570304368636993536?s=46&t=Nrzwk2aQY2BdaifQSSqU3Q

- A merge visualization I prompted Dall-E for,

![image alt text](/merge.PNG)



Good Reads about the Merge:

- https://fortune.com/crypto/2022/09/21/inside-look-behind-the-scenes-ethereum-merge/
- https://www.coindesk.com/tech/2022/09/15/meet-8-ethereum-developers-who-helped-make-the-merge-possible/
- https://ethereum.org/en/upgrades/merge/#main-content
- https://www.theblock.co/post/166999/the-merge-10-key-people-behind-ethereums-biggest-upgrade-yet


