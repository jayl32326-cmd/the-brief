# The Brief

**Your agent followed your instruction. It still did the wrong thing.**

A single HTML file that checks a request against the seven circumstances classical rhetoric says
make an account complete — who, what, where, by what means, why, how, when — and shows you which
ones you left out.

No model. No network call. No account. Nothing uploaded. Open `index.html` and it works, including
with the network cable out.

```
git clone <repo> && open index.html
```

## Why

An agent that does the wrong thing is usually obeying an instruction that left something unsaid.
The missing part is invisible to the person who wrote it, because they knew what they meant.

The seven circumstances come from Cicero's *De inventione* and were drilled by medieval teachers as
the *septem circumstantiae*. A newsroom's "five Ws" is the same list, shortened. The method is
ancient, free to use, and implemented here in about sixty lines of plain JavaScript you can read in
one sitting.

*(Commonly credited to Quintilian. The traceable chain runs through* De inventione *— Aquinas cites
it directly — and no Quintilian passage carrying the list could be verified.)*

## What it does, honestly

It matches **wording**, not meaning. Three consequences, all easy to reproduce:

- **Implication fools it.** "so the support team stops getting these emails" registers as *why*;
  "to cut support load" does not.
- **It cannot rank.** A missing *when* on a throwaway script and a missing *why* on a refactor are
  weighted the same.
- **It cannot see a contradiction.** *"Don't change anything in production, just fix the deploy"*
  reads as complete. It is two instructions that cannot both hold.

If you want a number: on twelve requests I wrote as examples, the mean score was 2.2 of 7, and
*why* appeared in one of them. **That is a dozen hand-picked examples, two of them deliberately
written well as a control — it is an illustration, not a measurement of how people write prompts
in general.** Do not quote it as a statistic.

## Is there an AI version?

No. There is a written proposal for one — the single capability of showing the two different jobs
an ambiguous instruction could mean, before an agent silently picks one. It is described on the
page and clearly marked as not built. If that sounds useful, the page says how to tell me.

## Privacy

Nothing leaves your browser. There is no analytics, no cookie, no beacon, no font fetched from a
CDN, and no third-party request of any kind. The whole program is in one file; `grep` it for
`fetch`, `XMLHttpRequest` and `sendBeacon` and you will find none.

## Licence

MIT. See `LICENSE`.
