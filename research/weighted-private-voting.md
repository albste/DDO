# Weighted voting with strong privacy

The weakest point of DDO and an open research problem.

## The problem

DDO gives every citizen a baseline vote and extra, capped weight for verified competence in a specific domain. Voters must prove eligibility and weight without revealing who they are, and anyone must be able to verify the result. The tension: a weight tier carries information. A rare combination of tiers can single out a voter, which is a fingerprinting risk and a route to coercion.

## What is needed

- Eligibility and weight proven in zero knowledge, without linking to identity.
- Per-question nullifiers so nobody votes twice on the same question.
- Weight tiers coarse enough that the anonymity set stays large.
- Receipt-free voting and re-voting until the window closes (the last vote counts).
- Public verifiability of the tally.

## Known gaps

- Fingerprinting from rare tier combinations in small communities.
- Cost and performance of zero-knowledge circuits for weight tiers (to be benchmarked on real circuits).
- Coercion resistance for remote voting at scale.
- Formal modelling of the scoring system against gaming.

## Approach in the roadmap

The phase 1 prototype has no zero-knowledge and documents the privacy gaps. Unlinkable credentials and nullifiers come in the community pilot, zero-knowledge weight tiers in the municipal pilot. See section 13 of the technical specification.

## How to help

Propose constructions, attacks, anonymity-set analyses or benchmarks. Open an issue referencing this file.
