# 2026-09-24 WG AP Suite Series B

Meeting to be held 19:00 Eastern Daylight Time (23:00 UTC)

## Attendance
 - Dmitri Zagidulin (acting Chair in absence of Darius Kazemi)
 - Ryan Barrett snarfed.org
 - Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
 - a <trwnh.com>
 - Liam Roche
 - Chris Harrelson

## Agenda

* Administrivia
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
     * Sign in under Attendance please

## Topics

Liam's PR on AP: https://github.com/w3c/activitypub/pull/621/changes
on issue 620

EP: concern about naive implementations delivering to as:Public? otherwise let's merge it?

Ryan: CFC period?

a: https://github.com/w3c/activitypub/issues/399 raises concern about "public" vs "publicized"; servers MAY do what they want with your data but it could be a violation of expectations

EP: do we formalize the to:Public vs cc:Public distinction that some implementations use?

EP: let's issue a CFC for the PR and see what the feedback is.

Ryan: https://github.com/w3c/activitypub/pull/626 could be CFC'd at the same time?

### 5.1 Outbox

a: should -> SHOULD?

### 5.2 Inbox

EP: define inbox before talking about how to discover it

EP: we describe POST but not GET

Ryan: "non-federated" appears only twice in the spec?

a: re deduplication, maybe it makes more sense to deduplicate at delivery instead of at time of serving a representation?

### 5.3 Followers

Ryan: "notifications" -> "activities"?

EP: we should describe the directed social graph earlier in the document?

### 5.4 Following

Ryan: "everybody" vs "all the actors"

### 5.5 Liked

### 5.6 Public

a: "shall"? https://github.com/w3c/activitypub/issues/412

a: "might result" actually always results in as:Public. https://github.com/w3c/activitypub/issues/404

EP: why is this here? it seems to be in the middle of the flow

EP: ref to activitystreams-core "collections and objects" should maybe be replaced with AP actors or collections instead?

Ryan: example should show an activity addressed to as:Public instead of just showing a stub collection

Liam: Does authenticated fetch violate the spec wrt "shall be accessible to all users"?

Chris: maybe we should say "with or without authentication" or "regardless of authentication"?

a: if we make this "no authentication" a requirement for as:Public, people are going to ignore it anyway and willfully violate that requirement. maybe with https://github.com/w3c/activitypub/issues/339 publishers can at least not lie about it

EP: lack of clarity here, we need to discuss in an issue

### 5.7 Likes

[discussion of how likes and liked are one letter off]

Ryan: we don't make this clarification about followers vs following...

### 5.8 Shares

Dmitri: "as appropriate" means what?

EP: parallel to likes

### 6 Client to Server

a: Activities ... are the core mechanism for ... we don't say "interacting". should we?

a: "from their profile"? -> "from their actor object"?

a: "MUST make a request" vs MUST use the Content-Type?

EP: split discussion of side effects? parenthetical "these" refers to what?

Ryan: "credentials of the user" should be of the actor?

EP: users vs actors distinction, we might just say "actor" here

Ryan: id generation https://github.com/w3c/activitypub/issues/438 -- why not return an error instead of silently discarding the id? 400 Bad Request?

EP: caching is a bit weird for a POST request to the outbox because POST is not cacheable

a: "there is no guarantee that time the Activity" -> "at that time that the Activity"

EP: maybe we should use example domains instead of real domains?

### 6.1 Client Addressing

EP: requirements to use object and target properties aren't part of client addressing. should we move these to a more general client requirements section?

Ryan: Should Move activities be included here?

Chris: Why is there a list at all? Does it omit any types?

EP: does it make sense to discuss addressing in 3 Objects instead of 6.1 Client addressing?

Ryan: Reconcile client addressing with AS2 audience targeting?

Ryan: "server will only forward" -> "server will only deliver"
