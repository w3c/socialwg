# Social Web WG-CG Joint Call 2026-10-02

Meeting held 10:00 Eastern Daylight Time (14:00 UTC)

## Agenda

* Administrivia
  * Scribe volunteer(s)?
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/) and [Community Group Membership](https://www.w3.org/groups/cg/socialcg/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
* Welcome
* Brief introductions as necessary
* [PR for non-HTTP ids](https://github.com/w3c/activitypub/pull/637) (Ryan)
* WG updates (Darius)
* [Task force](https://github.com/jernst/meetings/blob/pr-tf-table/DELIVERABLES-TASKFORCES.md) updates (Dmitri/Johannes)
    * Handles task force...?
* Any Other Business (AOB)

## Attendees

* Darius Kazemi
* David Roetzel
* Dmitri Z.
* bumblefudge
* Ryan Barrett
* Liam Roche
* Jeremiah Lee
* plh
* Evan P.
* Matthias Pfefferle

## Minutes

### [PR for non-HTTP ids](https://github.com/w3c/activitypub/pull/637) (Ryan)

 - Ryan: We've had conversations about usage of non-http IDs in ActivityPub so I took a try at changing some of the language in the spec. I was hoping for some response from people.
 - Evan: I was leaning more towards "use `id` with https and use alsoKnownAs for additional identifiers" for the next spec, but this seems to be jumping ahead of that in a big way
 - Ryan: I understood MUST as mandatory, and SHOULD as a "may not"
 - Evan: A SHOULD means you should do it, and a MAY means you may do it. This means an implicit "you may use whatever id" is in there, but you're saying that receiving servers SHOULD process something even if they don't know how to process it. If I get something that says "Ryan said this" and you can't verify it if you can't fetch the original etc etc then you shouldn't publish it. Our verification depends often on dereferencing
 - Ryan: In our spec it says dereferencing is the main verification technique, but in practice it's HTTP Sigs, and people are also moving toward embedded proofs/object sigs (eg VC). In this PR I mention that if you can't verify you don't need to process it. Sounds like the bigger question is whether we want to lean into non-http `id` vs leaning in to non-http `alsoKnownAs` or `url`.
 - bumblefudge: I'm sympathetic to both sides but I also think that v2 spec I'd like `id` to be globally unique but not necessarily dereferenceable the way in Ryan's proposal. But I also see the massive deprecation headache of people using non-http `id` as a transitional stage. I wanted to ask, in the original version the `id` must be publically dereferenceable -- but what does that mean for something that isn't public?
- David: want to second everything Evan said. Don't want to encourage non-HTTP ids since they wouldn't work well with the current fediverse
- Ryan: sure! I could try the url/alsoKnownAs half, which isn't in this PR, first instead
- Evan: more open to this if the receiver processing unsupported id schemes is MAY instead of SHOULD
- plh: could add url/alsoKnownAs for 1.1, url changes in 2.0. Add a note to the 1.1 spec telling/warning people there may be non-http stuff coming
- bumblefudge: language in here is great. if 1.1 shouldn't do this, add generic guidance on non-HTTP ids instead? and, can you treat id/alsoKnownAs as interchangeable, etc?
- Evan: could come up with generic id req'ts constraints, for any scheme. can I dereference, etc? What if we had a registry with suggested flows for processing different formats?
- Ryan: I appreciate this. I think I needed some guidance on what the spec is currently allowing. `id` SHOULD be http, is that best practice or a soft-to-medium requirement? I see a few paths forward. Maybe I remove all the SHOULD, MAY, etc from this PR, or just turn SHOULD process into MAY process. Another is to postpone this and approach the `url` stuff first.
- Evan: You're pointing out correctly that SHOULD is should, it's not MUST, and the current spec doesn't say what to do when you get an `id` you don't know what to do with. That's reasonable for us to say it's up to you what you do with it.
- plh: At the minimum we should remove the constraint that all identifiers MUST be dereferenceable. It doesn't necessarily apply to all identifiers and not even all HTTP identifiers.

### WG updates

- AP review ("book club") series of WG meetings is making good progress! Thanks to everyone who's joined
- Evan: there's also this PR/discussion that came from a previous meeting that we put up for CFC: https://github.com/w3c/activitypub/pull/621
- maybe try to publish a draft by TPAC in 3w?

### Task Force updates

- HTML Discovery: no mtg
- E2EE: met this week, heading toward CG draft. Come look at the repo, esp the issues marked blockers!
    - Currently working on threat modeling, based on W3C's guide
- Groups: met last Thurs
    - New version of Bonfire using public group interface, FEP-1b12
    - Using GoToSocial's interaction policies
- Remix: nothing
- HTTP Sigs: nothing
- T&S: Emelia is talking with new people about taking over as lead(s)
    - They haven't spent much time w/the CG before though. Let's support them!
    - bumblefudge: met w/Victor! agreed, let's support
    - David: other person is Eco (sp?), familiar w/CG
- Web site: migrating to GH pages. considering design, hero banner/call to action, etc. Please comment on this issue! https://github.com/swicg/activitypub.rocks/issues/97
- Geosocial: considering existing explainer draft, whether it should be more prescriptive as a report

- Data Portability:
    - Evan: good time to start meeting again?
    - bumblefudge: draft is ready to finalize. not meeting right now since implementers aren't implementing

- Handles:
    - Evan: Johannes says Anuj won't lead after all
    - Could let this TF hibernate until it has a lead again
    - For i18n webfinger specifically, Jim DeLaHunt is an advocate, wants a tracker for i18n-enabled WF services
    - bumblefudge: Jim could lead!
    - Darius: agreed! may reach out, w/Johannes

### Other

- Dmitri: want to look for second CG co-chair to support Johannes. (I'm stepping down, probably within a month)
- Evan: TPAC planning! will propose breakouts etc
    - plh/bumblefudge: SoLiD is interested. still time to meet w/their CG
