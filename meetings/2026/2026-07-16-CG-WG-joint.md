# 2026-07-16 Joint WG/CG Series B

19:00 Eastern Daylight Time (23:00 UTC)

## Proposed Agenda

* Administrivia
  * Scribe volunteer(s)? (Johannes with help from others)
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/) and [Community Group Membership](https://www.w3.org/groups/cg/socialcg/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
* Welcome (Dmitri / Johannes)
* Brief introductions as necessary
* Task force updates (Dmitri/Johannes)
* WG updates (Dmitri)
  * New WG draft meetings are scheduled
* ActivityPub Stack 2.0 - how/where/when should we discuss this? (Johannes)
* (Johannes) CG Website TF Proposal: the Website TF gets to manage all publicly visible websites related to the CG, not just activitypub.rocks. Currently https://www.w3.org/community/socialcg/ has some updates, and activitypub.rocks has different updates, and there are inconsistent calendar links etc, I think we need a single place that owns and resolves this
* Any Other Business (AOB)
    * https://github.com/w3c/activitypub/issues/573
    * https://github.com/w3c/activitystreams/issues/723
    * https://github.com/w3c/activitypub/issues/585

## Attendees _(please sign in!)_

* Dmitri Zagidulin (I.E., [Interop Alliance](https://interopalliance.org))
* Johannes Ernst (https://j12t.org)
* Ryan Barrett snarfed.org
* Evan Prodromou <acct:evanprodromou@socialwebfoundation.org> 
* [Ted Thibodeau Jr](https://www.linkedin.com/in/macted/) (he/him) (OpenLinkSw.com) // GitHub:[@TallTed](https://github.com/TallTed) // Mastodon:[@TallTed](https://mastodon.social/@TallTed)
* Philippe Le Hegaret
* [Michal](https://id.mrkvon.org)
* a <trwnh.com>

## Regrets

- Darius Kazemi

## Meeting Notes

- Darius had an emergency today, sends his regrets.
- Looking at non-controversion automatic transcription for these meetings like the DID working group, no decisions yet
- Dmitri has a new affiliation: small consulting group (credentials, wallets, DID, etc)

## TF Updates

* Evan: Discovery: relationship between AP objects related to an HTML page and vice versa. Closing in on a first draft version. Some issues:
  * How do we refer to various types of ActivityPub objects?
  * How do use embedded JSON-LD? (common on schema.org, search uses it). Can we do the same thing for AP objects?
  * Most recent draft: https://swicg.github.io/activitypub-html-discovery/
* Evan: AP API. Current work:
  * We don't have an easy way to do a membership query on collections (faster than linear scan)
  * Enhancement for auto-complete search
  * Spent much time on OAuth scopes in the past. Were moved into a next phase.
    * Scope: enables a client application to say what it wants, and the end user can approve/deny.
    * One idea: based on the types of activities that the user could work on
    * Different idea: objects of the activities: e.g. followers collection, replies collection to a particular post
    * Decided to "go up" to a more user-visible structure: scope about "liking" vs "posting images" etc

* Plh: various working groups interested in "identity on the web". Are you interested in a breakout session on this? https://github.com/w3c/tpac2026-meetings/issues/62#issuecomment-4723363296
  * Dmitri: from the CG perspective, very interested. Lots of related activities.

* Chris: Will we meet at TPAC?
* Plh: We said we would meet. Will put info into chat once I find it.
* Found: https://www.w3.org/events/meetings/76e40fa6-2003-4ee2-b985-f6f1c87e9baa/

* Johannes: Website TF clarification.

### Main Agenda

* Dmitri: WG-specific meetings are every other week with lots of work on the specs.

* Dmitri: start discussion on "ActivityPub Stack 2.0". CG stages are exactly meant to address this. Show up on Github issues, use Github label.

#### ActivityPub Stack 2.0 discussion

* Johannes: What are we trying to do with an Activity Stack 2.0? We need to figure out why and what we agree on. Now is a good time to try and figure out an approach that does not lead to major internal controversies. Just how 

* Evan: Must avoid breaking changes, do not risk a network split. Can be done in various way, e.g. HTTP 100 for protocol version update. Needs to be managed very carefully, no big change over

* Dmitri: I heard several questions / concerns:
  * What goes where
  * Hope not to get mired in too contentious fights
  * It took a long time to hammer out the charter for the group, for this exact question: current charter constrains us.
  * Breaking changes require incubation 

* Chris: is there a specific proposal to make breaking changes?

* Johannes: no. Only trying to figure out whether people are happy with the current state for the foreseeable future, or does anybody feel like we have to go beyond what is possible with the current process.

* a: Compatibility raises the question, compatibility with what? What is our compatibility target? Are we aiming for spec-compatible, impl-compatible, bug-compatible? This matters a lot for when a "bug fix" also "breaks compatibility" with people depending on the buggy behavior.
  * example issues:
    * `"Public"` vs `"as:Public"` vs `"https://www.w3.org/ns/activitystreams#Public"` addressing https://github.com/w3c/activitypub/issues/404
    * Update activity "partial update" can't remove properties https://github.com/w3c/activitypub/issues/477
    * Collection types have ambiguous addressing https://github.com/w3c/activitypub/issues/486
    * interop between actors and CIDs (verification methods and so on) https://github.com/w3c/activitypub/issues/574

* Ryan: we all know all the problems of how to evolve and not evolve systems. Suggest we just move forward and when we hit a difficitul problem, we figure out how to address it.

* Chris: Existence of the community is very important and we can do lots without breaking even if not elegant.

* Dmitri: is the WG going to work on a 2.0 right now? Absolutely not. Community group: yes, that's what we are here for. So who is "we"? CG is the place for new.

* Plh: has to go to the CG first.

* Chris: (inserts non-documented joke here)
 
* Plh: Need a proposal before any action can be taken.
    
#### Website TF scope

* Proposal by Johannes: "PROPOSAL: Extend Website TF mandate to cover not just activitypub.rocks but all public facing websites of the CG."
  * 8 in favor, none against

* a: would support a motion to have a public communications task force, not merely a website task force
    
#### Issues

Issue https://github.com/w3c/activitypub/issues/573

* Evan: For actors, we use https-based identifiers. Has lots of advantages. Two main issues:
  1. "unbearable lightness of HTTP server", ie.g. identifiers are somewhat ephemeral as servers go off-line
  2. efficiency: if a number of remote servers are trying to deref the same object at once, get a "thundering herd" load on server
* Evan: there have been various proposals, including DIDs. Christine uses bittorrent magnet URIs which are content-based, not address based.
* How could we explore this topic?

* Dmitri: super-interesting big topic. Need to time box. Start discussion here continue in issues.
* Three distinct asks:
  * cross-domain portable identifiers
  * content-addressed identifiers
  * lightening the load / CDNs etc to lighten the load

* a: brought up the topic before, ran out of time.
* Dmitri: should do a special call

* Plh: what about using the same identifiers as ATProto is using? We are working towards interop!
* Evan: makes sense!
* Dmitri: it's basically DIDs
* Dmitri: add to Github

* Ted: URIs can be used for identification and access. Do we need to replicate the entire news feed like NNTP did? Awareness that there is prior work we can learn from
* Chris: is the question: should we explore content addressable AP messages?
* Dmitri: yes
* Evan: would be nice to have a framework for experimentation in that area in the 1.1. spec. E.g. pick terminology in 1.1 that permits that (e.g. SHOULD, allow alsoKnownAs etc). WOuld not lead to interop, but would allow experimentation.

* Dmitri: remaining time: intro other issues, or resolve this now.
* Chris: do you have recommendation?
* Evan: maintain recommendations. Don't pick a particular DID for now.

* Proposal by Evan: ""1. Maintain the SHOULD https recommendation in the spec. 2. Document use of alsoKnownAs" "
  * 6.5 in favor, None against. a: "+0.5 because "alsoKnownAs" overlaps with "url" here". Ted: "also overlaps with owl:sameAs"

RESOLVED: "1. Maintain the SHOULD https recommendation in the spec. 2. Document use of alsoKnownAs" 

* Chris: anybody working on this?
* Dmitri: yes, have FEP (Actor-relative URLs https://codeberg.org/fediverse/fep/src/branch/main/fep/e3e9/fep-e3e9.md)~~, and silverpill's "Federation-friendly addressing and deduplication use cases" https://codeberg.org/fediverse/fep/src/branch/main/fep/cd47/fep-cd47.md) and server implementationo~~ (Correction after the meeting based on feedback from @bumblefudge)

Addition after the meeting based on feedback from @bumblefudge:
* and @bumblefudge 's ["Federation-friendly addressing and deduplication use cases"]( https://codeberg.org/fediverse/fep/src/branch/main/fep/cd47/fep-cd47.md), 
* and `silverpill`'s ["Portable Objects" FEP](https://codeberg.org/fediverse/fep/src/branch/main/fep/ef61/fep-ef61.md) 
* and server implementations



