# informant: pacman hook and cli for reading news feed

The AUR package `informant` will:

- provide command-line reader of important news from archlinux.org:
  ```
  # informant check
  There are 10 unread news items! Use informant to read them.
  ```
  and

  ```
  # informant read
  hplip 3.20.3-2 update requires manual intervention
  Thu, 19 Mar 2020 06:53:30 +0000

  The hplip package prior to version 3.20.3-2 was missing the compiled python modules.
  This has been fixed in 3.20.3-2, so the upgrade will need to overwrite the untracked
  pyc files that were created. If you get errors such as these

    
    
      hplip: /usr/share/hplip/base/__pycache__/__init__.cpython-38.pyc exists in filesystem
      hplip: /usr/share/hplip/base/__pycache__/avahi.cpython-38.pyc exists in filesystem
      hplip: /usr/share/hplip/base/__pycache__/codes.cpython-38.pyc exists in filesystem
      ...many more...
    

  when updating, use

    
    
    pacman -Suy --overwrite /usr/share/hplip/\*
    

  to perform the upgrade.


  Read next item? (Y/n): 
  ```
  and

  ```
  # informant list 
    0: zn_poly 0.9.2-2 update requires manual intervention                                                                                                                                                                                         Tue, 14 Apr 2020 16:30:30 +0000
    1: nss>=3.51.1-1 and lib32-nss>=3.51.1-1 updates require manual intervention                                                                                                                                                                   Mon, 13 Apr 2020 00:35:58 +0000
    2: hplip 3.20.3-2 update requires manual intervention                                                                                                                                                                                          Thu, 19 Mar 2020 06:53:30 +0000
    3: firewalld>=0.8.1-2 update requires manual intervention                                                                                                                                                                                      Sun, 01 Mar 2020 16:36:48 +0000
    4: The Future of the Arch Linux Project Leader                                                                                                                                                                                                 Mon, 24 Feb 2020 15:56:28 +0000
    5: Planet Arch Linux migration                                                                                                                                                                                                                 Sat, 22 Feb 2020 22:43:00 +0000
    6: sshd needs restarting after upgrading to openssh-8.2p1                                                                                                                                                                                      Mon, 17 Feb 2020 01:35:04 +0000
    7: rsync compatibility                                                                                                                                                                                                                         Wed, 15 Jan 2020 20:14:43 +0000
    8: Now using Zstandard instead of xz for package compression                                                                                                                                                                                   Sat, 04 Jan 2020 20:35:55 +0000
    9: Xorg cleanup requires manual intervention                                                                                                                                                                                                   Fri, 20 Dec 2019 13:37:40 +0000
  ```
- `pacman` hook to check while upgrade if there is something new

https://github.com/bradford-smith94/informant