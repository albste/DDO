# Proposed repository structure

Suggested name: `ddo` (or `ddo-protocol`). Documents are numbered so they read in order, with one folder per language.

```text
ddo/
├── README.md                      English entry point
├── README.it.md                   Italian entry point
├── LICENSE                        full text of CC BY-SA 4.0
├── CONTRIBUTING.md                how to critique, propose and translate
├── CODE_OF_CONDUCT.md             rules for respectful discussion
├── CHANGELOG.md                   version history of the documents
├── docs/
│   ├── en/
│   │   ├── 01-whitepaper.md
│   │   ├── 02-charter-of-fundamental-rights.md
│   │   ├── 03-technical-specification.md
│   │   └── 04-product-and-interface.md
│   ├── it/
│   │   ├── 01-whitepaper.md
│   │   ├── 02-carta-dei-diritti-fondamentali.md
│   │   ├── 03-specifica-tecnica.md
│   │   └── 04-prodotto-e-interfaccia.md
│   └── assets/
│       └── diagrams/
│           ├── roadmap.svg
│           └── architecture.svg
├── discussions/
│   ├── open-questions.md          questions the documents leave open
│   └── decisions/                 accepted changes, each with its reasons
├── research/
│   └── weighted-private-voting.md the weakest point, collected in one place
├── pilots/
│   ├── README.md                  how a community can run a pilot
│   └── founding-vote-template.md  parameters a founding vote must decide
├── code/                          empty until phase 1 (prototype)
│   └── README.md
└── .github/                       optional, add when you want it
    ├── ISSUE_TEMPLATE/
    │   ├── critique.md
    │   ├── proposal.md
    │   └── translation.md
    └── PULL_REQUEST_TEMPLATE.md
```

## Notes on the structure

- **`LICENSE`:** download the full legal text from creativecommons.org/licenses/by-sa/4.0/legalcode.txt and save it unchanged.
- **`discussions/open-questions.md`:** start it by collecting the open-question lists from the whitepaper, the Charter and the technical specification, so critics see where help is most needed.
- **`research/`:** weighted voting with strong privacy is the weakest point; a dedicated file lets researchers work on it directly.
- **`code/`:** keep it empty and say so, because the roadmap puts code in phase 1.
- **`.github/`:** you said not to rely on pull requests for now, so this folder is optional. Issues and discussions are enough at the start.
- **Diagrams:** the roadmap and architecture drawings exist as images inside the docs. Export them as SVG into `docs/assets/diagrams/` and reference them from the Markdown files.
