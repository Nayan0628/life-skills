# Service-Oriented Architecture for Performance and Scalability

## Introduction

I joined a new project and the project is having some performance and scaling problems. When more users use the application, it is becoming slow. My team lead asked me to check if Service-Oriented Architecture (SOA) can help to solve this problem.

## What is SOA?

From what I understood, SOA basically means you don't build the app as one big piece. You split it into smaller pieces where each piece is responsible for one job, like a user service, an order service, etc. When they need something from each other they just call each other, but otherwise they run independently.

Since everything isn't stuck together, I can fix or update one service without having to touch the rest of the app.

<p align="center">
  <img width="700" height="467" alt="Service Oriented Architecture diagram" src="https://github.com/user-attachments/assets/af7f5b40-0b98-4768-a2cc-16046798a2a5">
  <br>
  Figure 1: Service-Oriented Architecture
</p>


## How SOA Can Help

One thing I realized is that not every part of the app gets hit with the same amount of traffic. Like, if the order service suddenly starts getting a lot of requests, I can just scale that one up on its own no need to throw extra resources at services like notifications or user profiles that aren't even under load

SOA can also help in:

* If one service is getting hit with a lot of traffic, I can scale just that one instead of scaling everything
* Easier to reuse a service somewhere else later if needed
* When something breaks, it's way easier to trace the issue to one specific service instead of going through the whole app
* Keeps things easier to maintain since I'm only touching the part that needs changing, not the whole system

But SOA also has some problems. One downside I found is that since services are separate, they need to communicate with each other over the network so if the order service has to check with the payment service and user service on every request, that adds delay instead of speeding things up.

## Conclusion
So overall, I think SOA is worth considering for our project since we're clearly running into scaling issues with more users coming in. But I wouldn't jump straight into rebuilding the whole app as services that's too big a risk without knowing exactly where the problem is. I'd rather start by checking the logs to see which part is actually slowing everything down, pull just that one piece out as a service, and see if it actually helps before touching anything else. If it works, we can slowly move other parts over the same way instead of doing it all at once.

## References

* Kumar, FNU Pawan. "Developing SOA Architecture Web Services for High Throughput Systems." International Journal of Science and Research Archive, 2025. https://doi.org/10.30574/ijsra.2025.15.2.1511

* Castro León, Marcela, Dolores Rexachs, and Emilio Luque. "Service-Oriented Architecture: Learning with Generative AI and AWS." 2025. https://doi.org/10.1007/978-3-031-97573-8_24

* IBM. "What is Service-Oriented Architecture (SOA)?" https://www.ibm.com/think/topics/soa

* Garima Singh, NDC Conferences. "Service Oriented Architecture - Slice and Dice." YouTube, 2025. https://www.youtube.com/watch?v=2Y17sfPiSn4
