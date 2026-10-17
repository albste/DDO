# Open questions

Collected from the documents, so critics see where help is most needed. The weakest point is weighted voting with strong privacy (see [research/weighted-private-voting.md](../research/weighted-private-voting.md)).

## Whitepaper (section 10)

- How should domains be defined and who may create new ones?
- How much extra weight is acceptable before the system stops feeling fair?
- How can deliberation be built into a fast online process without making it exclusive?
- How should a pilot handle people who refuse to take part?
- What should happen when two valid laws, from different domains, conflict?

## Charter of Fundamental Rights

- Is a lot-selected review panel enough to resolve disputes about the Charter, or does it become a hidden power centre?
- Which rights are missing, and which listed here are too broad to justify limiting citizens' decisions?
- How should the Charter relate to a host country's own constitution during pilots?
- Where should the line sit between protecting a minority and blocking a legitimate majority decision?

## Technical specification (section 14, open research problems)

- Weighted ballots with strong privacy and low fingerprinting risk.
- Practical coercion resistance for remote voting at scale.
- Usable social recovery that does not become a new attack path.
- Sybil-resistant enrolment for people without official identity documents.
- Governance of trustees and witnesses: who they are, and how they are replaced.
- Formal modelling of the scoring system against gaming.

## Product and interface (section 11)

- How should voting work when a faction brings an amendment incompatible with the proposal: multi-option vote, runoff, or separate competing proposals?
- Should people not eligible to vote on a proposal be allowed to comment?
- How many members does a faction need to appear on the voting sheet, and which thresholds protect small groups?
- How do we keep the actual-spending view of the state economy map reliable when bodies publish late or incompletely?
- Should the website allow voting with a software key, or only linking to the app's wallet?
- To what level of detail should the map cover individual contracts and suppliers?
- What exact criteria decide whether an undeclared-impact flag is upheld, and who applies them?

## Parameters left to the founding vote

Voting conditions, support thresholds, scoring rules, weight cap and decay, voting windows and lock periods, candidacy requirements, Charter amendment supermajority and delays, and the aggregate limit on any group's share of weight. See [pilots/founding-vote-template.md](../pilots/founding-vote-template.md).
