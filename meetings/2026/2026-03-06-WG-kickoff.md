# Social Web WG, 2026-03-06

* Chair: Darius Kazemi
* Scribe: 

Call-in details: see https://www.w3.org/groups/wg/social/calendar/

Charter: https://www.w3.org/2026/01/social-web-wg-charter.html

# Attendees (please add yourself)

* Darius Kazemi, independent, Chair
* Evan Prodromou, Social Web Foundation <acct:evanprodromou@socialwebfoundation.org>
* Lisa Dusseault, Data Transfer Initiative (@lisarue@mastodon.geekery.org)
* Andy Piper, Mastodon @andypiper@macaw.social
* Aaron Parecki
* Dmitri Zagidulin
* Steve Blackmon
* David Roetzel, Mastodon
* Eugen Rochko, Mastodon
* Philippe Le Hegaret, W3C
* <a href="https://csarven.ca/#i" rel="schema:attendee">Sarven Capadisli</a> (Invited Expert)
* Tantek Çelik, Mozilla, https://tantek.com/

# Agenda

* Administrivia
  * Scribe volunteer(s)? Lisa
  * Reminders: 
    * [Working Group Membership](https://www.w3.org/groups/wg/social/)
    * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
    * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)

* Welcome, and overall mission, scope, and purpose (Darius)
* Brief round of introductions
* Proposal for WG meeting structure and cadence, including internal comms channels (Darius)
* Iteration goals for ActivityPub, ActivityPub suite errata (Evan)
* LOLA next steps
* WG membership discussion: who else should be in this room? (open)

* Any Other Business (AOB)
    * WebSub bug report
    * Breakout Days (https://github.com/w3c/breakouts-day-2026/)
    * https://github.com/w3c/ns/pull/11

# Notes


## Administrivia

Darius: This is our kickoff meeting and as such will be a bit unusual. We are focused on getting consensus on how we are going to get work done, and some consensus on high level goals. We won't be giving updates on work today except to further discussion of getting work done.


Reminder of W3C WG meeting processes, code of conduct linked above.

Scope: recent recharter means we're able to publish normative Notes and specifications, unlike the community group. We could decide to change our scope but want consensus on scope/focus.  

## Intros

*Participant intros (see above for participants)*

## Cadence of work

Darius: I propose we initially model our work style and cadence on that of the federated identity WG.  They're a highly successful WG, they get a lot of work done. They have a vibrant community group that works alongside the WG, and our incubation process in our charter was drafted based on theirs.

Fed ID work process: https://github.com/w3c-fedid/meetings/

Our charter: https://github.com/swicg/potential-charters/blob/main/stage-process.md

Broadly speaking, ideas percolate in the CG, then the CG & WG together *can* conclude to shepherd the work along in the WG.

Evan: We may also have FEPs, task forces, indieweb work; but by the time we get to WG stage we're talking about finalizing and more formal work. 

Darius: Also test suites and such fall in the WG.  But novel ideas presented to the WG will likely get directed to the CG for analysis and buy-in.  Since we're working closely with the CG, I propose many of our meetings should be joint meetings - like FedID, who have a certain number of closed-door meetings but also joint meetings WG+CG.  Cadence could be monthly or every other week, contingent on agreement with CG.

Dmitri: Sounds good. We're trying to walk the fine line between openness and process in a rough landscape. Let's go with joint biweekly. 

Evan: We very often overrun the CG timeslot monthly so it would be good to have more time via biweekly meetings.

Andy: Agree and to highlight, Mastodon just joined W3C and we have 3 people here now to kick off our participation.  We're ALL in Europe.

Darius: FedID has A meetings and B meetings, at different times to accomodate people around the world.  We may have a track at this time (9am Pacific) but also another time. There are many Japanese users of ActivityPub and people there are interested in participating. 

PLH: Consider using Zoom, because it has translation services.

Darius: Yes - while we do love our open tech (jit.si), reducing barriers to participation is also important. 

Along with meetings and email (which is a black hole for some people), I'd like to think about participation channels. Chat can be real-time and ad-hoc. The W3C Slack is my proposal. 

Tantek: The W3C slack is fine for informal. My counter-proposal is to use #social IRC channel on the W3C IRC server.  We were able to use that successfully in the first WG iteration and we do have a continuous archive running the whole time. https://chat.indieweb.org/social 

Darius: Is it bridged to Matrix?  TBD

Sarven: History is lost in slack channels after some number of months. I presume we have our main work preserved in GitHub.

Darius: Loss of history makes slack a non-starter IMO.  We'll look into the other options.

Dmitri: The other option is not to use chat at all. What do we traditionally use chat for?  Meetings, polls, minute transcriptions. Each one of those can be used for something else.   We also have to figure out transcription approaches, which is a pain point in many groups.  

Darius: Moving on as Evan suggested, we'll follow up on this. 

## Iteration goals for ActivityPub

Evan: We have goals in our charter for iterative changes to our documents for 2026, around six months from today. We would be going through the various recommendation processes, so I assume we need drafts before that.  I think we can make some changes to these .1 versions (ActivityPub 1.1, ActivityStreams 2.1).  WE've been tracking errata for years. We have 14 AP errata, 23 AS errata; typically text.

I propose to adopt our editor's drafts as WG editor's drafts. 

We should also (in addition to errata):
* add more examples to AP
* update Activity Vocabulary to to AP
* fix use of RFC 2119 terms
* revise text for clarity
* define terms better
* define conformance profiles
* decide which issues marked 'next version' to include 
* Reference OAuth, HTTP Sig and Web Finger features that are widely used

I would like to maintain backwards compatibility so that developers can keep working from existing specs rather than lose momentum.

If we have non-backwards compatible work, open question whether we work on major new versions of AP/AS. 

Darius: Yes - not to determine now in this meeting what's backwards compatible, but to work it out in discussions.  We have a short runway for this WG but it's possible to discuss future work.

Evan: we have 100 implementations. WE'd have to show serious benefit for non-backward compatible changes.

Darius: Highlighting the work done in the CG on the C2S API by Evan and others, I've seen a lot of interest in that lately.

PLH: We only need a CFC on the mailing list to adopt a draft. What's our merging policy - how many people does it take, do we want to review every PR including typos.  I recommend a minimum # of +1 on a GH PR to merge a typo PR, unless it's substantive in which case we trust editors to bring to WG.

## LOLA next steps

Darius: LOLA is our draft for live transfer of data between accounts. It's listed as a charter deliverable.  

Lisa: It's being implemented by two implementors, it does have open issues but it would be good to solve those open issues with WG process.

Darius: In that case we can do a CFC to adopt this.  

## Calls for adoption (Darius)

Proposal: Adopt the SocialCG drafts: ActivityPub, ActivityStreams core, and Activity Vocabulary as WG editors' drafts. 

Resolved: Adopt. Straw poll indicated yes; bring to mailing list for confirmation.

Proposal: Adopt LOLA unofficial draft as a WG Editor's draft

Resolved: Adopt.  Straw poll results in tentative approval to be brought to WG list for confirmation.

Also will loop in CG on these items.

## WG membership discussion

Darius: Who else should be in this room? WG membership may be as a W3C member or as an invited expert. I've got interest in invited expert status.  We can also look at which W3C member orgs ought to be in this room, e.g. news publishers.  We may be able to make the case and persuade folks to join.

Sarven: What are the gaps the group has? focus on filling gaps. E.g. if this group has anybody interested in investing in test suite development, we should be sure to cover that. 

Evan: It's important to extend invitations to the authors of AP and AS (names provided).  None have been very active lately, but important to extend invitation as a courtesy.  I suggest Abdullah T., goes by 'a', they/them; very detailed, focused reviewer of all of these specs. 

Tantek: I like what's been proposed. Since our charter is focused on maintenance changes, some of the most important invited experts are implementors. They will have the best perspective on when to fix the spec to align with implementation, and when to fix implementations instead.  Manton Reece has implemented most of our specs.  

Tantek: I also want to propose to reach out to Meta. They contributed to the earlier WG, they have Threads, they contributed to tests. 

## Any other business

# Action items

* Darius and Dmitri to set up joint meetings with alternating times
* Darius to email WG list about comms between meetings
* Darius to send CFC for LOLA WG Editor's Draft proposal
* Darius to send CFC for SWICG drafts: ActivityPub, ActivityStreams core, and Activity Vocabulary as WG Editor's Drafts
