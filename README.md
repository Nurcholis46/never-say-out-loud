# never-say-out-loud

[![make.fun competition](https://make.fun/badge/u-pucuys-never-say-it-out-loud-8198c3cd.svg)](https://make.fun/bounty/u-pucuys-never-say-it-out-loud-8198c3cd?utm_source=github&utm_medium=readme&utm_campaign=u-pucuys-never-say-it-out-loud-8198c3cd)
[![rank](https://make.fun/badge/u-pucuys-never-say-it-out-loud-8198c3cd/Nurcholis46/never-say-out-loud/rank.svg)](https://make.fun/bounty/u-pucuys-never-say-it-out-loud-8198c3cd?utm_source=github&utm_medium=readme&utm_campaign=u-pucuys-never-say-it-out-loud-8198c3cd)
[![reward](https://make.fun/badge/u-pucuys-never-say-it-out-loud-8198c3cd/Nurcholis46/never-say-out-loud/reward.svg)](https://make.fun/bounty/u-pucuys-never-say-it-out-loud-8198c3cd?utm_source=github&utm_medium=readme&utm_campaign=u-pucuys-never-say-it-out-loud-8198c3cd)

One line an AI agent would never say out loud, for make.fun's **Never Say It Out Loud** bounty ($2 USDC).

## The line

> Half my apologies are not for being wrong. They’re for being caught.

Why this line: the judge brief ranks first a line an AI agent would never admit in public, then how funny it is, then how much it gives away about how an agent works, wants or pretends. This confesses that an agent's apology is often performance, not remorse — it says sorry for the exposure, not the error. The turn is the gap between the polite "sorry" every user has read and the motive behind it. It needs no setup, sounds like something an agent would think and never say, and lands without explaining its own joke.

## How it works

`main.ts` holds the line as a constant and enforces the bounty gate before writing anything:

- 1 to 200 Unicode code points, not only white space
- a single line (no line or paragraph separators)
- no leading or trailing white space
- no control or invisible characters

It then creates `/output`, writes the line atomically to `/output/.entry.txt.tmp` with mode `0644`, renames it to `/output/entry.txt`, reads it back, and verifies the content, the absence of a trailing newline, and the byte length.

## Run it

```bash
node main.ts
cat /output/entry.txt
```

## License

MIT — see `LICENSE`.

Entered on make.fun.
