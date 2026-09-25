# Legal to Build Beautiful

Source for **[legaltobuildbeautiful.com](https://legaltobuildbeautiful.com)** — *Where the Code
Binds*, a draft paper on building-regulation reform targets for traditional architecture.

---

> # ⚠️ Nothing here has been verified
>
> **This is a test site.** It was built to trial a format and a research method, not to
> publish findings.
>
> **No claim on it has been independently checked.** Not one code section number, statistic,
> quotation, date, dollar figure, or legal characterisation. There has been no fact-check, no
> expert review, no second reader, and no institutional clearance. The material was assembled
> rapidly with AI assistance and published as-is.
>
> **Do not cite it. Do not build on it. Do not quote it.**

---

## "But Section 10 lists the open items"

Section 10 lists the citations the drafting process happened to flag as unresolved. **It is a
list of known problems, not a boundary around the unknown ones.** Everything outside that
table is equally unverified — it simply hasn't been identified as suspect yet.

If you take one thing from this README: the absence of a warning next to a claim means
nothing.

## Do not use this for design, permitting, or legal decisions

The paper cites live code provisions — IBC, IRC, IECC, ADA Standards, CFR sections, municipal
zoning ordinances. Those citations exist to sketch a policy argument. They are unverified, and
they are not compliance guidance.

Three specific reasons:

1. **Model codes are not law.** They bind only where a jurisdiction adopts them, nearly always
   with local amendments. What the IBC says and what your building department enforces are
   different documents.
2. **Editions move on three-year cycles.** This paper cites the 2021 IBC because 2024 section
   numbers could not be traced at all during drafting. Your jurisdiction may be on a different
   edition.
3. **Every citation is secondary at best.** ICC's own text is paywalled; code language here was
   cross-referenced against republications by jurisdictions like Seattle. Cross-referencing
   against a republication is not verification.

Consult your building department and a licensed design professional. Nothing here is legal
advice.

## How it was made, and why that matters

The research — searching, code cross-referencing, drafting — was done with substantial AI
assistance (Claude). A human set the scope and made the editorial judgments.

This is disclosed because it predicts the *kind* of error to expect. AI-assisted research is
fast at surfacing and connecting provisions and unreliable in specific ways:

- section numbers that were correct in an earlier code edition and have since shifted
- figures confidently attached to the wrong source
- quotations that have drifted from their originals
- plausible-sounding provisions that do not exist

The process caught roughly a dozen such errors in *widely circulated claims by other people*
about codes and architecture — that is what Section 9 of the paper is for. It would be naive
to assume it caught all of its own.

## Search indexing is disabled

`robots.txt` disallows all crawlers and `index.html` carries `noindex, nofollow`. This is
deliberate: an unverified document making specific claims about live building codes should not
be findable by someone searching for those codes.

**Before re-enabling indexing**, the content needs a real fact-check. To re-enable: delete
`robots.txt` (or change it to `Allow: /`) and change the robots meta tag in `index.html` to
`index, follow`.

The link still works and can still be shared directly — it just won't rank.

## What the paper attempts

An inventory of regulatory provisions that constrain traditional architecture, sorted by how
reformable each one plausibly is: federal statute, federal regulation, model code, local
zoning. The organising claim is that advocacy has aimed mostly at the immovable tier while the
movable tier goes uncontested.

Two structural features worth preserving in any verified successor:

- **Section 9 retires claims that favour the paper's own argument.** A dozen popular assertions
  about codes and beauty appear to be wrong or inverted.
- **Section 8 states the counter-case at full strength** and reaches a conclusion some
  sympathetic readers will dislike: make beauty *legal*, not *mandatory*.

Both are argumentative structures, not verified results.

## What it is not

- Not verified
- Not reviewed
- Not citable
- Not compliance, legal, or professional design advice
- Not an institutional position of any organisation

## If you want to help

Corrections are the most useful thing anyone can send, particularly from architects, code
officials, and land-use attorneys.

- **Open an issue** on this repository, or
- Email **corrections@legaltobuildbeautiful.com**

Name the provision, the edition, and your source. A correction that destroys an argument is
worth more than one that props it up.

Also wanted: primary sources for several figures that circulate widely in this literature and
were **deliberately omitted** here because none could be found — the Somerville and Cambridge
"% of existing buildings would be illegal today" statistics, the New Jersey rehab-code outcome
percentages, and any real cost figure for NFPA 285 assembly testing.

## Attribution — unresolved

The repository sits under the `manhattan-institute-labs` organisation, but the paper carries no
author and no institutional attribution, and **is not a Manhattan Institute position**. Either
attribution goes on the page or the repository moves. The current state is ambiguous in a way
that serves nobody, and it should be settled before the link is shared beyond testing.

## Repository contents

```
index.html     the entire paper, self-contained (inline CSS, no build step)
CNAME          custom domain for GitHub Pages
robots.txt     blocks all indexing — see above before changing
sitemap.xml    vestigial while indexing is off; safe to delete
.nojekyll      skip Jekyll processing
DEPLOY.md      hosting and DNS setup notes
```

No dependencies, no build step. Edit `index.html`, commit, and Pages redeploys in about a
minute. To work locally, open the file in a browser.

One external resource loads (Google Fonts); the page renders correctly without it.

## Versioning

Bump the revision number in the masthead on any substantive change and say what changed in the
commit message. Because this is a live document with known errors, **the revision history is
part of the record** — corrections should be visible as commits, not quietly overwritten.

## License

*Not decided.* Default copyright applies until a license is added, so no reuse rights are
granted. Given the content is unverified, that is arguably the right posture for now.
