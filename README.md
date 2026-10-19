# Android TV Package Manager

<img width="1239" height="929" alt="image" src="https://github.com/user-attachments/assets/25ce379a-55c4-44a8-9d83-d52b49aced7c" />


Find your Android TV on your home network and choose which apps to disable or turn back on, using a simple Windows app.

**Enable debugging on the TV → open `TVAppManager.exe` → connect.**

Everything needed to run the program is included. **No Python installation or commands required.**

## What you need

- A **64-bit Windows PC**.
- An **Android TV or Google TV** that supports network debugging.
- Both devices connected to the **same home network**, using Wi-Fi or a network cable.
- The TV switched on, with its remote handy to approve the connection.

## 1. Enable debugging on your TV

Already enabled it? Skip to step 2.

1. Open the TV's **Settings** and find **About**, usually under **System** or **Device Preferences**.
2. Find **Build**, **Build number**, or **Android TV OS build**. Select it with the remote **seven times**, until developer mode is enabled.
3. Go back to **System** or **Device Preferences** and open **Developer options**.
4. Turn on **USB debugging** or **ADB debugging** and accept the prompt. If there is a separate **Network debugging** or **ADB over network** option, enable that too.
5. Return to the TV's home screen.

Menu names vary by TV. See [Google's Developer options guide](https://developer.android.com/studio/debug/dev-options#enable) if you need help finding the setting.

Despite the name “USB debugging”, this program connects over your network and does not need a USB cable. Some TVs need wireless pairing instead; see the help section below. USB debugging alone does not enable network access on every model.

## 2. Download and open the program

1. At the top of this GitHub page, click **Code → Download ZIP**.
2. Right-click the downloaded ZIP and choose **Extract All**.
3. Open the extracted folder and double-click **`TVAppManager.exe`**.

**Keep the whole folder together.** The `adb` folder, including its DLL files, must stay beside `TVAppManager.exe`. ADB is the included tool that talks to your TV; you do not need to open it yourself.

## 3. Connect to your TV

1. Wait for the program to find devices, or click **Discover TVs**.
2. Select your TV and click **Connect**.
3. Look at the TV screen and **allow the debugging connection** if prompted. Choose **Always allow from this computer** only for your own trusted PC.
4. If the program says **unauthorized**, accept the TV prompt and click **Connect** again.

Your installed apps will appear, along with their current enabled or disabled state. You normally do not need to know the TV's IP address.

**Everything starts unselected. Discovering and connecting do not disable anything.**

## 4. Choose what to disable

Read the **Disabling assessment** beside each app. Click its row to see the explanation.

| Assessment | What to do |
| --- | --- |
| **Optional if unused** | Consider disabling it if you do not use that app or its features. |
| **Test individually** | Try one at a time and check that the TV still works normally. |
| **Keep for features** | Keep it if you use the feature described, such as casting or accessibility. |
| **Leave alone** | Keep it enabled; it is a core component or other apps may depend on it. |
| **Unreviewed: leave alone** | Its role is unconfirmed. Leave it alone if you are unsure. |

To make a change:

1. **Tick the checkbox** beside an app. Clicking its name alone does not select it.
2. Click **Disable selected**.
3. Review the TV and app names, then confirm.
4. Check Home, Settings and your usual apps before disabling anything else.

Start with one optional app you recognise and do not use. Some entries are important background services, and the assessments cannot guarantee the same result on every TV.

**Disabling turns an app off; it does not uninstall it.**

### Turn an app back on

Connect to the TV, click **Refresh apps**, and choose **Disabled** in the state filter. Tick the app, click **Re-enable selected**, and confirm.

Closing the program does not undo changes. Apps that were already disabled stay that way until you choose to re-enable them.

### Finding and selecting apps

Use **Search** or the state filter to find an app. Filters can hide checked apps without unchecking them, so review the complete confirmation list. **Clear selection** unticks everything. Refreshing or reconnecting also clears selections.

## Need a hand?

| Problem | What to try |
| --- | --- |
| **No Developer options** | Select the **Build** entry in About seven times, rather than Android version. |
| **TV not found** | Wake the TV, check debugging and confirm both devices are on the same home network. Avoid guest Wi-Fi. Click **Discover TVs** again. |
| **TV found, but connection fails** | Look for the TV's approval prompt. Check whether it needs a separate network-debugging option or wireless pairing. |
| **ADB or a DLL is missing** | Extract the entire ZIP again. Keep the `adb` folder beside the EXE. Create a desktop shortcut instead of moving just the EXE. |
| **Action buttons are greyed out** | Connect, then tick a checkbox. Enabled apps can be disabled; disabled apps can be re-enabled. |
| **A change failed** | Click **Refresh apps** to check the result. The program stops at the first failure; earlier successful changes remain. |

<details>
<summary><strong>My TV uses Wireless debugging with a pairing code</strong></summary>

1. On the TV, open **Wireless debugging → Pair using pairing code**.
2. In the program, click **Pair with code…**.
3. Enter the pairing address and port shown on the TV, then its six-digit code.
4. After pairing, click **Discover TVs** again, select the TV and click **Connect**.

Pairing and connection ports can differ. For a manual connection, use the address and port on the TV's main Wireless debugging screen. [Google's wireless debugging guidance](https://developer.android.com/tools/adb#connect-to-a-device-over-wi-fi) explains the pairing process.

</details>

<details>
<summary><strong>I want to enter the TV address manually</strong></summary>

Find the TV's **IP address** in its network settings. Enter it in **TV address** and click **Connect**. If the TV shows a debugging port, include it after a colon, for example `192.168.1.50:5555`.

</details>

<details>
<summary><strong>Windows shows an unknown-publisher warning</strong></summary>

This is an unsigned Windows x64 preview build. Only run a copy from a source you trust.

</details>

## Licences

The program's licence and included third-party notices are in the `licenses` folder and `adb/NOTICE.txt`.
