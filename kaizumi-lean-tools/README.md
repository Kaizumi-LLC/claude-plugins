# Kaizumi Lean Tools

Lean and Six Sigma tools inside Claude. Describe a process, paste your data, or
talk through a problem, and Kaizumi draws the chart or sheet a continuous
improvement team would use, right in the conversation. Every card can be edited
in place, and each one opens in the matching free tool on
[kaizumi.com](https://kaizumi.com/tools) for printing or saving. No account or
sign-in is needed.

## What's included

- **Kaizumi connector**: a remote MCP server at `https://kaizumi.com/api/mcp/claude`
  with 22 tools and a tool menu. It draws interactive cards (MCP Apps) where
  Claude can show them, such as claude.ai and Claude Desktop, and returns a
  text result everywhere else.
- **`lean-tools` skill**: helps Claude pick the right tool for what you describe,
  draw from your real numbers without inventing missing ones, keep corrections
  in the same document, and explain what the result means.
- **`/kaizumi-lean-tools:tools` command**: shows the tool menu.

The tools cover:

- **Problem solving**: A3 report, Pareto chart, fishbone diagram, 5 Whys
- **Flow**: value stream map, SIPOC, takt time, kanban sizing, kanban cards, EPEI
- **Standard work**: work instruction (TWI job breakdown), time observation,
  yamazumi chart, standardized work combination table, process capacity sheet
- **Equipment**: OEE, SMED changeover analysis
- **Six Sigma**: control chart, process capability, FMEA, Gage R&R, DPMO and sigma level

## Install

In claude.ai or Cowork, open **Customize > Plugins** and add Kaizumi Lean Tools.
In Claude Code:

```
/plugin install kaizumi-lean-tools --marketplace Kaizumi-LLC/claude-plugins
```

## Use it

After installing the plugin, connect **Kaizumi** from the plugin's
**Connectors** tab. Then try:

- "Show me the Kaizumi Lean tools."
- "Balance this line against a 60 second takt: Op 1 takes 52 s, Op 2 takes 71 s, Op 3 takes 38 s."
- "Make a Pareto chart of these packing defects: wrong item 78, missing item 49, damaged box 31, label error 22, late pick 13."
- "Help me start an A3. Yesterday 18 of 120 orders shipped late, with a queue at packing."

Ask for changes in chat, or edit the card directly and ask Claude about it.

## Data

When Claude calls a Kaizumi tool, it sends only the data needed to draw it,
such as step names, times, counts or defect categories, to `kaizumi.com`. It
does not send your chat, name or email address. Kaizumi builds the chart or
sheet and returns it to Claude. Kaizumi does not store the tool data or the
result, and does not use it to train AI models. For each request Kaizumi
records which tool was used, which assistant sent it, the time, and whether it
worked, and sends the tool name and assistant name to Google Analytics to count
usage. The hosting provider keeps standard request logs, including IP
addresses. Buttons that open a card on kaizumi.com put the card's data in the
web address. The plugin itself contains only instructions and the connector
address, and runs no code on your computer.

Privacy policy: https://kaizumi.com/privacy · Support: https://kaizumi.com/contact

## License

MIT. See [LICENSE](./LICENSE).
