# SafeAI

**Find what broke your network. Fix it safely.**

SafeAI runs on your own server, inside your network. It reads your routers, switches and firewalls, keeps every configuration
change, and when something breaks it shows which change the evidence points to. It only reads. Nothing changes on a device unless
your own people approve it, and the person who asks can't be the one who approves.

- **Know what changed.** Every change on every device: when, the exact lines, and whether anyone planned it.
- **Find the cause.** Each possible cause is tested against the live network and marked proven, disproven or unknown.
- **Fix with a second pair of eyes.** SafeAI prepares the undo; one person proposes it, another approves it, and SafeAI checks the result.
- **Stays with you.** No internet connection is needed, at install or afterwards. Your data never leaves your network.

> **Where it stands.** SafeAI has been tested on SafeCadence's own 61-device lab network and against simulated equipment.
> It has not yet run at a customer. Every number below is a lab result.

Try it without installing anything: the [live demo](https://safeai.safecadence.com) needs no sign-up.

## Install

You need one Linux server (Ubuntu 22.04 or 24.04, or RHEL 9) with 2 CPUs, 4 GB of memory and 20 GB of disk, on a network that
can reach your devices over SSH.

Download SafeAI — no sign-up — from [safecadence.com/download](https://safecadence.com/download/). Then:

```
sha256sum safeai-observe-2.9.85.1.tar    # must equal b60537ae0ca720188d6148e276c32e672b36a140d3570169f7d13d009897feab
tar -xf safeai-observe-2.9.85.1.tar && cd safeai-observe-2.9.85.1
sudo ./install.sh --expect-fingerprint fb51cd77f84753f29bfde10f6796f07a
```

The installer checks the server, verifies the bundle's signature, installs Docker from the bundle if the server has none, starts
SafeAI, and prints the console address and a one-time setup code. On a clean Ubuntu 24.04 server with 2 CPUs and 4 GB of memory
it took 17 seconds with no internet connection (our own test, 23 November 2026).

Next: [QUICKSTART.md](QUICKSTART.md), one page from install to your first devices.

## What it reads

| | Platforms |
|---|---|
| Read on our lab | Cisco IOS and IOS-XE, FortiOS (FortiGate), FRRouting, Nokia SR Linux. pfSense and OPNsense have been read on the lab too and are still marked preview |
| Preview: built from the vendor's documentation, not yet checked on a real device | Cisco NX-OS, IOS XR, ASA and Firepower; Arista EOS; Juniper Junos; Palo Alto PAN-OS; SonicWall; Sophos; WatchGuard; Check Point; HPE Aruba CX; Dell OS10; Ruckus ICX |

A line SafeAI doesn't know is shown as "not in the catalog". It is never guessed.

## Licence

SafeAI is free to evaluate: every feature, no limit on devices, for 90 days from its first start, and 45 more when you ask for
them. After that it keeps reading every device and showing every change at reduced capacity until a licence is added. Nothing
is deleted and nothing stops.

By installing SafeAI you accept the [evaluation agreement](https://safecadence.com/account/agreement).

SafeAI is not open source. This repository holds the release notes and the guides.

## Help

- Questions, or something SafeAI got wrong about your network: hello@safecadence.com. That is exactly what we want to hear.
- The full guides (installation, administration, design, security review) are inside the bundle and at
  [safecadence.com/safeai/docs](https://safecadence.com/safeai/docs/).
- To report a security problem, see SUPPORT.md in the bundle.

SafeCadence LLC, Tampa, Florida.
