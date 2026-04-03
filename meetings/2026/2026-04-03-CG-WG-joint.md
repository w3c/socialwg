# Social Web WG-CG Joint Call 2026-04-03

Call held 10:00 Eastern Daylight Time (14:00 UTC)

WG Chair: Darius Kazemi
CG Chairs: Dmitri Zagidulin, Johannes Ernst

WG Charter: https://www.w3.org/2026/01/social-web-wg-charter.html
CG Charter: https://swicg.github.io/charters/SocialWebCG-Charter-2025-02.html

## Attendees

* Darius Kazemi
* Dmitri Zagidulin
* Johannes Ernst
* Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
* Ryan Barrett snarfed.org
* @mayel@bonfire.cafe
* bumblefudge.com
* Christiano Longo
* Steve Blackmon
* Andy Piper
* Philippe Le Hegaret
* Emelia Smith
* Michal

## Agenda

* Administrivia
  * Scribe volunteer(s)? Johannes :heart: 
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/) and [Community Group Membership](https://www.w3.org/groups/cg/socialcg/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
* Welcome, and some words on joint WG/CG (Darius & Dmitri)
  - A/B series reminder, new meeting cadence
  - welcome Johannes as CG co-chair
* Brief introductions as necessary
* Task force updates (Dmitri)
    * API (EP)
    * E2EE (EP)
    * Discovery (EP)
    * Groups (EP)
    * Trust & Safety (ES)
* WebSub (plh)
* WG updates (Darius)
  * Adopting the SocialCG drafts: ActivityPub, ActivityStreams core, and Activity Vocabulary as WG editors' drafts. ([Stage 2](https://github.com/swicg/potential-charters/blob/main/stage-process.md#stage-2-formalization-community-group) of incubation process)
  - Proposal for moving forward on incremental document improvements (Evan) 
* Any Other Business (AOB)
    * Miscellany context (Evan)
    * Security context (Evan)
    
## Minutes

* Administrivia
  * Scribe volunteer(s)? Johannes
  * Reminders: 
     * [Working Group Membership](https://www.w3.org/groups/wg/social/) and [Community Group Membership](https://www.w3.org/groups/cg/socialcg/)
     * [CG/WG incubation process](https://github.com/swicg/potential-charters/blob/main/stage-process.md)
     * [W3C Code of Conduct](https://www.w3.org/policies/code-of-conduct/)
* Welcome, and some words on joint WG/CG (Darius & Dmitri)
  - A/B series reminder, new meeting cadence
    * joint meetings are to work together well
    * meetings at different time zones. A-series at 10am eastern, C-series later in the day, to enable broad participation
    * Evan: are we doing any outreach to communities in those time zones (e.g. east asia) to let them know they can more easily participate
  - welcome Johannes as CG co-chair
    * last month were CG elections, Dmitri was only candidate
    * Johannes offered to co-chair after the election was over. Dmitri, as CG chair, can appoint co-chairs, and he appointed Johannes as co-chair.
* Brief introductions as necessary
* Task force updates (Dmitri)
    * API (EP)
      * Evan: had meeting last month, meeting note in repo: https://github.com/swicg/meetings/tree/main/2026-03-19-activitypub-api
      * Auto-complete API endpoint
      * Endpoint for seeking an item in a collection 
    * E2EE (EP)
      * Meeting minutes: https://github.com/swicg/meetings/tree/main/2026-03-31-e2ee 
      * Evan: two great implementations in the works
      * Interop testing next month
    * Discovery (EP)
      * Evan: draft document open for over a year, wants to get it closed. Meeting scheduled for later in April. 
    * Groups (EP) 
      * Evan: also meeting scheduled for later in April
      * Mayel: we really care about implementing groups, closed groups, moderation, there are lots of issues in the repo, please participate
          * https://github.com/swicg/groups
    * Trust & Safety (ES)
      * NLNet grant to support PRs closing open issues, filed in Nov: through first round
      * open call for participation from platform/instance mods and codebase governers 
    * Website (JE)
      * activitypub.rocks needs a blog post announcing the Working Group, Darius will write something
* WebSub (plh)
  * discussed off-record 
* FedCM (Emelia)
  * Emelia is working on a project that requires her to collaborate with everybody related to social software who is interested in FedCM, open to running calls
* WG updates (Darius) 
  * Adopting the SocialCG drafts: ActivityPub, ActivityStreams core, and Activity Vocabulary as WG editors' drafts. ([Stage 2](https://github.com/swicg/potential-charters/blob/main/stage-process.md#stage-2-formalization-community-group) of incubation process)
  * Considering formal hand-off from CG to WG so the documents can become formal documents
  - Proposal for moving forward on incremental document improvements (Evan)
  - Evan: some history:
    - After AP and AS were adopted, responsibility for maintenance went to the CG. Main item: maintaining errata.
    - Have fielded issues from community and developers, either routing them to errata, or towards future enhancements
    - Have errata docs for AS and for AP:
      - AS: https://github.com/w3c/activitystreams/blob/main/ERRATA.md
      - AP: https://www.w3.org/wiki/ActivityPub_errata
          - AP diff: https://services.w3.org/htmldiff?doc1=https%3A%2F%2Fwww.w3.org%2FTR%2Factivitypub%2F&doc2=https%3A%2F%2Fwww.w3.org%2Fpublications%2Fspec-generator%2F%3Ftype%3Drespec%26output%3Dhtml%26die-on%3Dnothing%26md-date%3D%26url%3Dhttps%253A%252F%252Fw3c.github.io%252Factivitypub%252F%26file%3D
      - Vocabulary diff https://services.w3.org/htmldiff?doc1=https%3A%2F%2Fwww.w3.org%2FTR%2Factivitystreams-vocabulary%2F&doc2=https%3A%2F%2Fwww.w3.org%2Fpublications%2Fspec-generator%2F%3Ftype%3Drespec%26output%3Dhtml%26die-on%3Dnothing%26md-date%3D%26url%3Dhttps%253A%252F%252Fraw.githubusercontent.com%252Fw3c%252Factivitystreams%252Frefs%252Fheads%252Fmain%252Fvocabulary%252Findex.html%26file%3D
    - Usually adopted by consensus, typically by e-mail
    - Approx 20 for each document
    - Also maintaining living versions of the spec that applied the errata to the baseline: in git. Conservative number of changes, good candidate for publishing by WG, appears best way to get started
  - Emelia: could do pull request and then review the changes one by one, in order to do an additional pass on all changes
  - Evan: have already been merged
  - Emelia: while the CG has approved the changes, does the WG need to approve them explicitly?
  - Dmitri: Github code-level diffs this large can be hard to read, we should also use HTML tool diffs (like the Vocabulary diff above)
  - Darius: I want to clarify difference between adoption and approval. This is just a proposal for adoption as input documents, approval will be separate
  - Johannes: is this complication really required?
  - Darius: there is value in looking at the diffs
  - Emelia: the main goal of PR is to be able to inline comments and open to-do issues on it
  - Darius: WG needs to take a good look at the changes
  - bumblefudge: all changes since 2019 were "off the website" and not official. Use different versions for the sake of clarity? Make a change log. Would be good to make a 2.0.1
  - Evan: we are at crucial moment in the WG, most helpful would be to read through the whole document: is it communicating what it is needed, so reviewing diff's is great, but reading through the whole document as a whole is also very important
  - Philippe: posted diff in chat, there are not too many changes
  - Darius: Wants to work with Evan to figure out the most legible version of changes. There is both a need for holistic document review, and to flag specific changes if needed
  - Darius: What are the W3C practices for version numbers?
  - Philippe: two philosophies, need to look at it from the perspective of the spec user, not spec developer:
    - Spec is going to be referenced in regulation: clear version number with clear date
    - Version numbers are nightmare, state of the spec changes all the time eg in response to security issues. Example: HTML spec has no version number.
    - The closer you are to the core spec, the less likely you have version numbers. The closer to the regulator, the more likely you will. 
  - Evan: is it correct that a candidate recommendation does not have a different version number?
  - Philippe: how do we want the work to see ActivityPub? Something that is continually evolving, or something that has versions
  - Darius: need to do marketing of the spec. Hoping to market it to social media implementors.
  - Dmitri: currently we are only talking about 1.1 (errata only), strikes the right balance of "still compatible, but update"
  - Evan: Q3 release should be .1. It says "it's an improvement but they are incremental". There's a big difference between a handful of HTML implementations but over a 100 AP implementations. Need to avoid network split.
  - Evan: a September release should go beyond errata. Issues have been grouped into milestones.
  - Darius: reminder there are class 1-5 change types in W3C. So far, we've only been discussing changes in classes 1-3. There may be others in 4 and 5. Let's move errata first, and then approve more substantive changes after that.
  - Emelia: Not sure what class this is: need to discuss approaches to development of safe and private social software. Need to publish a document as so far it is not covered.
  - Darius: let's make this an item in a future meeting
  - Dmitri: sounds like there is no major disagreement to adopt the CG reports. We'll use the HTML diffs to give people another chance to review, and proceed with the process.
  - bumblefudge: e-mail out plh's diff
  - bumblefudge: we've never documented profiles or sub-communities. 
* Any Other Business (AOB)
    * Miscellany context (Evan)
    * Security context (Evan)
