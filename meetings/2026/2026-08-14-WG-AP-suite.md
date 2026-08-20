# Social WG AP Suite Call 2026-08-14

## Attendees
 - Darius Kazemi
 - a <trwnh.com>
 - Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
 - bumblefudge
 - David Roetzel

## Agenda

1. Introductions, Code of Conduct
1. Do we pull existing miscellany terms into WG 1.1 drafts? (https://github.com/w3c/activitypub/issues/591)
1. Continue AP suite group read through

## Minutes

### Miscellany terms

Following up discussion of [activitypub/591](https://github.com/w3c/activitypub/issues/591) in [last week's joint CG-WG call](https://github.com/w3c/socialwg/blob/main/meetings/2026/2026-08-07-CG-WG-joint.md#misc-apas2-terms), which is basically if we should pull in the content of [this Miscellany document](https://swicg.github.io/miscellany/). The Miscellany doc is is a CG Draft but not a CG Final Report. It exists because there wasn't a WG for a long time and so we were trying to get these terms in as extensions while AP was under CG purview, but in the intervening time the WG appeared so now there's a process hiccup.

After some discussion the group agreed that as a one time thing we get the CG to vote to approve the Miscellany doc as a Final Report and then the WG can pull it in. We all agree we need a different process for the future since there is a WG now.

Darius suggests W3C registries: https://www.w3.org/policies/process/#registries

evan suggests making the activitystreams context a living document

darius: I think we can make the context document itself essentially a machine-readable version of a registry. so the process would be: the WG votes to add a term to a Registry, and then it's someone's job to update the dereferenceable context document to reflect that.

evan: there are places where we link to a wiki page here: https://www.w3.org/wiki/Activity_Streams_extensions and instead how about we link a Registry?

a: strategically having a "core" as2 context and a "community" socialcg context makes more sense, especially coupled with w3c registry stuff (and the socialcg can govern the socialcg context how it wants) 

a: the context document provided alongside the miscellany draft has different definitions than what is widely used -- we should match the widely used definitions and not change them in incompatible ways

evan: I think there's a difference between telling people there is a calculus notation extension for AP/AS (for example) and so people who need that niche thing can grab it, versus the whole calculus notation getting pulled into a context every time I consume an activitystreams document. There's not a point in consuming a giant document with a lot of niche definitions just to get to basic things like hashtags.

darius: I think that's what A is proposing here. I would say we have one context/registry maintained by the WG that is for the major terms (and what constitutes major is of course up for debate and the point of deliberating as a WG), and then maybe there is a CG maintained informal registry and context (a CG unfortunately can't maintain a formal W3C Registry... so maybe we do have the WG maintain that one as well but we understand the CG does most of the work of nominating extensions for it)

darius: next step here is for me to send a CFC to the CG to turn Miscellany into a Final Report


### Begin ActivityPub group read through / commentary

We are starting at: https://w3c.github.io/activitypub/#conformance

### ActivityPub Section 2.1 - conformance

evan: it says "as you read this we are going to call out when something is c2s or s2s". There is another way to do that by saying "If you are to be a compliant client, you need to support sections 3, 4, 6, and 7" and so on. I think that's easier than mentioning embedded in the document.

evan: when it says sending and receiving servers, we haven't defined that.

darius: thing are very grammatically muddled in 2.1

evan: maybe we should also say something like listing sections that are common to both client and server so people can "diff"

a: there was a checkbox version of AP informally posted years ago: https://socialhub.activitypub.rocks/t/guide-for-new-activitypub-implementers/479/2?u=trwnh

evan: we have very few MUST requirements and a lot of SHOULDs. a pointed out that it's possible to have software that does nothing that is technically conformant with large parts of AP.

### ActivityPub Section 3 - Objects

evan: we conflate AP objects with AS 2.0 Objects here -- for example, AP objects need to be dereferenceable etc. we also jump straight into verification of properties of an Object without clarifying that we are getting into verification. we should break out everything from "servers SHOULD validate" to the end into some verification section.

evan: we are also way overusing the word object in Section 3

darius: when speaking in a meeting maybe we should disambiguate "object" vs "Object"

bumblefudge: what if we say "as:Object" in spoken WG meetings

evan: there's the section where we say "ActivityPub defines some terms in addition to those provided by ActivityStreams. These terms are provided in the ActivityPub JSON-LD context at https://www.w3.org/ns/activitystreams. Implementers SHOULD include the ActivityPub context in their object definitions. Implementers MAY include additional context as appropriate" which is confusing because we define AP context in terms of the AS context

a: we should just say AP uses the AS context and phrase it that way

evan: at one point AP had its own context document and we merged it all and I think this section is leftover. We need to define the relationship more precisely

### ActivityPub Section 3.1 - Object identifiers

evan: "All objects have the following properties" should have a MUST, the portion about C2S should be moved to the C2S section. "publicly facing content" is not defined; authority of a server is not defined.

bumblefudge: "actor's namespace" and "authority of the originating server" is related to HTTPS. we only ever think of authorities as apex domains because we are so used to HTTPS

a: we only recommend HTTPS URIs as a SHOULD, but we talk about how things need authority components and are derefrenceable. In HTTPS that's the TLS cert that tells you you are talking to the server you think you are. In theory another URI scheme that meets those requirements could work.

evan: what do we think about publicly facing?

darius: very confusing. is it "anonymous browser reachable"? as:Public?

evan: maybe we should talk about alsoKnownAs in 3.1. Maybe primary could be HTTPS and then alsoKnownAs could be used to point to other URI formats.

a: we had some discussion here: https://github.com/w3c/socialwg/blob/9bb70c4b5ee4a147facc86ea2e57a69c8322868b/meetings/2026/2026-07-03-CG-WG-joint.md?plain=1#L135-L145

[lots of discussion I couldn't scribe, sorry!]

bumblefudge: based on alsoKnownAs current usage it feels like it would be semantic drift to use it for things that aren't "subjects" in the sense "subject of a DID". alsoKnownAs may not be the perfect solution for alternative URLs.

evan: in general I'd just like to be able to say "here's the HTTPS url, here's an archive.org backup, here's a magnet, etc".

a: how about `{"url": [{"href": "https:..."}, {"href": "magnet:..."}, {"href": "ipfs:..."}]} `

evan: I don't like using `url` since that's for things like location of an image and so on

a: I think `url` should just be "when you resolve this field you get a representation"

darius: historical thread on Mastodon using alsoKnownAs in the as namespace without CG approval and the CG back-approving it https://socialhub.activitypub.rocks/t/defining-alsoknownas/907

bumblefudge: https://socialhub.activitypub.rocks/t/defining-alsoknownas/907/15

bumblefudge: is using `url` only for certain things like media images a mastodon-ism or an AS thing?

evan: in 1.0 it was about HTML pages, in 2.0 it was for references to video, image, and so on

bumblefudge: if there's a lot of history it would be weird to put other protocols there

evan: perhaps `otherIds`

darius: in the scope of our "1.1" remit on the working group, we s

a: this might be `owl:sameAs`, using exisiting is good but if we want to control what the term means we should come up with our own such as `as:otherIds`
