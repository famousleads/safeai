# SafeAI quick start

From nothing to your first devices read. Plan about 30 minutes; most of it is creating a read-only account on your devices.

## 1. Before you start

- One Linux server: Ubuntu 22.04 or 24.04, or RHEL 9; 2 CPUs, 4 GB of memory, 20 GB of free disk.
- The server can reach your devices' management addresses over SSH (TCP 22).
- Your browser can reach the server on TCP 443.

## 2. Install (about a minute)

```
sha256sum safeai-observe-2.9.85.tar      # must match the value on the release page
tar -xf safeai-observe-2.9.85.tar && cd safeai-observe-2.9.85
sudo ./install.sh --expect-fingerprint fb51cd77f84753f29bfde10f6796f07a
```

Write down the two things it prints: the **console address** and the **setup code**.
(Lost the code? `sudo safeaictl setup-code` shows it again.)

## 3. Create a read-only account on your devices

One username that can display the configuration and change nothing. Copy-and-paste settings for each vendor are in the bundle
under `deploy/accounts/`. This is the step that takes the time.

## 4. First sign-in

Open the console address in a browser. The certificate is self-signed until you install your own, so the browser warns once.
Enter the setup code and create the first administrator. The setup pages then ask for:

1. Your organization's name.
2. The read-only account from step 3.
3. Your management ranges (for example `10.20.0.0/24`), or a list of devices. SafeAI scans only the private ranges you list
   and adds every device the read-only account can log in to.

## 5. Look at what it found

- **Devices**: each device, what every configuration line means, and the problems SafeAI's checks found.
- **Home**: what you have, what is wrong, and what to do next.
- Press **Accept current as known-good** on a device when its first read is right. Later changes are compared with it.

## 6. Next

- Send device logs to SafeAI (INSTALL.md, section 5) so changes are noticed within seconds.
- Connect your monitoring so an alert opens an incident by itself (USER_GUIDE.md).
- Prefer no setup pages at all? Fill in one file and SafeAI sets itself up: `deploy/README.md`.

Stuck? hello@safecadence.com, or TROUBLESHOOTING.md in the bundle.
