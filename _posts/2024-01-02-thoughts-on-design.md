---
layout: default
title: Thoughts on Design
---

The thing that was hammered into my head as a CS student at OSU was that there is not necessarily a right answer to the architecture question. It's all about tradeoffs and about what serves the team's needs best. 

Two years into my engineering career, I'm starting to see at least the seedlings of some thoughts about that discussion.

### Principle:
A company or an organization within a company or even a team within an organization can implement good architecture poorly. 

Case and point, the last company I worked at. I was on the UI team. We built the frontend applications that our organization maintained. These applications relied on several dozen microservices. Every microservice was broken into a separate repositories. These separate microservices and repositories were managed by the cloud services team, which was separate from our team.

Separation of concerns, broken up into separate repos and managed by separate teams. Seems pretty organized and straight-forward, right?

Well, not quite.

One big issue was that our team really had no contact with the other teams. When I joined, I literally didn't know who was on the cloud services team. I never saw them, I was never introduced to them, I didn't have a standard way of communicating with them, and no one on our team seemed to know who they were either. We didn't know who to talk to about which service.

To make things worse, as I was getting familiar with our team's repos, I noticed that the transition to microservices was only half complete. All of the old services that used to live in the application monolith were left there for some weird reason. This code wasn't marked in any way, no one had flagged it as legacy code, and it was pretty much the same code that lived in the microservices repos. It was just left there to confuse the hell out of us.

So, just on these two observations alone, I notice a couple principles.

Microservices are pretty fricken useless if there's a lack of communication between teams. If you don't know who to talk to about which service, and there's no documentation when services change, why would you silo away this info from the team that actually consumes the service. This seems like shoving your microservices in a different room, locking the door, and throwing away the key. Good luck trying to figure out what the cloud services do now!
