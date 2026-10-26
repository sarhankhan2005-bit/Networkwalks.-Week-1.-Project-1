# WK1-PM1: Cybersecurity Lab Setup

Week 1 lab setup for the NetworkWalks Cybersecurity Internship. The lab uses Kali Linux as the attacker VM in VMware Workstation, connected to a NAT network.

> VMware Workstation was used instead of VirtualBox, which the task suggested.

## Lab overview

| Item | Configuration / status |
|---|---|
| Attacker VM | Kali Linux 2026.1, VMware Workstation |
| Network | NAT, `10.0.0.0/24` |
| Kali address | `10.0.0.2/24` (static) |
| NAT gateway and DNS | `10.0.0.254`; secondary DNS `8.8.8.8` |
| Host VMnet8 adapter | `10.0.0.1` |
| Clipboard | Copy/paste enabled |
| Drag and drop | Did not work in this session |
| Shared folder | Windows Downloads, mounted at `/mnt/hgfs` |
| Baseline | Clean snapshot taken |

See [TROUBLESHOOTING.md](TROUBLESHOOTING.md) for reported DNS/connectivity issues, shared-folder behavior, and the snapshot disk-space error.

## Setup notes

1. **Configure VMware networking.** Set VMnet8 to NAT on `10.0.0.0/24`, with gateway `10.0.0.254`. The host's VMnet8 adapter appears as `10.0.0.1` on Windows.
2. **Set up Kali networking.** Kali uses static address `10.0.0.2/24`, with gateway and DNS `10.0.0.254` and secondary DNS `8.8.8.8`.
3. **Check connectivity.** The terminal screenshot shows these commands and successful ping replies:

   ```bash
   ip a | grep "inet 10"
   ping -c 3 google.com
   ```

4. **Configure sharing and guest isolation.** Enable copy/paste in VM settings and share the Windows Downloads folder with Kali. Copy/paste worked; drag-and-drop did not. The shared folder was accessed at `/mnt/hgfs`.
5. **Take a clean baseline snapshot** after setup.

## Screenshot evidence

Screenshot evidence is pending addition to the repository. The planned images are the VMware network editor, Windows `ipconfig`, Kali terminal, VM settings, and snapshot manager. Images will be embedded here after they are uploaded to `screenshots/`.

## Troubleshooting

See [TROUBLESHOOTING.md](TROUBLESHOOTING.md) for the problems reported and commands visible in the terminal screenshot.
