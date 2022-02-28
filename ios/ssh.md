# How to SSH/SFTP into iOS Devices

## Prerequisites

- A jailbroken iOS Device
- A functional PC that's connected to the same WiFi network as your device.
  - This does not apply if you're connecting over USB.
- **OpenSSH installed on your device.**
  - `openssh-server` on Procursus and `openssh` on Elucubratus 

<h2 align=center> How to SSH </h2>

## Windows

<h3 align=center> Using cmd (Command Prompt) </h3>

> Note: This section only applies if you're using the Windows 10 Spring update or newer.


#### Over Wi-Fi

> Locate your devices' (local) IP address in settings by tapping the "i" icon beside the connected network.

1. Launch Command Prompt (cmd)
2. Type in `ssh root@your.ip.here` and press enter.
3. You will be asked for a password. The password will be invisible when entered. Type `alpine` and press enter.

The output should look similar to this:
![ssh-cli](assets/sshclioutput.png)

#### USB

> *Before continuing, you must install iTunes from Apple's website. (not the microsoft store) or else you will run into errors.*

1. Download the latest Windows release of libimobiledevice from [here.](https://github.com/libimobiledevice-win32/imobiledevice-net/releases/)
2. Extract the zip
3. Launch Command Prompt (cmd)
4. Drag usbmuxd.exe to it. Press return.
5. Open a second command prompt window and drag Drag iproxy.exe to it. Type `2222 22` after it.`iproxy.exe 2222 22`
6. The output will should like this: ![iproxy in terminal](assets/iproxied.png)
7. Open a third command prompt window and type `ssh root@localhost -p 2222`
8. You will be asked for a password. The password will be invisible when entered. Type `alpine` and press enter.

### macOS

#### Wi-Fi

> Instructions are the same as recent Windows versions. Launch the Terminal app and continue from step 2.

#### USB

1. Launch the Terminal app.
2. Install Homebrew using this command: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`. Press return after pasting it.
3. Be patient as Homebrew installs. You may be asked for your password during the process.
4. Once it's finished, you will be dropped back to a prompt with your username.
5. run `brew install libimobiledevice`
6. Connect your iOS device using a cable.
7. Open a new terminal window using Command+N
8. In the new window, type: `iproxy 2222 22` and press return. The output should look like this: ![iproxy in terminal](assets/iproxied.png)
9. Go back to the old terminal window and type `ssh root@localhost -p 2222`
10. You will be asked for a password. The password will be invisible when entered. Type `alpine` and press enter.

### Linux

<h2 align=center> How to SFTP </h2>
