# Cybersecurity Notes

## Workflow THM w/ OpenVPN

- Start the VM to be attacked from Task Section (green button).
- While the target VM instantiates start OpenVPN on host machine.
  - `sudo openvpn ~/Downloads/specmenu0.opvn`
  - *Personal NOTE:* Had an issue with launchinfg the VPN on my local Kali VM. It said "Options error: In [CMD-LINE]:1: Error opening configuration file... blah blah filename.ovpn" I updated and upgraded and it seemed to fix the problem.

- Create new tab in Terminal `ctrl-shift-T` so we don't stop the VPN.
- Check connection (tun0) and get my IP
  - `$ ifconfig`
    - Alternate to get my IP
      - `ip addr`
- Get target VM IP, credentials
  - On website

## SSH

## Copy files to target (SCP)

`scp` Secure CoPy copies/creates a file at the destination (local or remote) using SSH.
- Example `scp file.conf shmuck@8.8.4.4/home/Downloads/sheet1.xlsx`


## Enumeration

List of basic steps used in enumeration. Use own judgment. Be flexable.

### Step 1. Scan Ports
  - `nmap -sS -A -T4 -p- <target IP> -oN <outputfilename.txt>`
    - `-sS` Can be omitted. Default behavior: Scan Technique `-sS` TCP SYN scan [Man page](https://nmap.org/book/synscan.html)
    - Misc `-A` Detect OS and Versions
    - Timing and Performanxe `-T<0-5>` Timing template, higher is faster.
    - Port Specfication `-p- <target IP>`
    - Output `-oN <outputfilename.txt>`
