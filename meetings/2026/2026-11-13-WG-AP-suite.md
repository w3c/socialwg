# 2026-11-13 WG AP Suite Call Series A

Meeting held 10:00 Eastern Daylight Time (15:00 UTC)

## Attendance

- Darius Kazemi
- a <trwnh.com> (they/them) (scribing)
- Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
- David Roetzel (Mastodon)
- Matthias Pfefferle <acct:pfefferle@notiz.blog>
- Dmitri Zagidulin

## Agenda

1. Introductions, Code of Conduct
2. New schedule
3. Demo of Github bot for managing [publication workflow](https://github.com/w3c/socialwg/blob/main/governance/publication-workflow.md)
4. FPWD to-dos
    1. document Class 1, 2, 3 changes in current Editor's Draft
    2. WG Decision
    3. inform W3C Team of Decision, await approval
5. PRs to review
    1. https://github.com/w3c/activitypub/pull/668
7. Continue AP suite group read through

----

## Minutes

### New schedule

Darius: Talked with Johannes and because the A meetings have higher attendance we are moving to more of those; CG is now once per month because the WG needs more working time

### Publication workflow

Darius: New "governance" folder in socialwg repo records meta-decisions like this.

Darius: GitHub bot can be used more broadly, e.g. on WebMentions. Automation makes some sense but not for all.

Darius: Workflow "pr-lifecycle" triggers every ~5 minutes and runs script pr-lifecycle.js to check all PRs for labels

Darius: New PR comes with templated text containing instructions

Matthias (in chat): Wrapping it in an HTML comment will make it invisible even if someone forgets to erase the templated text

Darius: Could be a good idea but also don't want people typing in the middle of the comment?

Darius: Demo time! New PR submitted, it now has a timer after which it gets "Stale-PR" label. Idea is before WG meetings (or at the start), Darius/we can go through the needs-class label and assigns a class label like "class-2". This triggers a new comment window.

Darius: Labeling with a "class-x" label adds the "comment-open" label. When there is an objection in natural language, an editor/chair manually adds an "objections-open" label. "comment-paused" state pauses for comments. Manually adding "objections-resolved" removes the "comment-paused" and "objections-open" labels. End of timer removes "comment-open" and adds "comment-closed" label.

Evan: Thumbs up! Want to be clear about how "+1" works though -- more metaphorical than literal +1/-1 vote?

Darius: Intent is approval. Not looking for literal word phrase emoji etc -- up to the discretion of the editor to interpret comments and ask for clarification if unclear.

Evan: Does this interact or conflict with native PR workflow "request changes" and other actions?

Darius: It shouldn't be a problem, the bot will process things based on labeling actions.

Evan: I get nervous when PR proposes both a problem and a solution, would prefer issues for discussion. Hard to tease apart problem/solution in PRs. Can we make sure to identify problems in issues first?

Darius: This is separate from the PR process. I suggest amending the PR template to note that issues should be filed where appropriate. We can also say as a group "we're not going to apply class label to this" and advise the person when it needs more discussion.

Evan: More mechanical question: When is this pushed to activitypub repo?

Darius: ASAP today? I noticed as a matter of practicality that the tags could be namespaced because the activitypub repo has a lot of tags, and these tags need to be findable. Maybe something like wd/ for "working draft".

### FPWD todo list

Darius: Evan, do we have any progress on a document for listing Class 3 changes etc and explains them?

Evan: I can get that going before next meeting

Darius: Ideally 1-2 days before so group can review it

Darius: WG decision to move draft to FPWD, would like for this to be next week. Let the mailing list know ahead of time. Reminder to everyone that FPWD is an important milestone but all we are agreeing to is that "this document deserves to enter the REC process". that there's enough there to submit and there isn't anything egregiously wrong with it. then I inform W3C team and they can put us on the REC track and kick off horizontal review. Sarven said he thought there wasn't anything terribly objectionable; hopefully he's right!

### Review existing PRs

Darius: Some PRs came in before Nov 6 decision. PRs post-decision can be handled by the process but let's look at https://github.com/w3c/activitypub/pull/668 for example.

Darius: Fix line breaks in JSON example, so JSON example can be parsed. It's a non-normative change to a non-normative example, so I'd say it's Class 2 and could even be Class 1.

Evan: Class 2? It's not quite a syntax change...? Still would probably vote to apply it although the text could be reworked to be shorter as an alternative solution.

Darius: OK, applying "class-2" label now; this should start a timer.

Evan: Can we go through other PRs right now?

Darius: Any objections? No? OK then.


#### https://github.com/w3c/activitypub/pull/363

Darius: PR #363 from January 2023 proposes removing references to test suite since the test suite is broken. PR targets the README. This brings up a good point -- how to handle PRs that address meta-issues for the Github repo? For now removing "needs class", leaving PR unhandled.

#### https://github.com/w3c/activitypub/pull/458

Darius: PR #458 is a dupe of PR #668. Closing in favor of #668 because that one has a description.

#### https://github.com/w3c/activitypub/pull/637

Darius: PR #637, "should dereference" -> "should dereference or otherwise verify", plus some other conformance changes.

[class 3 or 4; probably 4 since the use of non-HTTPS identifiers could be construed as new functionality; however the counterargument is that we're not changing the SHOULD around using https:, it was never a MUST.]

Dmitri: Oversight that needs to be clarified

Darius: Let's keep in mind we're now discussing the PR rather than simply triaging it.

Matthias: Spec is so vague that we have a hard time getting compatibility. Take care not to allow so many possibilities? Agree there should be other options and open to impls but don't forget to focus on interop.

Evan: If we have doubts about Class 4 then it should be Class 4.

a: These requirements already exist to SHOULD use HTTPS and SHOULD continue processing; nothing really new is being added, just expanding/clarifying.

Darius: We can mark it Class 4 for now and let people object in the comments on the PR.

#### https://github.com/w3c/activitypub/pull/645

Darius: This is marked WIP, so we can skip this for now

Evan: Actually I want to split this into smaller PRs later

#### https://github.com/w3c/activitypub/pull/652

Darius: Remove "AP context" and refer to AS2 context instead

Darius: Looks like it renames "ActivityPub" to "Activity Streams", changes "at" to "identified by"

Darius, Evan (in chat): Class 2

Matthias: Should it be ActivityStreams?

Darius: Actually it's "Activity Streams"!

Darius: Tagging "class-2" and "WD-comments-open"

#### https://github.com/w3c/activitypub/pull/666

Darius: multiple typo fixes where maybe we want to split them. [runs through them quickly]

Evan: We can treat this as one PR for now but I ask that in the future we split PRs like this. As far as I can tell these are all Class 2.

Darius: I agree it's a Class 2 set of changes; it's a code smell thing for future PRs though.

### AP readthrough

#### 6.10 Undo activity

Darius: the link to "Inverse activities and Undo" links to a non-normative section.

Evan: We should make it normative?

Evan: Uses passive voice and doesn't assign responsibility for the undoing. Is it the server? Some other server? Client? etc. -- who is making the changes? "may be used" and "is used -> "the server SHOULD".

Darius: Similar statefulness issues with Undo. How do we keep track of state with Undone activities? a, any comment?

a: there's not really a way to link the Undo activity and then the activity being undone and then in reverse. Activities don't get mutated to say "I was undone by [this activity]". It would be nice to have a backlink.

Evan: That would be awesome, I suggest we add an "undoneBy" property or similar.

Matthias: What about similar way like a signing (?) implementation. What if we had a SHOULD where an API is provided that allows a remote server to inspect the state of an activity.

Evan: MUST be the same actor? seems pretty reasonable but doesn't allow for moderation or "higher privileges" to take action. could the MUST be a SHOULD?

Evan: Undo chaining, Undo an Undo? My suggestion is no. Just issue a new activity.

a: Also it prevents infinite chains of Undo, or multiple Undo of the same activity.

David: last paragraph "should" should be "SHOULD" or even "MUST".

Evan: Race conditions here as well. Maybe more relevant for S2S Undo.

David: I peeked ahead and S2S Undo is very short, just links back to this C2S Undo...

a: Subsections on Undo? Undo Follow, Undo Like, Undo Block as sub-cases with their own side effects

Matthias: I think you MUST use Delete instead of Undo Create.

Evan: This is something that can be really hard because you have to maintain data not in the AP layer. For Follow activities you have to keep track of the Follow.id potentially losing track of it. "Shape based Undo" gets used a lot.

Darius: Strong +1 on subsections. Ties into general editorial thought of needing more examples too.

### Etc

Darius: Next time we can start with 6.11 Delivery
