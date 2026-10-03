# 2026-09-17 Joint WG/CG Series B

## Regrets
- Darius Kazemi, WG Chair

## Attendance
- Johannes Ernst j12t.org, CG co-chair (filling in for Darius today)
- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- a <trwnh.com>
- Victor Hernandez Guzman <contact@victorh.dev>
- Lisa
- Liam Roche
- Chris Harrelson

## Agenda

https://github.com/w3c/socialwg/issues/22

1. Administrivia
   * Scribe volunteer(s)? 
   * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/) and [Community Group Membership](https://www.w3.org/groups/cg/socialcg/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
     * Sign in under Attendance please

1. Welcome and brief introductions as necessary

1. [Breakout sessions at TPAC](https://github.com/w3c/tpac2026-breakouts) (Evan)

1. WG updates (Dmitri/Evan?)
   * FYI: [Server-to-Service Content Delivery proposal](https://github.com/explainers-by-googlers/activitypub-service-content-delivery) submitted by Google to the WG in [last meeting](https://github.com/w3c/socialwg/blob/main/meetings/2026/2026-09-11-WG-AP-suite.md), see also [this issue](https://github.com/w3c/activitypub/issues/620)

1. Task force updates
   * [Tracking table](https://github.com/jernst/meetings/blob/pr-tf-table/DELIVERABLES-TASKFORCES.md) (Johannes)

1. Discussion of CG Drafts (Evan) (ref)

1. Any Other Business (AOB)

## Minutes

### Introductions

- Victor Hernandez Guzman: trust and safety lead (contact@victorh.dev / https://www.linkedin.com/in/victormhdz)

### Breakout sessions at TPAC Dublin (Evan)

- Breakouts for our task forces
- Overlapping breakouts
- Special topics?
- Data portability?
- Joint breakout session on identity?
  - Identity On The Web https://github.com/w3c/tpac2026-meetings/issues/62#issuecomment-4723363296
- Evan will propose some sessions

### WG Updates

#### Google proposal

- Liam: brief recap of what they are proposing
- Evan: if we were to standardize a protocol (such as a relay) the CG should probably do a first pass on, with a report. But what I'm seeing here is a very narrow proposal, which I don't feel rises to that level
- CH: has been implemented previously
- Liam will create a PR. Scope is about two changed sentences.
- Evan: merge next week's meeting? 

#### Other

- Evan: Been doing deep-dive reviewing, coming close to end
- Evan: can we have a number of changes ready for TPAC?

### Dmitri

- Stepping down as co-chair to focus on implementation
- JE: well-deserved rest from great work!
- JE: reactivated CG, taskrces going, CG charter, WG charter, producing reports, 
- JE: this is too big a job to do by himself, wants to volunteer others


### CG / Task Force updates

* JE: thinking of adding non-TF status to the table, e.g.
  special event on identifiers this week
* Evan: impact is a few changes to the AP 1.1 draft 

#### API

* Evan: API: profile of AP + OAuth Client Auth + a few other things (CORS, rate limiting)
- Not moving basic profile forward to draft yet
- Identified volatile parts of the spec, want to provide more information
- MediaUpload, proxyUrl new docs
- draft blocker label
- POC implementations for seekitem, sse, autocomplete
- Seek editor for RARs document

#### LOLA

- JE: CoC is still open, but no comments / objections so far
- Evan: implementations are crucial
- Lisa: have Emissary and AP Testbed

#### HTML discovery

- Evan: No consensus yet to move to CG draft
- Disagreements are largely editorial

### Geosocial

- EP: 
- Microsyntax: 
- Can we do realistic geotagging using named hashtags?
    - hashtags from tags.pub for Canadian locations
    - ~80%

### Trust and Safety

- VHG: stepping up as co-lead with echo
- Best practices draft under development
- New leadership: https://github.com/swicg/activitypub-trust-and-safety/issues/167

### Web

- JE: Moving to Hugo!
- JE: fedidevs.org should redirect or get merged?

### Remix

- New explainer: https://swicg.github.io/activitypub-remix/

## CG Drafts

- Process noted in CFC on the mailing list: https://lists.w3.org/Archives/Public/public-swicg/2026Aug/0105.html
- CFC passed!
- Add to swicg/general
- Link to staging process (related)

