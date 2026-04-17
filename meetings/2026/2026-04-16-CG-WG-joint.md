# Social Web WG-CG Joint Call 2026-04-16

Call held 19:00 Eastern Daylight Time (23:00 UTC)
Scribes: Lisa Dusseault, a

WG Chair: Darius Kazemi
CG Chairs: Dmitri Zagidulin, Johannes Ernst

WG Charter: https://www.w3.org/2026/01/social-web-wg-charter.html
CG Charter: https://swicg.github.io/charters/SocialWebCG-Charter-2025-02.html

## Attendees

* Darius Kazemi
* Dmitri Zagidulin
* Johannes Ernst
* Chris Harrelson & twin Evan Prodromou
* Lisa Dusseault
* Aaron Parecki
* a

## Agenda

* Administrivia
  * Scribe volunteer(s)?
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/) and [Community Group Membership](https://www.w3.org/groups/cg/socialcg/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
* Welcome (Darius)
* Brief introductions as necessary
* Task force updates (Dmitri)
    * API (EP)
    * E2EE (EP)
        * https://hackmd.io/Z1YJoX_eSOSG3wivUkI-fA
        * https://github.com/swicg/activitypub-e2ee/issues/72
    * Discovery (EP)
    * Groups (EP)
    * Trust & Safety (ES)
    * Geosocial (JL)
* WG updates
  * Status of Drafts for ActivityPub, ActivityStreams core, and Activity Vocabulary ([Stage 2](https://github.com/swicg/potential-charters/blob/main/stage-process.md#stage-2-formalization-community-group) of incubation process) (Darius)
* Any Other Business (AOB)
  * Inconsistent typing in AS2-Vocab vs jsonld context [original issue](https://github.com/w3c/activitystreams/issues/595), [recent discussion](https://github.com/w3c/activitystreams/issues/595#issuecomment-3736032233), [open PR](https://github.com/w3c/ns/pull/11) (plh)
  * Live meeting translation and platform

## Minutes

### Administrative/welcome/Introductions

 * Note the offset meet times to allow different timezone folks to participant; we'll note actual attendance and then things may shift. 
 * Anyone can join the CG linked above; invited experts can join the WG linked above. 
 * note the W3C code of conduct.
 * Johannes Ernst is the new CG co-chair.
 * Chris Harrelson introduced himself. 
 * New WG invited expert 'a' said hello.

### Task Forces

Evan:

- Geosocial TF: representing location within the text of ActivityPub objects.
- E2EE TF: Proposal for being able to rapidly seek an item within a Collection forthcoming.  

Johannes: Mastodon has gotten funding from the Sovereign Tech Fund, among others for E2E implementation - are they involved in the E2E work, how are they going to spend the money?  2 more backend devs...? 

Evan: Claire from Mastodon has been in the meetings participating in the standardization process, but one of the questions that came up in their funding was making sure E2EE did not interfere with user safety on the Fediverse. E2EE should not be used to harass people on fedi or do it secretly in a way that mods can't see it. Want to provide trust and safety features like being able to report E2EE messages, non-repudiable; techniques for doing this with e2ee like message franking but need to consider this more holistically.

Darius: Some concerns possibly?

Evan: Yes we need to balance the expectations between privacy of e2ee vs safety of being able to report abuse.

Evan: Will add links into minutes.

Darius: Thanks Evan. Any other questions? Will note we could probably do better job as WG/CG of advertising some of these open questions and issues in TFs out to the mailing list and other venues so people can read them and follow up if interested. Will think about this later because interesting problems come up and we should market these issues and protocol developments.

### WG updates

Darius: We had resolved some things by last meeting that we should have ready by next meeting. Last meeting WG resolved to adopt editor's drafts from CG to be the new working drafts of the WG. Drafts under umbrella of WG would allow us to make progress on editing them, diffs can be quite complex so we will probably go with HTML diffs but can try to come up with alternative views as well to make it easier for people to spot and understand changes.

Evan: Starting with errata. I should have been producing these diffs, forgot we need to review diffs first. My question: when do we stop maintaining errata for 2017/2018 docs and start saying "it all goes in the next version"? W3C has class system for errata, small typos vs major changes. On review, we are responsible as a WG to maintain errata for the published docs until they are superseded. So I think the CG is still responsible until the WG publishes the 2026 versions. Closer to publishing the next version usually means less emphasis on errata but technically we still maintain it. In our GitHub repo we can probably maintain different branches of the documents. Open to either git or copying the document. Maintain the docs but should also have working drafts for next versions.

Darius: We can do that and open to comments.

Evan: Where to go from here -- we need a critical eye, rigorous read through and try not to miss mistakes from having read the documents so many times. We should open issues before doing PRs so we can discuss the issues and have people on the same page before spending time on PRs. In CG issue triage we have been looking at which issues require which actions, have also been adding issues to milestones recently so we can prioritize issues that can be handled in 2026. Some questions about how to approve PRs but my expectation is that as we get closer to finishing issues for the next milestone, then that's the point we could put out a next working draft. I'm concentrating on text, missing examples, undefined terms, concepts not introduced before they are used, requirements that conflict with each other or with normative requirements, RFC 2119 language missing for implied requirements, clumsy language, repeated reqs, hidden reqs, relationships that are unclear... I think with this version we are not necessarily looking for adding or removing features in 2026 versions, but does not hurt to document them and keep them for later.

Darius: Encompasses any Class 1, 2, 3 changes -- adding a RFC 2119 MUST is a Class 3, is a normative fix even if the language before was highlighting the importance. I'd like to work with you out of band and present this over the list to the groups and in particular I'm interested in pointing out where the process is legitimately, by this process, in this location, period of time, etc -- tell us what you think, please review all changes and make it clear to participants in both groups so no changes get snuck in.

Evan: Let's not get too bottlenecked on people, me in particular, adding discussion issues is something we should all do. On topic of PR approval, one thing I've seen is 2 approvals = merge, this could be seen as approaching consensus instead of requiring the chair to review and merge all changes.

Aaron: OAuth WG follows similar process and is pretty chill, we discuss changes since last time and no surprises, it works I think

Lisa (in chat): +1 to Aaron - editors are in charge of the quality of the document, regardless of the editing/PR/merge process, and responsible to the WG for content not PRs. 

Chris: CSS WG has same approach, PRs don't contain type 3 or substantial changes, bring it back to the group as a checkpoint if it does.

Darius: Something to consider, editor approval could be enough, but make it clear to people that there are comment periods so no one gets surprised.

Evan: Might be opening up more complexity, but we have expected date of Q3 2026, aka September 30 for me. No scheduled work for Micropub, WebSub, LDN -- and we also have LOLA which is still open. Do we slot in other recs? Is it time to start bringing LOLA into WG?

Darius: Any thoughts, Lisa?

Lisa: Happy to get back to it with wider review and possible implementations. Bit hard to more or less solo it, judging feedback and incorporating it all is a lot of self management!

Lisa: Looking at auth process, is it consistent with how it's done elsewhere Chris? (with a side mention of Aaron who also works on this)

Chris: I can take a look. Send me sections to review

Lisa (in chat): https://swicg.github.io/activitypub-data-portability/lola.html#authorization

Darius: Any other LOLA or WG comments? When we chartered WG in particular, broader documents under our umbrella, someone needs to be in charge of stewarding these documents. Idea was we needed to hear from the groups that use those documents about need for updating and maintenance work -- editors to step up and do the work, we can't do the work without editors.

Evan: Manton Reece from micro.blog, wonderful guy, did volunteer on public-swicg list about helping to manage Micropub and Webmentions, not sure if participated in standards process before but possibility -- worthwhile to do the outreach?

Aaron: I'd be happy to help him with that, can't take on solo but can help.

Evan: Talk to Manton then?

Darius: Manton should be in the WG, will kick off an email

Evan: That's 6 documents at the same time -- is it realistic to take them on all at the same time?

Aaron: Wary of biting off more than we can chew, but there has been independent evolution that is worth capturing. Lots of work already done. We're not starting from zero. Iteration has already happened in years since.

Darius: Great! Will see if we can get conversation going over email later.

### PLH raised issue

Darius: PLH apologizes, on a flight, couldn't attend meeting but raised a PR that needs discussion

Inconsistent typing in AS2-Vocab vs jsonld context
[original issue](https://github.com/w3c/activitystreams/issues/595),
[recent discussion](https://github.com/w3c/activitystreams/issues/595#issuecomment-3736032233),
[open PR](https://github.com/w3c/ns/pull/11)

Darius: Highly technical changes so maybe not best to discuss this at this meeting right now?

a: Summary of issue in the descriptions -- Link.href is stated to be a Reference `@id` in the context document but the vocab document says it has a range of `xsd:anyURI`. Semantically a Link is a Reference as defined in RFC 5988 / 8288. Also Reference `@id` processing in JSON-LD has practical concerns of expanding relative references. Whereas a Literal is just a string that happens to be datatyped. In JSON they can both look like a string, but it matters whether the string represents an `@id` or a `@value`. Sarven shares this position; Evan had concerns that I would say are more schematic than semantic -- the desire is to have it represented as a JSON string and not embed nested information.

Evan: I don't think we have consensus, we shouldn't make changes if we are not sure about it; don't want to make changes that break things for JSON vs JSON-LD use

a: Changing the JSON-LD context will break old data and embedded JSON objects are possible even with `@value` so it's not like changing the context will fix this. It could even make it worse.

Darius: a, can you bring this to the mailing list to get more eyes on it and we can reach some kind of consensus?

a: I can do that, yeah.

### International participation and tool use

Darius: International participation is something we want to encourage, our series B meeting in this time slot is more friendly to Asia time zones, invited some East Asian devs to this meeting but some language barriers as well, asked PLH how groups can mitigate this, PLH said some groups have a Zoom-based workflow with auto translation. We currently use Jitsi Meet which has better privacy story than Zoom but thinking about the ways this might exclude people from participating.

Evan: In the past we talked about non-OSS tool usage but it has been a big issue for community members as well, people report it is impossible to launch certain proprietary tools at times, we have historically erred on side of FOSS but important to consider multiple needs.

Darius: Could use both? Jitsi for A meetings, Zoom for B meetings?

Dmitri: Automated transcription maybe?

Johannes: How good are the machine translations here? Perhaps would not help with overall comprehension if the transcription is not good and mixes up words in multiple languages, especially technical terms.

Aaron etc: How good are *transcription* services in lieu of translation?  It may be much easier to read English than understand spoken English at speed, and transcription services may be better quality. 

### Time and scope

Evan: our expected completion date is Q3 2026... We could deliver in November instead of August , will that be OK? Are dates gentle suggestions?  When there is pressure between time and scope, we need to limit scope appropriately. We have been sitting on these documents for almost a decade. Maybe the perfect would be enemy of the good in this situation.  When a topic is too tangled, let's work on clearer diagrams and descriptions rather than tough issues? BUt if there are important topics we have to get done before we ship, let's identify those.   But I prefer to 'ship' by end of 2026.   (clarification request)  Public working draft is the definition of 'ship'.

Chris: Have we decided not to make further (substantive?) changes to these specs until that happens?  

Darius: I think the focus until the docs get out the door that depend on each other is to get the docs out the door before whatever "ActivityPub Next" is. 

Darius: We can discuss 2.0 in parallel but we should focus on the minor changes first and keep the discussions for major changes on the side. Our charter expects us to get these new drafts out.

Evan: Example of a "new feature", say there's a marketplace feature that people want. We have an extension mechanism for people to try doing this without officially merging it into the main spec or leaving it as an extension.

Chris (in chat): is there a centralized list of the current set of docs that needs to be republished as FPWD?

Darius (in chat): They are listed in the charter

### Conclusion

Darius: We are 2 minutes over, see you all at the A meeting, probably tomorrow these notes will go up.

## Evan's notes on process

### Process for updating Activity Streams 2.0 Core, Vocabulary, ActivityPub

1. Apply errata.
2. Make a new branch for the next version of the documents (so we can maintain errata for existing docs).
3. Rigorous reading and review. See below.
4. Add an issue for each comment.
5. Let percolate and let discussion happen.
6. Triage (this version? Next version? Errata? Other treatment?)
7. Add to project.
8. Generate PRs.
9. Approval on PRs (2+?)
10. Merge.
11. When all (most? some?) project issues are complete, FPWD?
12. Rinse and repeat.

#### Review topics

- Terms that are used without a formal definition
- Concepts that are not introduced before they are used
- Requirements that conflict within the document
- Requirements that conflict with dependencies
- Requirements that don't use RFC 2119 language
- Clumsy language
- Repeated requirements
- Hidden requirements from JSON-LD or RDF that aren't made explicit
- Hidden assumptions from other documents that aren't made explicit
- Relationships between object types or properties that are unclear

Ideas and comments generated now that aren't appropriate for the .1 version are still useful. Better to generate them now than to self-edit.
