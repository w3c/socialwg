# 2026-08-20 Joint WG/CG Series B

Meeting to be held 19:00 Eastern Daylight Time (23:00 UTC)

## Attendance
 - Darius Kazemi, WG Chair
 - a <trwnh.com>
 - [Johannes Ernst](https://j12t.org)
 - Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
 - Ryan Barrett <snarfed.org>
 - Philippe Le Hegaret <plh@w3.org>
 - Dmitri Z.
 - Mark Corbett Wilson
 - Liam Roche
 - Philip Mallegol-Hansen
 - Lisa Dusseault
 - Wibi

## Agenda

* Administrivia
  * Scribe volunteer(s)? a, johannes
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/) and [Community Group Membership](https://www.w3.org/groups/cg/socialcg/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
     * Sign in under Attendance please
* Welcome
* Brief introductions as necessary
* Discussion of CG Drafts (Evan) ([ref](https://lists.w3.org/Archives/Public/public-swicg/2026Aug/0042.html))
  * [Tracking table](https://github.com/jernst/meetings/blob/pr-tf-table/DELIVERABLES-TASKFORCES.md) (Johannes)
  * HTTP Signatures Report consensus update
* WG updates (Darius)
  * Miscellany Terms update ([discussion](https://github.com/w3c/socialwg/blob/main/meetings/2026/2026-08-14-WG-AP-suite.md#miscellany-terms), [CfC](https://lists.w3.org/Archives/Public/public-swicg/2026Aug/0066.html)) (Darius)
* Task force updates (Dmitri/Johannes)
* Any Other Business (AOB)

## Minutes

### Process to produce CG-DRAFT and CG-FINAL reports

* Discussion of CG drafts. Some references in the agenda. Thread that Evan started on process (see above)
* Evan:
    * Main output of CG are reports, two stages: 1) Draft, maybe multiple 2) Final.
    * We have 2 Final reports and 3 Draft reports
    * Example: AP + Webfinger: created TF, appointed editors, iterated over draft, straw poll in CG meeting, then published as Final
    * Then we had explosion in TF and deliverable reports. Also changed charter.
    * Have not published reports for a year or two. Not sure exactly why.
    * Did a search and found 23 documents in process. But don't have a clear process to get from there to final report.
    * Proposed light-weight process in e-mail
        * Different stages: when good for implementors to start implementing, when there are no outstanding issues so it can be final etc
        * TFs produce drafts, CG take it to final
* Johannes: We have a table of task forces and deliverables but I am not sure how up to date it is. I put it in the meetings repo so that when task forces have meetings, we can update the table at the same time. Would be useful to have a better view of what is going on at any point.
* Darius: Are you volunteering to maintain it as CG chair? Responsibility of chair?
* Johannes: Reasonable to assume!
* Evan: Agree, but also TF leads should be involved here.
* Darius: Seems like people are in favor of this process and we should probably go ahead and make this exist? People can comment on the PR if they notice anything wrong/missing/etc.
* Evan: I want to make clear that there should be a more formal process than just github PR to the table. 
* Darius: table for managing info, but outputs go through CG mechanisms
* Johannes: TF leads, please compare your own outputs with the results of Evan's search through repos.
* Darius: I recommend reaching out to specific authors, maybe send to mailing list but also reach out 1:1
* a: TF leads should announce existence of Draft reports and bring Final reports to CG for 2-week CFC on publishing them
* Darius: Can Evan write this up formally somewhere and bring it to mailing list?
* Evan: That sounds great! Will do.
* Darius: Relatedly, we have Ryan's HTTP Signatures report and let's check in on that.

### Discussion of HTTP Signatures report

* Dmitri: It should have been published by the CG years ago but fell through the cracks.
* Darius: Process at the time agreed to publish it, we just never did.
* Evan: need to do more work on HTTP Signature
* Ryan: Written in early 2024 and finalized in june 2024, best to think of it as a "snapshot in time" and not current best practice. Like Evan said, we should probably restart the TF as well.
* Darius: Good opportunity to reach out and ask for participation to write a new report.
* Johannes: Do we have consensus that this gets published as FINAL from 2 years ago, then announce this on blog? Is someone going to shoot me for announcing it?
* Darius: Consensus was already reached years ago so go ahead and fix this "secretarial error".

ACTION ITEM: CG chairs to publish FINAL HTTP Signatures report but backdated, then announce this via appropriate venues

### Miscellany terms

* Darius: WG wants to adopt Miscellany terms, issue CFC to CG; issues with miscellany have since been resolved; is the report ready to be published as a FINAL report by the CG so that it can move up to the WG?
* Johannes: Asking for consensus, or...?
* Darius: Important that there are no objections to this, WG wants the CG to move forward first.
* Evan: Quick talk about what miscellany terms are -- 4 terms popularly used by implementers (manuallyApprovesFollowers, sensitive, movedTo, Hashtag) and they were placed in activitystreams namespace erroneously by early implementers. But a WG could integrate these terms into official spec.
* Darius: CG making this a FINAL report gives WG path to adopt these terms.
* Johannes: Evan, where are we in your process for CG reports?
* Evan: Entertaining a proposal for CG-FINAL, has been in draft state and issues cleared. Terms widely used even without the context document. Widely reviewed.
* Johannes: CFC to mailing list vs straw poll right now? Probably best to put a DRAFT on the website right now and move to FINAL in a couple of weeks.
* Darius: I put out a CFC and the intent was to be done with this 2 weeks after; so far it's been a week and I guess we have another week
* Johannes: I suggest we redo the CFC wrt the CG chairs publishing it, with clear deadline and so on.
* Evan: Sure, good plan.
* Darius: Good plan.
* Evan: Johannes, let's go through process after meeting to get the DRAFT published and then issue CFC to FINALize it.

### WG updates

* Darius: We have been continuing our read-through of the spec and gotten through a bit further.

### TF updates

* Johannes: Can we go through the table and see if it is up to date and it makes for a good process?
* Darius: Sure

#### API TF

* Evan: Level 0, Level 1, Level 2 being discussed.
* Johannes: Deliverable?
* Evan: Two deliverables: 1) Basic profile, 2) Level 1. Basic profile is in draft right now but we just decided to do Level 1.

#### Data Portability TF

* Lisa: Some wrinkles ironed out. Anyone with updates or news regarding LOLA roadmap? I think it's ready.
* Johannes: There are 2 deliverables, right? Table says LOLA but links to index file https://swicg.github.io/activitypub-data-portability/lola.html
* Johannes: OK we can fix this
* Lisa: One document talking about requirements, one document for LOLA. Don't know if process document is relevant or still needs to be a deliverable.
* Johannes: What should we publish on the website? Sounds like if it's relatively stable then we can put out a DRAFT
* Lisa: Leave it to CG/WG call

#### HTML Discovery TF

* Evan: Document in async production for a while, ready for draft review and implementation.

#### E2EE TF

* Evan: Previous joint meeting had report.
* Johannes: Draft? How far away from final?
* Evan: Close to end. MLS Draft is out, has been implemented by 2 servers (Emissary and Bonfire) showing interop. Update to MLS document based on their implementation experience. Process getting through issue backlist and deciding in or out. Refinement process at this point.

#### Forums TF 

* a: Julian is TF lead and has decided to do all-async. Maybe reach out to Julian regarding deliverables?

#### Geosocial TF

* Evan: Two docs. 1) Personal places, maintain a list of places that are important to you. 2) Report on geosocial microsyntax, ways to tag content to a specific place, specific syntaxes under discussion. How do we do checkins and so on is still open.

#### Groups TF

* a: got Groups draft report, very early, but it exists and contains the agreements so far. https://swicg.github.io/groups/ 
* Johannes: please provide a summary for the table
* a: will do
* Ryan: how are groups different from forums
* a: Groups is for people, Forums is for posts and threading

ACTION ITEM: Provide a summary

"Participating in group contexts with specific members and other community affordances"

#### Handles TF

* Darius: Anuj sends regrets, will be at next meeting
* Evan: Repo exists now, when do we have the first meeting?
* Johannes: IMO Anuj calls this as TF lead, talk to me and get it on the calendar

#### Remix TF

* Evan: Bob and I are coleading this, we had a meeting last week, remix and aggregation is how to take activities from multiple sources and organize into a single feed/set/etc. Assembling user stories right now regarding search, hashtags, actors. Looking at how we can publish sources and criteria for an aggregated feed. Next work is to assemble explainer and report

#### Trust and Safety TF

* a: One possibly candidate to step up as TF chair. Emelia is trying to figure this out.
* a: Overview is a living document and may not want to be published as draft. But other Draft Reports documents are listed in the index document and figure out the deliverables from there section 3.

#### Website TF

* Johannes: Links on front page of CG page have changed recently, linking out to activitypub.rocks and so on. Please let us know when you have anything interesting to say so we can publish it!

#### Extension process

* Evan: What we expect from TF outputs is to take reports and make them extensions when ready. For now example to test the process was the miscellany terms, but now that we have moved forward on miscellany we can move forward on this.
* Johannes: CFC for extensions policy after miscellany is FINAL?
* Evan: Yep

#### Previous

* Evan: HTTP Signature was never closed/completed, still want to do RFC 9421 report.

### Any Other Business

* Darius: Anything?
* Darius: OK, looks like we had a efficient and productive meeting today! As always, everyone keep an eye out on the mailing list and for upcoming meetings. Next week we have another AP suite WG meeting. See everyone else in a couple of weeks!
