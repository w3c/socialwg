# Social WG AP Suite Call 2026-10-22

## Attendees
 - Darius Kazemi, Chair
 - a <trwnh.com> (they/them) (scribing)
 - Ryan Barrett
 - Chris Harrelson
 - Johannes Ernst https://j12t.org (late)

Regrets, Evan Prodromou

Meeting held 19:00 Eastern Daylight Time

## Agenda

1. Introductions, Code of Conduct, WG Membership
2. Continue AP suite group read through

## Minutes

### ActivityPub spec read-through

#### 6.5 Follow Activity

- Darius: last time Evan pointed out "when and only if" is weird wording, also state issues with where pending follows live. https://w3id.org/fep/4ccd tries to deal with that. Do we need to specify more here?
- Ryan: related question about multiple Follow or multiple Undo. seems fine but...
- Darius: last time comment about behavior of using id vs embedding by shape?
- Ryan: not this section specifically
- Darius: i get why there isn't a collection as it exists right now because that's more "private data" than "social API" and it lives more in implementation land. use case of seeing someone else's collection?
- a: possible collection might not be exposed

##### side effects

- a: side effect is not of the Follow in your outbox, it's actually the side effect of receiving an Accept in your inbox. maybe replace it with a link to 7.6 S2S Accept and 7.7 S2S Reject?
- Ryan: we need to expect state stuff that isn't really specified by the standard and that's ok i guess. it's interop stuff
- Darius: so then what does this mean? do we just have a single sentence and a link or two?
- a: yeah, maybe even make Accept Follow and Reject Follow subsections to make it even clearer? 7.6.1 and 7.7.1

###### reading the inbox C2S

- Chris: How would the client know about the Accept/Reject
- Darius: reading inbox after it's delivered/received.
- a: maybe Section 6 needs to talk about GET inbox?
- Ryan: we talk about the inbox in 5.2 and we talk about fetching in 3.2, at least
- Darius: somewhere we need to clearly describe the relation between clients and the inbox

##### follow state machine

- a: larger point: "Follow state machine" is implicitly defined here and has been broken for a long time. Follow -> Accept is how you mutate that state machine, but there are no consistency guarantees or introspection to get the current state. Desync, state loss, race condition, etc can make it so that you can't follow a specific actor ever again, no reconciliation mechanism.
- Ryan: AP is not a data sync protocol and maybe we should try to address this but it will be a small band-aid at best...
- a: people are using it that way regardless!
- a: Can we maybe have a "subscription model" section that talks about all of this? Instead of leaving it as a loose bundle of side effects split across several sections

###### what to do about this

- Chris: what can we do about this?
- Darius: maybe reach out to implementers? or standardize some kind of error messages? have some way of knowing "something went wrong". For a 1.1 spec idk if this can be fixed. Maybe more work that can be done later.
- Johannes: What do users expect? I expect that my friend sees the same thing I do. Inconsistency means a protocol failure. We need to commit that we want to fix this, maybe out of scope for 1.1 but it should be on a roadmap of some kind, that these are the conditions we want to exist at some point eventually. We can't say "we don't care".
- Chris: In the meantime it seems appropriate to note these scenarios and possible mitigations.
- Ryan: We may not figure out what to even say in a 1.1 about this, need more time to think about it.
- Darius: 2.0 definitely should try to fix and mitigate the issue
- Ryan: desync can also happen with more than just Follow
- Darius: essentially a rapid unfollow-follow cycle can leave the state machine in an unpredictable state
- a: yes, one mitigation is to educate users that they need to wait 1 hour or 12 hours or 24 hours between unfollowing and refollowing. not great... issue is created by processing follow-state-related activities by shape instead of by id (because implementers didn't want to handle cases where more than one Follow exists). retry logic and out-of-order delivery is the other half of the problem -- processing an Undo Follow will destroy the newer Follow
- Ryan: separately we might have shared mutable state
- a: either 1) manage state entirely on the sending side, 2) have some kind of CRDT or whatever to auto-rachet apply monotonically increasing state (as Ryan suggests) to a Relationship

#### 6.6 Add Activity

- Darius: nothing jumps out as particularly wrong
- Ryan: maybe some guidance about what's appropriate to Add to what?
- Darius: so an example?
- Ryan: yeah

##### use cases

- Ryan: how is this used on fedi right now?
- Darius: pinned posts, usually

##### add/remove is very basic and doesn't work well with the middle of an OrderedCollection

- a: sidenote on collection management:
    - https://socialhub.activitypub.rocks/t/stricter-specifications-for-pagination-of-collections-and-orderedcollections/2633
    - https://socialhub.activitypub.rocks/t/pre-fep-evolving-orderedcollection-to-be-more-useful/4608

#### 6.7 Remove Activity

- Darius: seems fine as well

##### AP `target` vs AS2 `origin`

- a: minor point about using `target` instead of `origin` as AS2 specified; we should probably explicitly note that discrepancy at the very least

#### 6.8 Like Activity

##### managing the liked collection

- Ryan: maybe say non-normatively that there could have been Add/Remove to liked collection
- Chris: Undo Like vs Remove from liked?
- Ryan: yeah that's how it ended up
- Darius: you could send an Add activity to the liked collection and that would be compliant
- Darius: kind of smells like a legacy thing
- Darius: why not Add to followers?
- Darius: sort of like syntactic sugar
- a: Honestly I'd rather have the Like activities and not just a bunch of contextless objects (when were they liked?)

##### announce

- Ryan: we are missing the Announce activity
- a: it doesn't have any C2S side effects though... unless we define a `shared` collection or similar as you suggested earlier

#### 6.9 Block Activity

- Darius: Block Activities -> Block activities? (capitalization)

##### federation despite SHOULD NOT

- a: Do we acknowledge that in practice people do actually deliver Block activities?
- Darius: Maybe a sample flow of this to illustrate the potential issues
- Chris: Why do people deliver Block activities anyway?
- a: assuming there is a "server" on the other end and it is operating in good faith, it can hide profiles and posts when it receives a Block activity.
- Ryan: Regrettably we use Block activities in Bridgy Fed to allow users to unfollow without unbridging (?)

##### "interact"

- Johannes: what does "interact" mean here exactly?
- a: maybe something like "any incoming activity gets dropped"
- Darius: it's pretty unclear here, it could mean a lot of things. we should be more precise about it.
- Ryan: also in the case of federating Blocks, we should define if the blocked actor can "see" the objects
- Darius: This makes it more complicated wrt HTTP GET.
- Johannes: suggest we don't use the word "interact"?
- Ryan: non-normative guidance
- Darius: talk about POST and GET, give example.

##### muting

- Chris: Muting is not in the spec, right?
- a: AS2 defines an Ignore activity but AP doesn't define side effects. could have a collection for `ignored` users or have server-side filtering of results via `proxyUrl`

##### misc issues

- Darius: interactions aren't being checked at the origin, say Alice blocks Bob, Bob likes Alice's post, Charlie gets Bob's Like but never checks Alice's object's likes collection, so Charlie thinks Bob liked it and the Block never actually works as far as Charlie is concerned
- Ryan: mentions break when you mention someone who is known to have blocked you, that's not in the spec

##### addressing of Block activities

- a: Trust and Safety issue re: delivering Block activities to a `host` or `moderator` instead of to the directly blocked `object` actor
- Darius: kind of out of scope of AP for now? but could be mentioned in a non-normative note. or a WG Note that we can link to.

##### flagging

- a: Relatedly we don't have a section on Flag activities either

#### 6.10 Undo Activity

- Darius: making a chair call to defer this to next meeting because it's another statefulness nightmare
