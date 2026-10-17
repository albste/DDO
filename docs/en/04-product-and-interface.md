# DDO Product and Interface

### Draft of the public website and the app: what they contain, what they show, what can be consulted

by **albste** · Oct 17, 2026 · Version 0.1 · License: CC BY-SA 4.0

Companion to the DDO Whitepaper and Technical Specification. It describes the product as the citizen sees it: the sections, the life cycle of a proposal, the map of the state economy, the sheet a voter sees before voting, factions and comments. It is a design proposal, not a final interface specification: parameters marked "open" are left to each pilot's founding vote. The same warning as the Technical Specification applies: nothing here should be used for binding votes before independent review and audit.

## 1. Why this document exists

The Whitepaper says how decisions are made and the Technical Specification says how the vote is protected. A simpler question was missing: where does all of this live? In DDO every step, from proposal to outcome, starts and is consulted in the same place. If a decision is not visible there, as far as the system is concerned it does not exist.

Three principles guide the rest of the document. They follow from the Whitepaper principles, in particular "Verifiability with privacy" and "Open by design":

1. **One source.** The website and the app show the same data, taken from the same public records. No official information exists only inside one product.
2. **Every decision has a readable effect.** A proposal that moves money must show, in a navigable way, what changes in the state accounts before and after.
3. **Voters see the whole picture.** Positions, numbers, risks, changes and debate are presented in the same format for every proposal, and nobody can choose what to put first.

## 2. Two products, the same functions

DDO has two separate products that do the same things.

- **Public website.** Opens in any browser, with no account. Anyone, including people who are not eligible citizens, can read everything: proposals, factions, comments, outcomes, the economic map, the records.
- **Citizen app.** This is the wallet from the Technical Specification (section 4) with the full interface. It keeps keys in secure hardware and performs the actions that require an identity.

Actions (proposing, supporting, joining a faction, commenting, voting) require an eligibility proof. On the website the proof comes from the citizen's wallet, through a QR code or a direct link to the app, so keys stay on the device. Booths run the same client.

| Function | Public website | Citizen app |
| --- | --- | --- |
| Read proposals, factions, comments, outcomes | Yes, no login | Yes |
| Browse the state economy map | Yes, no login | Yes |
| Verify records, receipts and tallies | Yes | Yes |
| Propose, support, join a faction | With wallet linked | Yes |
| Comment (including anonymously) | With wallet linked | Yes |
| Vote | With wallet linked | Yes |
| Key custody | Never in the website | Secure hardware of the device |
| Notifications and deadline reminders | Optional | Yes |
| Offline use for enrolment and assisted voting | No | Through booths |

Both products share a common core (data formats, public read interface, interface components) and both are open source. The read interface is public and documented, so anyone can build a third client or an independent dashboard. If the website and the app showed different things, verification would be left to whoever runs them, which is exactly what DDO wants to avoid.

## 3. Map of sections

Same structure in both products.

| Section | Content |
| --- | --- |
| **Proposals** | All proposals by state (draft, gathering support, deliberation, voting, closed, locked). Search and filters by domain, territory, law type and economic impact |
| **Votes** | Open and upcoming votes that concern the citizen, with deadlines |
| **Outcomes** | Results, verification proofs, the approved version of the law and the end of its lock period |
| **State economy** | The navigable map of revenue, debt, assets and destinations, with its history (section 5) |
| **Records** | Published ballots, checkpoints, scoring rule versions, audit trails, actions of mediators and operators |
| **My space** | Credentials, domains and weight bands, memberships, comments, receipts for one's own votes, accesses to one's data by authorities (Whitepaper section 6) |
| **Rules** | Thresholds, voting windows, lock periods, weight cap and the Charter of Fundamental Rights, current and past versions |
| **Mediators and operators** | Who is in office, term, expiry and the record of their actions |

## 4. The life cycle of a proposal

Every proposal goes through the same stages, and each stage leaves a consultable trace. The stages follow the Whitepaper cycle (section 3) and make deliberation and post-outcome monitoring explicit.

| Stage | What happens | What can be consulted |
| --- | --- | --- |
| **1. Draft** | A citizen writes the proposal, picks the domain and law type and, if needed, the change to the economic map | Text, versions, author (or proposing mediator) |
| **2. Gathering support** | The proposal collects support up to the threshold for its law type | Number of supporters, threshold, time left |
| **3. Impact check** | Automatic checks on the economic map, on conflicts with locked laws and with the Charter. Anyone can flag an undeclared impact | Check results, flags and replies |
| **4. Deliberation** | Mandatory period in which factions form, people join, comment and amend | Factions, memberships, comments, risks, amendments |
| **5. Vote** | Voting window with the sheet described in section 7 | The sheet, one's own receipt, time left |
| **6. Tally and outcome** | Result and proofs published at close | Result, tally proofs, record |
| **7. Lock and execution** | The law is locked; if it has economic effects, real movements are compared with those approved | End of lock, economic map "approved versus actual" |

Gathering support and deliberation are two different things. The first decides whether a proposal deserves to be discussed, the second whether it has been discussed enough to be voted on. The minimum length of deliberation is a founding vote parameter, as the Whitepaper requires (section 10, "Populism and manipulation").

## 5. State economy: the navigable map

### 5.1 What it shows

The **State economy** section is a large map that can be scrolled and zoomed, representing all public assets and their movements. It has four kinds of element.

- **Revenue.** Taxes, fees, contributions, income, transfers received.
- **Assets.** Funds, accounts, property, holdings, reserves.
- **Debt.** Creditor, amount, rate, maturity.
- **Destinations.** Where the money goes: domains (health, education, infrastructure, ...), bodies, territories, projects.

Elements are linked by **flows**: amount, periodicity and legal basis. Each flow points to the law or proposal that established it. From the map you can always go back to the decision and, from the decision, to who voted on it and with what outcome.

### 5.2 How to navigate it

- **Zoom by levels.** You start from the overview of the state (a few large items), then go down into domains, bodies, and individual items and projects. At each level the totals match those of the level above.
- **Free panning.** Drag and zoom by touch, mouse or keyboard, with a minimap so you don't get lost.
- **Time.** A time slider shows the map at any date and lets you compare two dates.
- **Filters and search.** By domain, territory, body, creditor, amount, proposal or law.
- **Paths.** Selecting a flow highlights the path upstream (where the money comes from) and downstream (where it goes).
- **Three views of values.** *Approved* (decided by citizens), *actual* (observed from data published by bodies) and *proposed* (in ongoing proposals). Gaps between approved and actual are highlighted.
- **Table view.** Every screen has a table equivalent, for accessibility, screen readers and comparison. Data can be downloaded in an open format.

### 5.3 How it is built and who updates it

The map is a versioned data set. **Nobody edits it directly**, not even operators. It changes in only two ways.

1. **Citizens' decision.** An approved proposal applies its change to the map (section 6). The new version references the proposal and the vote record.
2. **Observed data.** Public bodies publish real movements with a digital signature. These update the *actual* view but never change *approved*. If the two diverge, the divergence is public and stays visible.

Map versions and checkpoints live in the transparency log (Technical Specification, section 3), like other records. They are public data with no personal data, so erasure rights raise no problem.

**Consistency checks.** Every version must meet rules anyone can verify: outflows do not exceed inflows plus the change in balances; a balance does not go negative without being declared as new debt; the totals of each level match the sum of the levels below; no flow violates a law in its lock period.

**In pilots.** A community pilot has no state budget. The map covers the community's own funds (dues, contributions, common goods), with the same structure. It moves to the data of a municipality or a state only if the body publishes it.

## 6. Proposals that move money

**Rule.** A proposal that requires an allocation of money or a transfer of funds must also include the proposed change to the economic map. Without it, it cannot leave the draft stage.

### 6.1 The change to the map

The author uses the same map editor and states the changes: new flow, reduced or removed flow, reduced fund, new debt, new revenue, a tax increase. The system computes and shows:

- the map **before** and **after**, with only the changed parts highlighted;
- the effect on totals: balance, debt, spending by domain, impact by territory;
- the **coverage**: where the money comes from. Every expense must name a source (reduction of another item, new revenue, use of reserves or new debt) and the source is shown at the same level as the expense, never hidden;
- the constraints violated, if any. A proposal that violates them does not move on to support.

### 6.2 Undeclared impacts

A proposal can have economic effects the author did not declare, by mistake or by choice. To limit this:

- the author states whether it moves money; if the answer is no, the change to the map is empty;
- in the impact check (stage 3) any eligible citizen can flag an undeclared impact, attaching an estimate;
- the flag and the author's reply are public. If a flag is upheld, the proposal returns to draft to add the map change; the criterion for upholding is a rule voted in advance, not a discretionary decision by an operator.

### 6.3 After approval

If the proposal passes, its map change becomes a new version of **approved**. When the executing body publishes real movements, the **actual** view is compared with it. A gap beyond an agreed threshold creates a public flag, linked to the proposal. A proposal that does not stay within its economic limits is visible.

## 7. The voting sheet: what voters see

When a proposal passes the support threshold and deliberation, eligible voters find the same **information sheet**, in the same format for every proposal. There is no way to present it more favourably.

```text
┌──────────────────────────────────────────────────────────────┐
│ PROPOSAL  #482 · Territorial · Domain: Transport             │
│ Open until Nov 24 · Expected lock: 2 years                   │
├──────────────────────────────────────────────────────────────┤
│ 1. SUMMARY             What changes, in a few lines  [Text]  │
│ 2. FACTIONS            Faction A   312 members               │
│                        Faction B   187 members               │
│                        Faction C    64 members               │
│                        No membership declared      1,040     │
│ 3. ECONOMY             Before/After on the map  [Open map]   │
│                        Spend 4.2 M · Coverage: cut to        │
│                        item X (2.0 M) + new debt (2.2 M)     │
│ 4. WHAT CHANGES        Laws/rules/flows touched              │
│ 5. RISKS               Declared · Flagged · Automatic checks │
│ 6. COMMENTS            By faction · Named or anonymous       │
├──────────────────────────────────────────────────────────────┤
│ [ VOTE ]   You can revote until close (the last one counts)  │
└──────────────────────────────────────────────────────────────┘
```

### 7.1 Factions and number of members

A **faction** is a position on a proposal, with a name and a short statement. There are factions in favour, against, in favour with changes, and alternatives.

- The author's faction is created with the proposal. Any eligible citizen can propose another during deliberation; a faction appears on the sheet only with a minimum number of members (open parameter), to avoid a proliferation of empty factions.
- Each eligible citizen can join **only one faction** per proposal and change it until deliberation closes.
- **Membership is not the vote.** It is a declaration of position. It does not bind them, does not reveal their vote and does not anticipate the tally. The sheet says so explicitly ("declared members, not votes").
- The number of members is public, but **not who they are**. Membership uses the same eligibility proof and per-proposal nullifier as voting (Technical Specification, section 5): one membership per person, not linkable to identity or to memberships on other proposals.
- Factions appear in random order for each visitor, not by size.
- The figure shown is a head count. Weight bands from weighted voting do not appear in memberships, to avoid reducing vote privacy.
- Each faction can attach an **amendment**, a variant of the text or of the economic change. The author can accept it; otherwise it becomes a competing proposal with its own sheet (open question in section 11).

### 7.2 Proposed economic change

The "Economy" part of the sheet is the map change from section 6, as a before/after comparison. Voters can open it on the map and navigate it at every level. If a faction has an economic amendment, the map also shows the variant.

### 7.3 Risks

Risks are collected from three sources, kept distinct by origin:

- **declared by the author**, mandatory, with estimated probability and impact and mitigations;
- **flagged by citizens**, those added by factions or individuals during deliberation, with their estimate;
- **automatic checks**: constraint violations, weak coverage, effects on debt, territorial concentration of spending.

A sheet with an empty Risks section says so (no risk declared or flagged); it does not hide the section.

### 7.4 What changes

The precise list of what approval changes: new or amended law text (with a diff), rules touched, economic map flows, related laws and, if any, the lock periods involved. It is the same information as the change list in a code review: voters know what really changes.

### 7.5 Comments by faction

Comments are shown **grouped by faction**, so the arguments of each position can be read. A chronological view of everything is also available. Replies, reports and sorting by date or by reader-declared relevance are provided.

## 8. Comments, anonymity and moderation

**Who can comment.** Citizens eligible to vote on the proposal. People who are not eligible read but do not write, so the debate reflects those involved and outside invasions are less likely (open question in section 11).

**Two modes, chosen by the author.**

- **Named.** The comment is signed with a public name chosen by the citizen.
- **Anonymous.** The comment is not linked to any identity. The wallet proves, with a zero-knowledge proof, that the author is eligible and produces a per-proposal label. Within the same proposal it appears as "Anonymous 17", consistent across their comments; on another proposal it is a different label and nobody can link the two.

In both modes the comment carries the label of the author's faction, if they joined one. An anonymous comment reveals neither a name nor anything beyond the faction and the proposal.

**Limits and abuse.** Anonymity must not become a tool for abuse or manipulation.

- An anonymous label is unique per person and per proposal, so the rate of comments can be limited and a label blocked on that proposal only, without tracing the person.
- Moderation acts on reports. A removed comment always leaves a trace with the reason (illegal, off-topic, personal attack), does not vanish silently, and the removal can be contested. The decision is made by a panel drawn by lot from eligible citizens, not by an operator; enforcement follows Article 4 of the Charter (due process).
- No operator, and no authority, can trace the author of an anonymous comment: the system does not keep that link, so there is nothing to hand over.

**Where comments live.** Comments may contain personal data written by their author, so the text stays outside the log, in encrypted conventional storage. Only cryptographic commitments (hashes) go on the log, so edits and deletions can be proven without the log containing the texts (Technical Specification, section 10).

**Small groups.** In a very small territory or faction, the count alone can identify people. Below a minimum number (open parameter) the system shows a range instead of the exact number and does not show the faction next to an anonymous comment.

## 9. What goes on the log and what stays off

| Data | Where | Why |
| --- | --- | --- |
| Proposal text and versions (hash and reference) | Log | Prove what was put to the vote |
| Changes to the economic map and its versions | Log | Public data, no personal data |
| Faction definitions, membership counts and nullifiers | Log | Verifiable count, no identity |
| Ballots, outcomes and tally proofs | Log | Universal verifiability |
| Cryptographic commitments of comments and removals | Log | Prove edits and deletions |
| Comment text | Off-log, encrypted storage | May contain personal data |
| Data observed from bodies (actual movements) | Log, signed by the body | Public comparison between approved and actual |
| Search indexes, thumbnails, notifications | Off-log | Convenience services, rebuildable from the logs |

## 10. Risks

| Risk | Why it matters | Proposed mitigation |
| --- | --- | --- |
| Map full of errors or false data | Decisions rest on wrong numbers | Data signed by bodies, approved/actual comparison, public flags, audits |
| Map too complex | Too much detail discourages voters | Zoom by levels, summary at each level, table view, always consistent totals |
| Economic impacts hidden in a proposal | Undeclared spending | Impact flags, return to draft, comparison with real movements |
| Membership counts sway the vote | Bandwagon effect: people join the largest faction | Random faction order, explicit "not votes" label, counts shown as numbers and not percentages |
| Brigading and outside coordination | Organised comments to shift the debate | Only eligible citizens write, rate limit per label, traced removals |
| Harassment behind anonymity | Anonymous authors answer to nobody | Per-label per-proposal block, moderation by lot with public trace, contestation |
| Identification by exclusion | In small groups people can be traced | Minimum thresholds, ranges instead of exact numbers |
| Disinformation in comments | False data presented as fact | Comments with linkable sources, flagging, risks and automatic checks shown separately |
| Digital divide | People who do not use the app or site miss this information | Public booths with the same sheet, printed sheet, assisted voting |
| Information overload | The sheet becomes too long to read | Fixed six-block structure, summary on top, detail on request |

## 11. Open questions

- How should voting work when a faction brings an amendment that is incompatible with the proposal: multi-option vote, runoff, or separate competing proposals?
- Should people not eligible to vote on a proposal be allowed to comment? Would a limited opening (for example residents or domain experts) improve the debate or open a door to manipulation?
- How many members does a faction need to appear on the sheet, and which minimum thresholds protect small groups?
- How do we keep the *actual* view reliable when bodies publish data late or incompletely?
- Should the website allow voting with a software key (less secure than device hardware), or only linking to the app's wallet?
- To what level of detail should the map cover individual contracts and suppliers, without exposing commercial or personal data?
- What exact criteria decide whether an undeclared-impact flag is upheld, and who applies them?

## 12. Development aligned with the roadmap

1. **Specification and prototype.** Read-only public website with the proposal life cycle and the map viewer on sample data. Economic change editor and consistency checks. Factions and comments under a name, without cryptographic anonymity (privacy gaps documented, as in the Technical Specification).
2. **Community pilot.** App with wallet, faction membership with per-proposal nullifier, anonymous comments, full voting sheet, map of the community's own funds.
3. **Municipal pilot.** Map on real municipal data published and signed by the body, approved/actual comparison, moderation by lot, booths with the same sheet, full accessibility.
4. **Scale-up.** Upper levels of the map (more bodies and territories), third-party dashboards on the read interface, parameter review in light of the pilots.

## License

Released under [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/). Credit the original author, **albste**, indicate changes and share derivative works under the same license.
