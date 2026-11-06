# 2026-11-06 Joint WG/CG Series A

Meeting held 10:00 Eastern Standard Time (15:00 UTC)

## Attendance

- a <trwnh.com> (they/them) (scribing)
- Matthias Pfefferle <acct:pfefferle@notiz.blog>
- Johannes Ernst https://j12t.org
- David Roetzel
- Evan Prodromou
- Jeremiah Lee <acct:Jeremiah@alpaca.gold>
- bumblefudge.com
- Darius Kazemi
- Chris Harrelson

## Agenda

* Administrivia
  * Scribe volunteer(s)?
    *  Ryan and a
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/) and [Community Group Membership](https://www.w3.org/groups/cg/socialcg/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
* Welcome
* Brief introductions as necessary
* New meeting schedule (Darius and Johannes)
  * Monthly:
    Week 1: Series A Joint CG/WG
    Week 2: Series A WG
    Week 3: Series A WG
    Week 4: Series B WG
* WG updates (Darius)
  * TPAC Updates
  * call for WG Decision: New publishing workflow 
    * https://tinysubversions.com/temp/potential-wd-flow.pdf
* CG Chair elections (Dmitri or Johannes)
* [Task force](https://github.com/swicg/meetings/blob/main/DELIVERABLES-TASKFORCES.md) updates (Johannes)
* Any Other Business (AOB)

## Minutes

### New meeting schedule (Darius and Johannes)

Changing to three WG calls + one joint call per month

Two issues came out of TPAC:
* One series aren't well attended
* Will need to do more focused spec work heading up to delivering the first draft in Q1 2027

This will hopefully help!

Johannes: this can be an opportunity for the CG to take a step back, look where we are and decide what our priorities should be going forward, including get back to incubating new ideas. New CG chairs should drive this.

+1s in chat from Ryan, Jeremiah, David

Calendar events will be remade according to new schedule

### TPAC Updates

Main yearly W3C in-person conference! WGs get together in person, work across W3C, etc

Minutes for WG meeting are in w3c/socialwg meetings repo: https://github.com/w3c/socialwg/blob/main/meetings/2026/2026-10-29-WG-TPAC-meeting.md

Big updates for us: planning for first public working draft (FPWD) aka "AP 1.1" in Q1 2027

W3C publishing process encourages iterating on drafts; in consultance with plh the workflow should be automated so that merging a PR results in a new publication on w3.org with the latest revision.

To avoid having to make a WG Decision on every single PR, we can instead make a WG Decision on a generalized process, which was sent out in a Call earlier.

### Call for WG Decision: New publishing workflow 
https://tinysubversions.com/temp/potential-wd-flow.pdf

- Following conformance class changes (1-4)
- Every PR starts a 4-week timer to assign Class 1, 2, 3, or 4
- Class 1/2 changes open a 7-day comment window (including objections to class assignment)
    - With one +1 from members other than the author, plus no objections, we can merge
- Class 3/4 changes open a 14-day comment window
    - With two +1s from members other than the author, plus no objections, we can merge
- Objections pause the window; fixing the objection starts a new 7-day window
- 4-week timer expiring = "no resolution" (unresolved objections AND inadequate 👍s)
- Darius taking on responsiblity of managing this, but will automate as much as possible in future


- Evan: PRs should be linked to existing issues or existing discussion; otherwise on the PR we should have a clear idea of what is the problem being solved. Would like to avoid big PRs that don't go through because of discussion on smaller points
- Darius: Broadly I agree; I'll make a PR template in GitHub to remind people that PRs should be atomic changes that address one thing, but I'll take that under advisement. I assume a 4 week timer will run out if there's too much discussion, so there's a natural incentive to make PRs small so they are more likely to get merged.
- Johannes: What about: no PR except for to address a specific issue that was known before.
- Darius: Maybe, maybe not? It could avoid drive-by PRs with controversial changes
- Ryan: Curious about higher-level Q1 2027 work planning. What do you all think we should do? Where is the WG on a spectrum between "make changes and ship all at once" vs "make changes in smaller windows and ship every Friday (e.g.)"
- Darius: Q1 can be spent iterating; attempting to hit Candidate Recommendation (CR) by end of Q1 will necessarily constrain what goes into the draft. Goal is still to push only for Class 1,2,3 and no 4 changes. Maybe a 1.2 document...?
- Ryan: Goal is to get something out, not to do all the work? Just to have something to show other people?
- Darius: Yeah, in addition we have other workstreams for e.g. combining AS2-Core and AS2-Vocab as we loosely committed to in other meetings. (Edited to add: we actually made [a formal WG decision to combine AS2 and AS Vocab](https://lists.w3.org/Archives/Public/public-socialweb/2026Jun/0001.html).)
- bumblefudge: do we need a test suite by CR?
- Darius: We need it at the end of the CR process as we're moving into REC. Maybe end of Q2? ~6 month deadline let's say for the new WG Test Suite TF
- Johannes: Categorize issues into blocking vs non-blocking? Just a thought... "These 5 things absolutely have to happen" vs "These can happen later". Also, I like the process but is there any way of speeding it up? It looks like PRs can take on the order of months, and do we have that many months?
- Darius: +1s are meant to fast-track changes, but we need to make sure there is a reasonable window for objections in all of these scenarios. Objections being resolved starts a 7-day timer for example. "longest" PR should take ~5 weeks from start to finish, but an uncontroversial Class 2 could be closed within 7 days and an uncontroversial Class 3 could be closed within 14 days. Our job is to be right (as possible), not to be fast (despite our sense of urgency). As Chair it is important to me to have a real sense of legitimacy with every change we make and a real chance for people to comment or object if necessary.

PROPOSED: new publishing workflow, 
https://tinysubversions.com/temp/potential-wd-flow

Straw poll in chat: +1s from Jeremiah Lee, Johannes Ernst, David Roetzel, Chris Harrelson, bumblefudge, Matthias Pfefferle, Evan Prodromou, Ryan Barrett; no objections

RESOLVED: new publishing workflow, https://tinysubversions.com/temp/potential-wd-flow


### CG Chair elections

Johannes: Wanted Dmitri to help run the election to be more impartial; otherwise maybe Darius can help run it. Process is a bit vague beyond what we have in our charter.

Evan: We have 3 self-nominations, so it would be great to run an actual election. Structure allows chairs to nominate co-chairs as well, so we could in theory elect 1 chair and have them nominate co-chairs.

Johannes: I read that the CG can elect chairs or co-chairs, so the proposal makes sense, if we have 1 chair that can appoint co-chairs then that could be better than appointing chairs who are at odds with each other (?)

Darius: Similar to how US Vice President used to be elected separately from President and would obstruct them?

Johannes: Chair status gives you access to W3C site and calendar

Darius: Either way, -1 to doing it right now; we don't have enough participation in this meeting. Better to use the CG mailing list and do it completely asynchronously.

### [Task force](https://github.com/swicg/meetings/blob/main/DELIVERABLES-TASKFORCES.md) updates (Johannes)

#### Geosocial

- Jeremiah: Recap of FediForum session; notes merged
- Evan: last discussion was about our explainer and if we want to do a CG report at this point

#### HTTP Signatures

- Ryan: Good opportunity but TF isn't active right now.
- Evan: In our last meeting I volunteered to work with you on reactivating for RFC 9421 support. Momentum on adopting RFC 9421, so writing a document is a good idea. Cna we put a meeting on the calendar for November?
- Johannes: Keep it in the table for now and hope to start it up again? What's a good 1 sentence summary?
- Ryan: Seeing who in fedi has adopted it, updating the report to document double-knocking, tracker for adoption?
- Evan: Sounds great, current report is currently Cavage focused, but a next version might put them on equal footing or put RFC 9421 above.

#### Website

- Johannes: Meeting next week. Want to point out, single most important question is a tagline, on the front page, we need to say "what is ActivityPub for". if i hear about AP and go to the site, what should I see? We have an issue with suggestions. https://github.com/swicg/activitypub.rocks/issues/97

#### API

- Evan: seekItem wants to move to CG-DRAFT https://swicg.github.io/activitypub-api/seekitem

#### Discovery

- Evan: last meeting was productive; maybe next meeting we can discuss going to draft

#### E2EE

- Evan: MLS support into browsers? Takes a lot of complexity out of doing it in AP. Two big issues came up: repudiability ("i never sent that message"), which conflicts a bit with moderation; another is developing a threat model to figure out if the spec meets our needs as a group. Probably looking at Q1?
- Darius in chat: someone from Mozilla at the e2ee meeting whose major comment was: "I am here to make sure you're using MLS. You are. Good job." Mozilla-authored explainer for an MLS Web API https://github.com/mozilla/mls-webapi-explainer/blob/main/MessagingLayerSecurity.md
https://github.com/mozilla/mls-platform-api

#### Portability TF 

BF (In chat): Portability is pretty much in maintenance mode awaiting implementer interest on LOLA and on the various FEPs. Please reach out to me and/or Lisa D if you are thinking about putting LOLA or account export on your feature timeline, implementers! We will spin up meetings on whatever cadence and timezone works for you 

#### Testing TF (WG)

BF (in chat): Testing TF is... also awaiting volunteers haha. Reach out to BF

#### Groups

- Evan: Follow and Join activities being distinct. Permissions; implementation matrix being tracked by mayel from Bonfire

#### Remix

- Evan: Awaiting (?)

#### Trust and Safety

- a: https://swicg.github.io/activitypub-trust-and-safety/sensitive/ got merged, probably can move to CG-DRAFT soon

#### miscellaneous

- Evan: Part of the work is exploring the problem area, we don't always know what the deliverables will look like.
- Johannes: so maybe table should include "areas of discussion"? Considering asking TF leads to provide their own status updates with PRs each month.

### Any Other Business (AOB)

none
