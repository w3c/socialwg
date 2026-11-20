# 2026-11-20 WG AP Suite Call Series A

Meeting held 10:00 Eastern Daylight Time (14:00 UTC)

## Attendance

 - Darius Kazemi
 - Evan Prodromou <acct:evanprodromou@socialwebfoundation.org>
 - Jeremiah Lee 
 - Ryan Barrett snarfed.org
 - bumblefudge.com
 - David Roetzel
 - a <trwnh.com> (they/them) (scribing)
 - Matthias Pfefferle <acct:pfefferle@notiz.blog>

## Agenda

1. Introductions, Code of Conduct
3. FPWD to-dos
    1. document Class 1, 2, 3 changes in current Editor's Draft
    2. WG Decision
    3. inform W3C Team of Decision, await approval
4. PRs to review
    1. feat: examples of inbox forwarding; Closes #557 https://github.com/w3c/activitypub/pull/678
    1. feat: examples for shared inbox delivery; closes #558 https://github.com/w3c/activitypub/pull/677
    1. feat: Update activity examples; closes #548 https://github.com/w3c/activitypub/pull/676
    1. feat: example of public addressing; closes #542 https://github.com/w3c/activitypub/pull/675
    1. feat: examples for Followers Collection; closes #539 https://github.com/w3c/activitypub/pull/674
    1. Examples for section 3.2 Retrieving objects https://github.com/w3c/activitypub/pull/673
5. AOB 
5. Continue AP suite group read through
----

## Minutes

### Introductions, Code of Conduct

Darius: installed workflow bot on GH repo
Evan: it's great!

### PRs to review

#### #678 feat: examples of inbox forwarding; Closes #557 https://github.com/w3c/activitypub/pull/678

Darius: is this non-normative? ie are all examples non-normative?
Evan: I think this, and examples in general, are class 3
Evan: a: do you know of any implementations of inbox forwarding that don't match this?
a: seems right. usually authn/authz is the difficulty -- HTTP signatures don't forward cleanly, so either embedded signatures are used or an Announce activity is used with reference which can be fetched with TLS (unless the announced object is private, in which case you need separate Authorization)

#### #677 feat: examples for shared inbox delivery; closes #558 https://github.com/w3c/activitypub/pull/677

Darius: I expect this is also class 3, same as #678
Evan: first two actors have accounts on different domains; we don't say sharedInbox has to be on same domain as actor. class 3

#### #676 feat: Update activity examples; closes #548 https://github.com/w3c/activitypub/pull/676

Darius: only id and endTime are sent, rest is omitted. Also, cross references to other examples
a: remove Content-Length header?
Ryan: remove all HTTP bits?
Evan: wanted to show where activity is going, but Content-Length yes

#### #675 feat: example of public addressing; closes #542 https://github.com/w3c/activitypub/pull/675

Evan: class 3
Darius: class 3
David: is as:Public the preferred term?
Evan: I think this is it after JSON-LD compaction. a?
a: yes since the as: prefix is applied to every URL in the doc, including values of properties like to/cc/bto/bcc/audience which are id-typed. if we do nothing, `as:Public` is what the compaction algorithm produces. if we undefine the as: prefix, then the full URL would be produced. if we defined a vocab-relative property, then `Public` would be produced. Lots of implementations don't do JSON-LD or compaction, but should handle it on the receiving side because of our non-normative note to accept all 3 of Public, as:Public, and the full URL. See https://github.com/w3c/activitypub/issues/404 for more details.

#### #674 feat: examples for Followers Collection; closes #539 https://github.com/w3c/activitypub/pull/674

Darius: class 3

#### #673 Examples for section 3.2 Retrieving objects https://github.com/w3c/activitypub/pull/673

Evan: 404 is maybe the most challenging/surprising here. could add 401/403 too
a: important to note that 404 is hiding the existence in the example
Darius: thoughts on how many examples per PR? this one has a lot but the diff is readable
Evan: it deals with one issue, which is the "atom" here
Darius: class 3

#### #637 expand on using non-HTTP ids in 3.1 Object identifiers https://github.com/w3c/activitypub/pull/637

Ryan: we maybe concluded that this is too encouraging of non-HTTP ids. is that right?
Evan: idea here is good. I'm worried about the "SHOULD keep processing" if the id scheme isn't supported
David: don't want to set false expectations that non-HTTP ids will be widely supported or work
bumblefudge: JSON-LD ids can be URLs, UURNs, etc. we could choose to require dereferenceable ids but don't have to
a: maybe need an explicit set of req'ts for all usable id schemes
Evan: extensions you can ignore are fine. extensions that aren't ignorable cause problems.
  eg if I get an at:// id with a did: actor and didn't know the relationship between them, should I continue
bumblefudge: I like a's suggestion of id req'ts! we don't have good ways of verifying unknown/unsupported info since it's unknown/unsupported
  cross-profile is a bit theoretical here with a single first profile, but still
a: how many requirements are based on id scheme vs other factors, eg authn/authz? id could be more opaque -- say you GET an object by sending a hypothetical Request activity to an actor, and you receive an object with an embedded signature. you've just sidestepped HTTP GET entirely!
bf: starts to look like a second profile where ids can be at:// URIs etc. need to understand which trust model(s) you're in
Evan: +1 with the "SHOULD continue processing" being dropped. and, drop the enumeration of schemes
Ryan: lots here! is this PR still the right next incremental step?
Darius: looking at next draft/WD iteration. could open an issue and keep discussing there
  overall people seem to support the high level idea. just incorporate the feedback
David: noting objection here as well in comments. my point of view is that specs and standards should encourage interop, and we want to stay explicitly compatible with original version of AP, and set the right expectations so that people new to AP don't have incorrect expectations of interop.
Ryan: Do you think "IDs MUST be https:" would be better, putting other concerns aside?
David: Maybe being totally flexible and not mandating anything?
Darius: Ryan, as author of the PR you are welcome to close the PR and we can give it another go, regardless of WG process; I can't force you to keep the PR open if you don't want to. This PR seems like a candidate for a PR that will go stale; we built the process so that if you don't do the updates and resolve the objections, it will close by December 11. As bumblefudge points out, anyone can open a new PR with different wording. I'm not super worried about infinite PRs sticking around ad nauseum.
Evan: I would love to see the sentiment about identifiers preserved; Ryan, it would be appreciated if you stick with it and move this through.
Darius: Even a weaker or less opinionated PR would be one step forward. We can open a new issue immediately afterward to continue the work.
Ryan: OK, I'll continue the PR.
Darius: Thank you; let's move on to FPWD.


### AOB

Darius: how's everyone feeling about new process?
  all merges are manual. closing is occasionally automatic
Evan: do you always want to merge? or can we?
Darius: process requires non-author to merge; I'm of the mindset that it was bad form to merge your own PRs. I'm happy to do the merges.

Darius: Sending out a reminder re-linking Evan's FPWD changes doc. It's sufficient for the WG to make decisions based off of it, but between now and when we make the FPWD decision, I'd like to work with you to make a more prose version of it that's easier for outside reviewers to look at. Moving to FPWD triggers horizontal review... Right now we have a sort of changelog format, it would be helpful for reviewers to have something at the top explaining "this is the narrative of what's changed" -- it might even be one paragraph. Something to contextualize the changes to someone who's never looked at AP before.


### FPWD to-dos

skipped
