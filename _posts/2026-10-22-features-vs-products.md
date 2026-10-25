---
title: 'Features vs Products'
date: 2026-10-22
permalink: /posts/2026/10/features-vs-products/
tags:
  - blog
  - NSF
  - research
  - I-Corps
  - entrepreneurship
  - startups
  - customer-discovery
  - phd
---
> *Journey before destination*
> --- From Brandon Sanderson's *The Stormlight Archive*

So this is a post that is long over due, but sometimes, life takes you on unexpected paths. This week, I successfully defended my PhD dissertation in Mechanical Engineering from Temple University and will be moving on to the next chapter of my career, so I wanted to take some time to revisit this journey and close things out.

Building something that nobody wants (or worse, wants to buy) is often regarded as the cardinal sin to avoid at all costs when launching a startup. It's why, for the most part, startup business development typically *starts* with defining the customer, the customer's pain point, and how to monetize it. Only then do you start getting into how innovative business models, new technology, software, et cetera, can be brought in to fill that gap. The whole point in this is to identify people with money who have a problem that you can solve, rather than trying to find people (let alone people with money) who need the solution you've made to a problem you're certain they have.

It's a sin I'm all to familiar with and committed in the past with my first startup Tergeo Technologies. I'm a roboticist. I live in Philadelphia. Philadelphia has a litter problem, why don't we get robots to fix this! Well...who pays for this? Is it more effective than just getting a human? Is it cheaper? Is there enough margin in the hardware that we could actually make a profit? How would we operate a Robot-as-a-Service model? Are people even comfortable with bulky semi-industrial robots on the sidewalk with them? Is that even safe? Ultimately, these are the questions that should have been answered prior to building not one but two prototypes that are now collecting dust in my basement. Hit me up if you're in need of some RaspberryPis, batteries, or servos.

When I set out on this journey again I was determined to *not* make that same mistake again by going through the NSF I-Corps program and doing things the right way. To reiterate, my goal with going through the NSF I-Corps was to examine the market and see if there was a business niche that I could leverage my PhD dissertation research into. My research covers how you can use geophysical properties of the Earth's terrain, gravity field, and magnetic fields to derive a position fix for an inertial navigation system. In particular I have focused on gravity and magnetic anomaly aiding for navigation in GNSS-denied environments, something that has been a bit of a hot topic in inertial navigation circles for several years now. When I started my PhD and certainly by the time I decided to try out I-Corps, I had worked in this research space long enough to know that it was a real technical problem that people wanted solved, but the only business case I had built around it was either a) as a traditional tenure-track researcher working via grant-funded research; or b) as a researcher in a UARC, FFRDC, or other such national lab similarly working on contracted out basic and applied research and development. The question was then was there enough there to turn this into a repeatable business model outside of the traditional research avenues?

This leads to the second cardinal sin of startups: building a feature instead of a product. This one is tricky, because there is absolutely an exit model of building a comprehensive feature set that another larger company purchases for the sake of acquiring the features and the corresponding engineers that built it. This is the classic acquire-hire. We've seen this recently in the software tooling space with the Bun and Astral acquisitions.

I-Corps really pulled no punches. It forced me to get out of the lab and talk to potential customers, partners, and stakeholders, and to confront the harsh reality that interest in my technology did not automatically translate into a viable business model. The program emphasized the importance of validating the market need before investing heavily in building a solution, and it became clear that my initial assumptions about the commercial potential of my research were overly optimistic.

What I heard was, "Your technology is interesting and impressive, but don't rip out our existing avionics suite." "It's impressive, but we have our own internal solutions for this." "We appreciate the innovation, but it's not something we can integrate into our current operations." Essentially, the feedback was consistent: while the technology was valued, the practicalities of adoption and integration posed significant barriers, particularly when talking about high-stakes environments like aviation and defense that already have trusted and validated systems in place. This highlighted a crucial insight: the market demand was not for the technology itself as a standalone product, but for the expertise and capability to implement it effectively within existing systems. People were hiring for this role. Businesses wanted folks that could build passive navigation capabilities that were resilient to GNSS-denial. If there were this many people looking for this expertise, it suggested a viable business opportunity lay not in selling the technology as a product, but in offering specialized services and consulting to help organizations integrate and leverage it effectively.

Also a dud. People didn't want a consultant to come in and implement or integrate this solution for them either. The market was signaling that while there was interest in the technology, there wasn't a willingness to pay for external expertise to deploy it. This was a tough pill to swallow, but it was an invaluable lesson in understanding the nuances of market demand and the difference between technical feasibility and commercial viability. It became clear to me that while my research was interesting, while it had commercial value, I was fundamentally building a feature in somebody else's navigation and autonomy stack. So I made the decision to not go forward with this route and turned my attention to job applications.

One company that was hiring, was Mach Industries. Autonomous aerial vehicles and platforms operating in GNSS-denied environments were the focus, and they were actively seeking expertise in passive magnetic navigation solutions. This indicated a clear demand for specialized skills in this area, reinforcing the idea that while the market might not be ready to buy the technology as a standalone product, there was a tangible need for the knowledge and capability to implement it effectively. I've been there for about ten months now working on upgrading and modernizing their navigation stack, with an emphasis towards enabling passive geophysical navigation feedback as well as other alternative PNT techniques as well.

We'll see how this plays out in the coming months as we continue to integrate and test these advanced navigation capabilities on real-world platforms. The hope is that by demonstrating the practical utility and reliability of these techniques, we can bridge the gap between research and operational deployment, ultimately proving the commercial viability of the technology in a tangible and impactful way and start a virtuous circle of field data validating research, posing new questions, and leading to new research thrusts. If you're interested in working on tough problems on the GNC stack for autonomous UAVs, [we're hiring](https://machindustries.com/careers) for a range of positions in the GNC department, across all disciplines, and across ranges from new grads to Principals.

---

*This post is the conclusion of my short lived series documenting the transition from research to real-world product through the NSF I-Corps program.*
