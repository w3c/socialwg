# 2026-08-27 WG AP Suite Series B

Meeting held 19:00 Eastern Daylight Time (23:00 UTC)

## Attendance
 - Darius Kazemi, WG Chair
 - Ryan Barrett snarfed.org
 - Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
 - a <trwnh.com>

## Agenda

* Administrivia
  * Scribe volunteer(s)? (Ryan)
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
     * Sign in under Attendance please
* Welcome
* Brief introductions as necessary
* Fostering East Asian community  
* Continue AP suite group read through
* Any Other Business (AOB)

## Minutes

### Fostering East Asian participation

 - Ongoing effort here and broadly in W3C. More friendly times, etc.
 - Not comfortable with realtime interactive discussions due to language
 - Could we do more async instead? GitHub, mailing list, forums
 - We should look at how W3C more broadly has done this
 - Zoom realtime translation/captioning. Tools can provoke opinions but improving accessibility is valuable
- Hong Minhee (Fedify), Misskey (Japan), etc
  less significant fediverse/AP penetration in China (yet!)
  
### Spec read-through

Last was AP 3.1: Object identifiers

#### AP 3.2: Retrieving objects

Any value in consolidating the two different Content-Types?
- JSON-LD WG is working on related ideas, they have more complexity, partial refinement of types, etc
- Are they both in use? Yes!
- JSON-LD representation is more involved, has more req'ts
- ... *but* AS2 says they should be treated as the same profile and equivalent
  > Because Activity Streams 2.0 can be considered a restricted profile of JSON-LD, Implementations SHOULD consider the `application/ld+json; profile="
https://www.w3.org/ns/activitystreams
"` media type as being equivalent to `application/activity+json`" 
- maybe say so explicitly! (some consensus on this)
- https://github.com/w3c/activitypub/issues/571
- some difference is the expectation of *processing*, ie do you process the data as LD (eg with @context) or not. that's a req't of processing, not the data itself, but still
- important section because it describes one (the "pull") method of distributing data!
- it matters mostly for profiles (the profile= parameter) -- profiles of activity+json do not require additional @context but profiles of ld+json do 
- Should we say objects should/must have any properties here? eg id? Does that overlap with similar language in 3.1?
- Also note that this is the first mention of authn/authz
- ...and HTTP response status codes. Could consider JSON problem reports, newly standardized since AP 1.0
- Is paragraph two necessary? Seems redundant? It's more descriptive/explanatory than normative.
  - a: merge it with 1st paragraph, or i.e. put the paragraph break after the first sentence? p1 = use HTTP GET, p2 = conneg may be used but you must return for the as2 media types 
- Possibilities for wordsmithing, pgs 1 and 2
  - pg 1: We should define ActivityPub objects as AS2 content available over HTTPS.
    - a: im thinking of AS2 documents that have an id that matches the network location via HTTPS but doesn't fulfill any other requirements (like it's missing a type or something if we end up saying type is required)
- If 3.2 is so important (and it is) the spec should be clear about that
- This (and 3.1) are also where we'd look at expanding to non-HTTP transports, eg content-addressed either explicitly or implicitly

#### 3.3 The source property

- Common for microsyntax, eg markdown
- Consider shortening the NOTE?
- Also, should we address how AP objects are edited?
- Is section 3 the right place to call out that we all support GET but few support PUT, PATCH, DELETE, POST to create?
- Should we talk about `source` in C2S instead? move to be 6.2.2 instead of 3.3?
- On the other hand, there's a data model vs behavior distinction. Another option is to mention this in 6.2.2 and cross-link

#### 4 Actors

- Name normalization list item two is confusing
- JSON-LD doesn't have "dereferencing" ids in the same way
- Should we just drop the name normalization? Strong ish consensus on this
- If anything, Webfinger would go here
- Maybe *define* an AP actor?
- The distinction btw AP actor and AS actor here is a bit confusing. Bigger issue to tackle

#### 4.1 Actor objects

- This is the actor definition!
- OrderedCollection vs Collection instances, or Links, are interesting
- compacted URIs vs embedded objects are sources of trouble here in the wild
- streams could be useful but isn't actually used, it's maybe not well defined. same with others maybe too. nothing about domains, ranges, etc. should they go into AS? here? pros and cons
- there's a `liked` collection but no `shared` collection
- "json object which maps" - JSON should be capitalized?
- Missing period after "see 5.4 Following Collection"
- Overall structure: why are there two separate MAY sections? just the example?
  - MUST, SHOULD, MAY - then an example - then another MAY
- ...vs https://www.w3.org/TR/activitystreams-vocabulary/#actor-types
- other AP-specific properties too, eg miscellany, and others, via extension process. OK to have many of those, some widely used, and some eventually "graduate" into the standards, but not all (or any)
- what other terms should we include here? maybe any that are involved with behavior, eg inbox delivery, vs just data
- Dmitri advocates for merging AS and AP (!)
- endpoints are widely used in the wild for all sorts of ad hoc endpoints!
- proxyUrl: needs more space to breathe!
- OAuth server metadata docs probably subsume many or all of the OAuth endpoints here, eg:
  - provideClientKey: define or deprecate
  - signClientKey: define or deprecate
- extension endpoints?
  - would they need a registry?
  - example: for Groups, am I a member of this group?
  - endpoints and streams were both somewhat attempts to support extensions. endpoints succeeded somewhat, streams didn't
- one editorial note, we talk about "foreign server" here, it's the only use of it in the doc, IIRC we have other language to refer to the same thing elsewhere but I'm forgetting exactly what. "remote" and "receiving" are also in there
- sharedInbox is very important in the wild! helps scalability. also surprisingly controversial here
- references to AS name and summary in notes could be improved -- they are applicable to all Objects not just actors
