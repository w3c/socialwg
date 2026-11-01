# Social Web Working Group TPAC 2026-10-29
Held 11:30 GMT in Dublin at TPAC

## Present
- Darius Kazemi, Chair
- Aram Zucker-Scharff (The Washington Post)
- Matthias Pfefferle <acct:pfefferle@mastodon.social>
- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- Philippe Le Hegaret (plh)
- a <trwnh.com> (they/them) (scribing)
- Muadh Al Kalbani (Samsung)
- David Roetzel
- Benjamin Case
- Brian Dipta
- bumblefudge.com ( https://identity.foundation/ , DID Methods WG)
- Chris Harrelson
- Sarven Capadisli <https://csarven.ca/#i> ( @csarven@w3c.social ), TAG

## Agenda

11:00 - intro, administrivia
11:15 - getting to First Public Working Draft
12:00 - conformance test suites

## Notes

- CLA, CoC
- Introductions (see [Present](#present))
- Slides: https://github.com/w3c/socialwg/blob/main/meetings/2026/2026-10-29-TPAC-Slides.pdf

### FPWD

Darius: Specs reached REC status in 2018 but WG did not exist to maintain them until January 2026 rechartering. CG exists and some work can be elevated to new WG.

... revising an existing spec. Changes can fall into various classes.

- 1 = no change to text (broken link or stylesheet)
- 2 = no change to conformance (clarify non-normative text or fix typos)
- 3 = no new features (expand or contract requirements to make something conforming or non-conforming)
- 4 = new features

... Accumulated many changes so we want to push for a working draft that can be reviewed.

... We don't need to worry about Class 4 or formal objections at the moment; need to make a WG decision and field internal objections. Some class 3 changes exist; we need to document those. Lower-class non-substantive changes can be made without highlighting them.

... FPWD getting ready will trigger a horizontal review.

... Plan to get there: publicly document changes so people can refer to them. Then make the WG decision and request approval. Documentation should take a few weeks (?), then horizontal review might take a few months.

PLH: Providing links to github commits can suffice, but it's not ideal by far. Best case scenario we have a list of changes for the TAG to look at. Horizontal review can be triggered automatically. Unless we have something specific for them to look at, this should suffice with one caveat: the Web has changed since 2018. Trying to move forward without new security and privacy review will not work; needs a re-review with a fresh eye, not just the changes. At minimum we need Step 2 here, make the WG decision.

Sarven: {Talks about TAG's Explainer} Not looking at minute details of solutions but we want the use cases to be clear and the problems being solved to be clear. In addition to threat models and other such things helps with review. Personal feeling, there are no show stoppers. Can only suggest to not punt to a later stage; get it out and get quick feedback. 

Darius: [...]

bumblefudge: How do we help make sure things are in or out of scope?

PLH: Explainer https://w3ctag.github.io/explainer-explainer/#introduction will require some substantive work; security reviews now include trust models. At some point we need to deal ...

Evan: Are we absolutely sure we don't want Class 4 changes? New terms from miscellany count as Class 4 changes since they're new features.

PLH: If it's in the spec then great, if we're still talking about it then we can wait a little.

Darius: In interest of getting to FPWD we can maybe hold off on that at first then re-evaluate later with another WD. Don't want to be stuck without a draft for another 3 months.

David: So far we talk only about AP, but what about AS2? While on the subject -- earlier we had a vote to combine AS2-Core and AS2-Vocab, does that need to go through same process?

Darius: Different bucket of work for now. Discuss in future meetings.

PLH: Want the group to consider "automatic publication" on every commit to the documents. Makes life easier because of automatic tooling on GitHub actions. Removes the question of "when do we publish" but we need to get to FPWD.

Evan: Sounds like we're holding off on Class 4; focus on AP right now; look at AS2 going to FPWD in Q1 2027?

Darius: Yes, once AP is FPWD I want to look at spinning up AS2 to FPWD.

... Do we need to get a new WG decision for each draft, or...?

PLH: Maybe a +1 or +2 can lead to PR being merged. Avoid things being published that we never wanted to publish.

Darius: instinct as well, we can have a WG decision something like "merge PRs with editor and chair approval"?

PLH: Publish "at will"; Web Apps WG is using a decision from 2016 that they still point to today.

Sarven: Some form of a decision URL can help. Document that the decision happened in a linkable format.

PLH: Make it as easy as you can.

Muadh: README close to an explainer?

PLH: It needs to be an explainer.

Chris: FPWD isn't blocked on an explainer; group just needs to decide to do it and the explainer can be done in parallel.

Darius: I want actual consensus and not say we are under time pressure. WG needs to make an informed decision while understanding the scope of all changes we want to make.

PLH: Question 1: What information do we need to make the decision. Question 2: Charter says async. Need to issue a CfC even if we make a provisional decision today.

a: practical process for choosing issues to address in FPWD?

Evan: Suggest that Class 1 and Class 2 can be handled with PR +1, no need for a full CfC on typos or broken links.

PLH: Class 2 changes can sometimes be Class 3 in disguise.

Darius: What about "uncontroversial" Class 2 changes?

Chris: PR + 1 seems fine for Class 2.

a: I'm less concerned about the publishing time window and more concerned about the *review* time window. We should review PRs more frequently so that PRs don't stall or get stale for a very long time.

Evan: I can commit to checking on PRs within 4 weeks. Let's add PR review to Friday issue triage.

Darius: Change up our WG agendas from this point on, we can finish up our readthrough but I'd like dedicated time for open PR discussion to close things out.

Evan: Reason I would like to have quicker resolution for PRs because trivial changes are taking a long time to resolve. Need to explain why it's important for the group to review it, then actually review it. Spelling errors are usually a "yeah this looks fine".

Darius: Bringing PRs to the WG meetings should alleviate the problem of PRs never getting looked at.

Sarven: Thre is https://www.w3.org/guide/editor/ that gives guidance and quite a bit of liberty to editors to make changes w/o having to drag the whole group to every minute change.

PLH: Caveat: Can't force a change through. Bypass in 2 ways: admin rights, or subset of PRs can go into a different queue for automatic approval.

Darius: 1st week November WG meeting, concrete proposal re: moving to FPWD and which changes to bring in at a high level, and agreeing to publish in XYZ fashion. Set of publishing rules and guidelines.

### Test suite

Darius: We're not making Class 4 changes and very few Class 3 so we don't have much in the way of a test suite, but we do want to eventually move beyond the "minimum viable test suite" to include 1.0 functionality. We're going to need it later anyway.

bumblefudge: Process is a bit squirrely since we can't link PRs to how they change a consensual test suite. How do we measure conformance? We need a way to measure conformance. Ideally each spec change PR could include a test case change if appropriate.

Evan: in terms of testing we can look at AP sections 3, 4, 5 for the "relatively easy" part to test, it is read-only work using HTTP GET. Two complications: authenticated GETs don't define a method for authentication. Typically HTTP Signature profile? At least refer to profiles. As we move into section 6 and 7 it gets harder to test, though not impossible, per-profile (e.g. testing codepath fork to profile AuthZ choice). If we can get a test suite for 3 4 5 that's a good progress. For 6 we'd need to add in an OAuth profile.

Aram: I wouldn't want to approach this as a PR-by-PR process, we might want to bundle several related changes related to a single mechanism. Wait a bit until we get to writing tests.

PLH: Web Platform Tests can be run on every push, for example.

Chris: No tests right now, correct?

Darius: Correct.

PLH: Framework for running tests. Other groups write documents and rely on vendors to run their own tests.

bumblefudge: We have a couple proposals for the framework. How to harness it, the middle steps that implementations need. We have "pieces of test suites".

Chris: Artifacts not currently working, right?

Evan: Built by other groups. At least 3 test suites for AP -- 1st was built by Christine that was a text adventure game asking yes or no questions if you succeeded. We had 10 or 12 passing implementations. 2nd is the one by Juan, Ben, Dmitri; extracted SHOULD/MUST/MAY but doesn't have a test driver to run the tests against an impl.

bumblefudge: It tells you how to do it via HTTP. Kind of "curl based". Very JSON-y. An implementation is just "something that returns JSON" basically.

Evan: 3rd test suite, pragmatic, by Johannes Ernst, takes various AP implementations and launches them as Docker containers, but it doesn't test to the spec, it tests to the implementations.

Sarven: Maybe that needs to be picked up, that approach should be kept in mind?

PLH: Without understanding the point of testing it is useless to test, chicken and egg problem. A lot of stuff already that may or may not have tests, at the minimum you need a label that says "this PR needs tests". First step is we add such a label, maybe even going back in time and looking at past changes. Ideally useful to vendors as well, not just W3C. Put the right people in the right room to tell us what we should do, then tweak as needed.

Darius: a WG TF for a test suite could be called for, it's probably not productive to have the mainline WG time taken up by testing. Process-wise I'm not sure if a chair can just make a TF or...

PLH: Yes.

Darius: Great! I'm using my chair power to create a WG Testing TF; Juan, can you run it since Evan is already running too many?

PLH: proper way is to ask for objections first :)

Darius: Any objections?

Evan: I'm in favor

Darius: I don't see objections on Zoom -- Juan, are you willing?

bumblefudge: Yeah

Darius: I plan to be in these meetings, don't want too many TFs in the WG like we have in the CG.

Chris: Do we have involvement from people at large?

Darius: Maybe can rope some people in if they are willing. Johannes is a WG member already.

Chris: TF should be scoped for harness and framework

Darius: I think you're correct. Making the tests is important but not the primary work; create the infrastructure first.

Chris: Is there a particular implementation we can test against?

a: careful not to test for implementation quirks vs features of the spec?

Darius: If someone makes a test suite we want to have a starting place at least. We're probably not writing that many tests so it hopefully shouldn't be a huge issue.

bumblefudge: Everything between implementation and protocol is out of scope, so what can you test about what the implementation is "thinking"? You can only test the HTTP boundary.

Darius: I trust the test suite builders to not bias toward any specific profile/implementer. Lots of non-AP differences that need to be dealt with before testing AP, I would just hope that the framework put together would allow for multiple "glue layers" here.

Chris: in Web Platform Tests there is a concept of web "drivers" for Chrome, Gecko, Webkit, etc. so maybe a Mastodon "driver" etc etc can make sense here.

Darius: Good discussion about testing, thanks again to Juan for taking on the WG Testing TF work as well. We technically need this before REC. Talking about months, not weeks. Still room for discussion on this. If you're worried about the TF and its works then I encourage people to attend the WG TF meetings.

### Closing notes

Chris: can we resolve on specific methodology for FPWD?

Darius: It's so tricky that I'd like to put it to the mailing list instead, actually.

bumblefudge: Not just the spec but also talking about vocab and context.

Chris: Isn't that part of the spec?

a: Context is kind of a "living document"; ontology is non-normative; the source of truth is the specs themselves.

bumblefudge: I'm bringing this up because people cache context files for a very long time.

Darius: it's clear we need to discuss this more as a group.

PLH: Create a Github issue in the WG repo about this issue to make sure it's added to the agenda.

David: AS2 context is used; AP context is not used.

???: Mark the AP context as archived?
