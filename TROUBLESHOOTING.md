# Troubleshooting Notes

This file records the issues reported during the WK1-PM1 lab. Only commands visible in the supplied terminal screenshot are listed; the exact steps used to resolve every issue were not provided.

## DNS and network connectivity

DNS and connectivity failures occurred during setup. The later Kali terminal screenshot shows successful replies to `google.com` (three packets received, zero packet loss), so connectivity was working at the time of that capture.

The screenshot shows these commands:

```bash
ip a | grep "inet 10"
ping -c 3 google.com
ls /mnt/hgfs/Downloads | head -5
```

The Windows network screenshot shows the host Wi-Fi address as `192.168.1.24`, the VMware VMnet8 adapter as `10.0.0.1`, and the VMware NAT subnet as `10.0.0.0/24`. In VMware NAT settings, the gateway is shown as `10.0.0.254`. The Kali address provided for the lab is `10.0.0.2/24`.

## VMware shared-folder behavior

The Windows Downloads folder was shared with the Kali VM and accessed under `/mnt/hgfs`. Copy/paste was enabled and worked. Drag-and-drop did not work in this session.

The command shown for listing a few shared-folder entries is:

```bash
ls /mnt/hgfs/Downloads | head -5
```

## Snapshot disk-space error

A disk-space error occurred while taking a snapshot. A clean baseline snapshot was subsequently taken, as reported for the completed setup. The provided notes do not specify the exact remediation steps, so none are inferred here.

## Related documentation

See [README.md](README.md) for the lab configuration and setup overview.
