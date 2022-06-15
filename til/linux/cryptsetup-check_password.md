# HOWTO: Check password

```
# cryptsetup open --type luks --test-passphrase /dev/nvme0n1p2
```
It will ask for password:

```
# cryptsetup open --type luks --test-passphrase /dev/nvme0n1p2
Enter passphrase for /dev/nvme0n1p2: 
No key available with this passphrase.
```