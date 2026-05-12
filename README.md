# Yantra · CredMitra cockpit — three visualization directions

Self-contained HTML mockups exploring how an AI-native operations cockpit for an Indian MSME lending business process could look, derived from the CredMitra design-system reference (which itself transposes the Anthropic "memory + dreaming" SRE demo onto Indian financial services).

Open **`index.html`** in a browser. Three tabs at the top swap between directions; the "side-by-side" toggle on the right renders all three scaled down in one viewport.

## Three directions

All three render the same loan-origination cockpit with the same three example applications and the same design-system tokens (colour ramps, monospace-for-machine vs sans-for-human, agent identity swatches). They differ in spatial / interaction paradigm.

| # | File | Paradigm | Best for |
|---|------|----------|----------|
| 01 | `option-1-channel.html` | Slack-style channels on the left; work items render as posts in the stream with agents as nested child rows. | Operators who live in channel-based tooling already; clearest expression of "agent is the executor of the work item". |
| 02 | `option-2-terminal.html` | Dark, monospace-forward tail. Histogram strip, command bar, tabular trace lines. | High-volume estates where information density matters more than friendliness; closest to the original Anthropic SRE demo aesthetic. |
| 03 | `option-3-pipeline.html` | Kanban swim-lanes — Intake → Underwriting → Fraud → HITL → Decided — with cards that carry their nested agent rows. | COOs and ops floors who think in flow / WIP / bottlenecks; makes lane-level health and stage transitions explicit. |

## Shared example data

- **app_8821** · Pune steel-fab · ₹18L · *paused for HITL* — uw-agent recommends ₹15L, two ambers (kyc address mismatch, OCR conf 0.71), fraud cleared.
- **app_8819** · Hyderabad trading · ₹8L · *escalated* — fraud-agent detected loan-stacking (4 enquiries / 11d).
- **app_8825** · Coimbatore textile · ₹12L · *live* — uw-agent in step 3 of 6, banking analyser running.

## Design principles surfaced in every view

1. Work item is the unit, agent renders as its child.
2. Provenance is visible, not buried — every READ / RAN / WROTE has inline memory-store tags.
3. Memory has permissions, versions, and writer attribution — right rail shows org (RO) vs team (RW) stores with version chips.
4. Agents collaborate through files, not orchestration — sibling agents under the same work item.
5. Humans unblock agents, they don't redo their work — HITL banner with "approve · resume" framing.
