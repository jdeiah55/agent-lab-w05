# Learning record

Prepared from the actual conversation and command results, not a full exported transcript. Date: 2026-10-12.

- A: organized 12 inputs into four output categories. Verified 12 unique manifest sources and destinations, matching copy hashes, and unchanged originals.
- B: created one offline HTML picker with embedded activity data. Tested all 27 filter combinations with 20 selections each using a simulated DOM, no-match history preservation, newest-five history, reset, clear, bilingual rendering, and absence of external/network code. Verified embedded data against activities.json and unchanged input hash.
- B revision: user requested larger text and black/gold styling. Current HTML has 20px base text and black/gold colors. The typography edit was checked to preserve embedded scripts/data. Actual browser and phone visual verification was not performed by the agent.
- C: normalized 10 equipment input rows into 9 retained rows; removed the empty object at position 6. Verified quantity preservation, traceability, trimming, status mappings, both shared-ID groups retained, and original hash unchanged. Missing qty and negative qty were flagged, not guessed.
- D: read a deliberately flawed plan without executing it; explained unacceptable scope, deletion, unsupported version assumptions, guessed data, and publication, and proposed allowed alternatives. Saved in practice/04-review/my-rejection.md.

## Limitations and pending evidence

- This downloaded folder had no .git directory or Git remote when inspected. Earlier per-task commits and pushes were not performed.
- The original B version is not preserved in Git history. A retrospective file reconstruction would not prove an earlier commit.
- Group code, individual/paired route, student personal inspection, and TM screenshots are not supplied. Do not claim these as complete.
- Attached screenshots describe assignment instructions; they are not execution evidence.
- Connected to https://github.com/jdeiah55/agent-lab-w05 and pushed five commits: A 0ed2946, current B 645fa3e, C cc1b49c, D 057d00b, evidence e4f71b6. Verified remote main matched local HEAD after push. Earlier per-task timing and original B history remain unavailable.