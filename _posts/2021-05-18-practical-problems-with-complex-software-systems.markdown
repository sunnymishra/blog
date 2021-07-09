---
layout: post
title:  "Practical problems with complex software systems"
date:   2021-05-18 18:30:35 +0530
feature_image: images/messy-system.jpg
tags: [softwaretips]
---

Complexity in a system can change form and can be passed on to different parts of the whole system but it can never be removed. Complexity has to exist to solve complex business use-cases.

<!--more-->


#### The architect's mind

Ideally an architect has to maintain a fine balance between various priorities while designing a system. The system should be simple and less complex, the system should be easy to use by writing simple SDK contracts, the system should use standard design patterns so that documentation of the system and training of engineers would be easy to modify the system, the system should solve all the documented business use-case at the time of designing the system, the system should give acceptable response latency, any abnormalities should be documented.

A software system is built initially with a fixed set of business use-cases to solve. The external dependencies are defined and the contracts between talking sub-systems are frozen. This also means that the system was built to solve a fixed set of problems in a 'lab' and tested in a closed system devoid of all the external abnormalities. While the code gets documentation as it gets written, as the lab phase gets over the use-cases are documented and the engineers are trained to use it and modify it if the need arises.

#### Practical example of complex system

While working on a system design a few years ago I came across some harsh realities. We were building an autonomous framework that would have multiple trigger points. Each trigger would have to then invoke various REST endpoints to fetch raw data. Also, which trigger would invoke which REST endpoint of course would have to be configurable. Once the data is received, the system would then have to run some Map-reduce transformations and then deserialize the result into customized JSON strings and dump it into the datastore. Here the fact that each REST endpoint would have a unique response Schema adds complexity to the overall design decision.

We did 3 iterations to solve the above problem. Each had its limitation; the first one wouldn't solve all the business use-cases that the Product manager would add on the fly. The second iteration worked but it was so complex that it would take weeks to add/modify a feature into the system. The third module was built with future use-cases in mind, a very robust system, unfortunately, it used various 3rd party libraries, some of which overused Reflection and thus slowed down the response time.

#### Hidden cost

Apart from the engineering cost of reducing or managing the complexity, there is also the inherent need to educate the stakeholders. Imagine having a boss who thinks that a framework which is built with 2 senior engineers over 2 Sprints (6 weeks) cycle should take away all the complexity from the consumer modules, therefore any new feature addition can be managed at the consumer module side and no additional development effort would be wasted on the framework itself. This is flawed reasoning. No framework is robust enough to handle all the future business use-cases. Every addition of a new use-case would require modifying the system and therefore knowingly adding complexity. This also requires expensive developer's time.

Consider this use-case: The above system was built because previously the entire team had to write code by hand to handle every new "Trigger -> Data fetch and Map-reduce processing -> Result schema materialize and persist phase". This was a huge engineering cost. To cut back on this cost, the framework was built and the entire complexity was pushed to the framework so now the individual engineers only need to write the trigger code, which would be very simple. With time, new use-cases would be added and the framework had to take the brunt by adding more complexity. The system is solving all the use-cases but at the cost of increased entropy and complexity.


#### The changing form of the complexity of the system

This brings us to the last part: the changing form of the complexity of the system. There is a huge cost involved here in terms of training the new engineers to modify the framework system code. By design, it was meant to abstract away all the complexity and only expose simple SDKs to the consumers. This means every time a new use-case had to be supported the complexity had to be adjusted within the system, without compromising the SDK contracts, else it would mess us the entire consumer module. But in reality, we don't always have the original engineers available, who built the framework. So we train the new engineers, but with less time they are not adequately equipped. So they take a longer duration to modify the framework codebase. To alleviate this problem, someone came up with an easy alternative, but a messy solution: add shims in the consumer code. We all know what shims are, right? You are scared of touching the complex framework code, but you have to add the new feature, so what you do? So you add an adapter code directly in the consumer module and this Shim would now handle the new use-case before invoking the system. Problem solved. But now the complexity of the system had been moved from the core system to the peripheral sub-module. Hard to identify the bug and hard to fix. Now instead of 1 giant spaghetti code of mess, we have spaghetti spread all over the place.

The crux of this article is to highlight, how we build complexity into a software system and how it is not possible to remove complexity entirely. *The complexity has to live somewhere in the system, to serve all the business use-case.* Do check out [this article](https://ferd.ca/complexity-has-to-live-somewhere.html) for further read on this concept:  



Image credit:    
 <cite>Photo by Amol Tyagi on Unsplash</cite>