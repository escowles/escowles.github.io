---
layout: post
date: 2018-09-05 22:39:43 -0400
title: digital collections developer's toolkit
---

reading jonathan rochkind's blog post, [proposed rails-based digital collections developer’s toolkit](https://bibwild.wordpress.com/2018/09/05/proposed-rails-based-digital-collections-developers-toolkit/), a couple of things jumped out at me:

> It could possibly be addressed by trying to reduce the scope of the re-usable toolkit to just focus on getting our app launched (which one could say is the approach Princeton and PSU are taking), but there’s still some risk that as we try, we find it’s just not going to work.

i don't think that's what we're doing.  the data mapper working group produced an mvp app to demonstrate valkyrie, using several samvera and broader rails community gems, and figgy has built on that work and implemented both our local logic and some patterns we think others could use.  the one piece that we haven't built has been a web framework, and we've been open to collaborating on that, but for various reasons it hasn't worked out.  until recently, figgy [had the beginnings of a web framework in it](https://github.com/pulibrary/figgy/pull/1280), and we had some discussions with penn state about collaborating on it before deciding that the approaches in figgy and cho were different enough that they weren't going to share a meaningful amount of code.  i continue to think a web framework could be a useful complement to valkyrie, and would gladly discuss working on one with anyone.

 * * *

> We could try rewriting our app based on valkyrie, plum->figgy style. This actually isn’t too different than the proposal here, we’re still rewriting an app from scratch. Using valkyrie instead of just active_record (and the attr_json gem which is already fairly polished) — it’s not clear to me this will make the development any easier. On the one hand, possibly we’d be able to share more code than just valkyrie with other valkyrie-using institutions — but it’s not entirely clear at this point how much or how mature/polished we can make it. On the other hand, developing on fairly young valkyrie instead of mature well-understood ActiveRecord will, I think, create additional cost, and, in my judgement, additional ongoing cost making the architecture more expensive to work with. If we’re not actually all that excited about ending up on valkyrie (having no desire to be able to switch to fedora), it’s not clear what the benefit here would be.

two things:

1. given the amount of code that will need to be written from scratch for this project, i think it's going to have the same growing pains that any new code has.  and since attr_json is essentially a solo project, it might work well for SHI's uses, but i'm skeptical about how polished and well-suited it really is for anyone else's needs.

2. i don't think switching back to fedora is a big reason to use valkyrie.  i think being able to share code with other people who are using fedora is more important, and having a defined api and clear separation of concerns is a definite improvement.

 * * *

> Even if the project does not reach the level of success desired, in any of the ways outlined above, it might still provide ideas, patterns, approaches, that could influence other approaches in samvera community. In the best case, it could produce re-usable modular components that themselves could even be re-used in other approaches (valkyrie-based and/or hyrax? I’m not certain how plausible that is).

no matter how this turns out, i expect to learn a lot about how a digital collections framework should work, so i expect it to be a productive exercise.  hopefully there will be code that can be shared with valkyrie apps, but even if not, the design work will be informative, at the very least.  i think this is exactly the kind of experimentation the samvera community needs, to explore the possibilities for a lighter-weight framework we could all benefit from.
