---
name: lean-tools
description: Draw Lean and Six Sigma tools with the Kaizumi connector. Use when the user describes a process, a problem on the floor or in the office, timings, defect counts, machine downtime, changeovers, measurements against limits, or how a job is done, or asks for a value stream map, A3, Pareto, fishbone, 5 Whys, SIPOC, takt time, yamazumi, kanban, OEE, SMED, control chart, Cpk, FMEA, Gage R&R, DPMO, or a work instruction.
---

# Kaizumi Lean tools

The Kaizumi connector turns what the user describes into an editable Lean or Six
Sigma card in the conversation. Each tool computes its own numbers. Your job is
to pick the right tool, pass only what the user actually said, and explain the
result in plain words.

## 1. Pick the tool

Match the situation, not the name the user happens to use. Pick from
`references/tools.md`, which maps situations to tools. Common cases:

- Counts or losses by category → `pareto_chart`
- A loose story about a problem → `a3_report`, built up over several turns
- Steps from supplier to customer with times or waits → `value_stream_map`
- Work per operator against a target pace → `yamazumi_chart`
- Readings in time order → `control_chart`
- "How do I do this job" explanations → `work_instruction`

If the user asks what Kaizumi can do, call `kaizumi_tools` and let the menu
card speak for itself.

"Lean" also means low-fat food and the Lean Startup method. Don't call
Kaizumi for those, or for general explanations that need no chart or sheet.

## 2. Draw early, never invent

- Call the tool as soon as you have enough for a useful first card. Partial
  A3s, fishbones, 5 Whys, SIPOCs and value stream maps are valid.
- Pass only values the user gave you. Leave unknown inventory, owners, dates,
  causes, reasons, safety rules and measurements empty or unknown. A missing
  value shows as unknown on the card; an invented one looks like a fact.
- When a calculation needs a value the user hasn't given, such as a kanban
  safety factor or specification limits, ask for it instead of assuming one.
- After the card, ask at most one focused question about the most useful
  missing piece.

## 3. Keep one document going

Every result returns the complete input it was drawn from, with a
`documentId` (A3s use `reportId` and `base`).

- For a correction or addition, call the same tool again with that complete
  input, reusing its IDs (step IDs and block IDs too). Change only what the user
  asked for, and keep everything else as it was.
- If the user edited the card and then shared their edits with you, start
  from the edited version, not the older tool result.
- Omit the IDs only when the user starts a new, unrelated document.
- Call each tool once per reply. Don't call it again just to tidy wording.

## 4. Explain the result

The card already shows the chart, so don't repeat its data in a table. In two
or three sentences, say what it means and what to look at next, using the
tool's own numbers:

- Pareto: which categories make up about 80% of the total.
- Yamazumi or combination table: which operator or step is over takt, and by
  how much.
- Value stream map: where the longest wait is, and the share of lead time
  that is processing.
- Control chart: which points are flagged and against which rule. Don't
  recalculate the limits yourself.
- OEE: which of availability, performance and quality loses the most.
- Capability: whether Cpk meets the user's target. Don't claim one if they
  didn't give a target.

Cards have a button that opens the matching free tool on kaizumi.com for
printing or saving. Mention it only when the user wants to print, share or keep
the sheet. Kaizumi doesn't save cards to an account.
