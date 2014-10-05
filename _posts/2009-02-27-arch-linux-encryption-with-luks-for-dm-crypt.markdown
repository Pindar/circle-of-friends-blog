---
layout: post
status: publish
published: true
title: 'Arch Linux: LVM on top of an encrypted partition'
author: fensterplatz
author_login: fensterplatz
author_url: http://www.pindarsign.de/webblog
excerpt: "<strong>Introduction</strong>\r\nHere, I'm describing how to set up
  full disk encryption using dm-crypt combined with logical volumes with Arch Linux.
  Most people use encryption to avoid physical access to their data by people who
  aren't explicitly allowed. It makes quite much sense to set up encryption at a notebook
  in case it's getting lost or stolen - the finder/thief has the hardware but
  not your data! For this scenario, it is not necessary to have all copies of that
  data encrypted because you usually keep the copies on a safe place (i.e. if you
  are using a home server for backups). In the other case, if you explicitly don't
  want anybody to access your data at any time at any place you have to make sure
  that all copies of the data are either erased or stored encrypted. Also don't forget:
  A running system which uses full disk encryption is still vulnerable to network/Internet
  attacks!\r\n\r\nThere are two ways of setting up an encrypted disk using LVM:\r\n1.
  Create the LVM and encrypt every volume separately\r\n2. Set up LVM on top of an
  encrypted partition\r\n"
wordpress_id: 767
wordpress_url: http://www.pindarsign.de/webblog/?p=767
redirect_from: "/?p=767"
date: '2009-02-27 20:41:16 +0100'
date_gmt: '2009-02-27 19:41:16 +0100'
categories:
- Allgemein
- Technik
- Linux
tags:
- linux
- arch linux
- lvm
- encryption
- luks
- arch
- dm-crypt
comments:
- id: 39769
  author: Pierre
  author_url: ''
  date: '2009-03-19 12:48:18 +0100'
  date_gmt: '2009-03-19 11:48:18 +0100'
  content: "Mate...I can not thank you enough for sharing this. I have been battling
    with this for three weeks now, and now I can see where I got it wrong.\r\nThank
    you."
- id: 39770
  author: Lathqe
  author_url: ''
  date: '2009-03-26 20:23:24 +0100'
  date_gmt: '2009-03-26 19:23:24 +0100'
  content: "Thanks for this guide!  I can't seem to boot, though.  I'm getting this
    error message: \r\nError 14: Filesystem compatibility error, cannot read whole
    file.\r\nAny ideas?"
- id: 39771
  author: fensterplatz
  author_url: http://
  date: '2009-03-28 14:42:19 +0100'
  date_gmt: '2009-03-28 13:42:19 +0100'
  content: "Hi Lathqe,\r\n\r\nwhat kind filesystem did you choose for boot, home and
    swap partitions (e.g. ext3)? Usually this error occurs if a file is bigger than
    the filesystem. Maybe you chose a wrong size for the boot partition (should be
    at least 150 MegaByte)."
- id: 39778
  author: soldiar
  author_url: ''
  date: '2009-03-31 14:27:19 +0200'
  date_gmt: '2009-03-31 12:27:19 +0200'
  content: "Hello,\r\n\r\nthanks for this tutorial. It's much more easy to setup this
    way. Great.\r\n\r\nI'm starting to use arch linux (I'm an ex Debian/Ubuntu
    user) and this interests me very much.\r\n\r\nI'm having problems to boot. The
    system boots, asks for the passphrase and then gives an error: \r\n\r\nEnter LUKS
    passphrase:\r\npadlock: VIA PadLock not detected.\r\nEnter LUKS passphrase:\r\n\r\nI'm
    using the benbi cipher as is explained here. Do I need to add a module or something?
    Don't we need to edit /etc/crypttab? I did encrypt the partition and then
    create the lvm group and volumes before starting /arch/setup.\r\n\r\nCan
    you say why is this happening? Thanks in advance."
- id: 39780
  author: soldiar
  author_url: ''
  date: '2009-03-31 15:54:12 +0200'
  date_gmt: '2009-03-31 13:54:12 +0200'
  content: "err... I was trying to install to an extended partition (/dev/sda6).\r\n\r\nI
    tried this again in a vbox vm using an entire disk and it worked like a charm
    (the padlock message appears after typing the passphrase but the kernel boots
    anyway).\r\n\r\nI'm going to try again using only primary partitions on my disk.\r\n\r\nThank
    you for this."
- id: 39782
  author: fensterplatz
  author_url: http://
  date: '2009-03-31 16:25:06 +0200'
  date_gmt: '2009-03-31 14:25:06 +0200'
  content: "> Don&acirc;&euro;&trade;t we need to edit /etc/crypttab?\r\n\r\ncrypttab
    is there to map keys and partitions. So if you created a key randomly and stored
    it to a file (like in arch-wiki) you have to map the partiton (eg. /dev/sda1)
    to the file containing the key. We don't need crypttab for the reason that we
    don't store a key to a file. There is to say, that with our method, the passphrase
    should be long (>20 characters) and well chosen.\r\n\r\nI get the padlock message,
    too. It's just a note that padlock support couldn't be enabled (I don't think
    you have a VIA processor). For more information: http://www.via.com.tw/en/initiatives/padlock/hardware.jsp"
- id: 39784
  author: lathqe
  author_url: ''
  date: '2009-03-31 21:50:45 +0200'
  date_gmt: '2009-03-31 19:50:45 +0200'
  content: "Sorry to delay in responding.\r\nMy initial problem was one of not pointing
    it to the right HD. (read: \"noob\")  Ok, so I pointed GRUB to sda, but then I
    ran into more problems, further down the process.\r\n\r\nSo to back up and take
    it from the top:\r\nI'm trying to do this on a SD card on my eee701 (I have my
    own slimmed-down ubuntu with LXDE on the internal, and I'm wanting to start to
    move toward Arch.  I'm in a situation that demands full encryption on everything,
    so my OS choices are a bit more limited.)\r\n\r\nSo in the initial install I told
    it to install to sdb (because that's what the SD was at the time), but now it
    thinks it's sda because I booted to it.  \r\n\r\nI did the \"edit\" option from
    within grub and changed it to see hd0 and sda, and then it got past the first
    error I mentioned...\r\n\r\nNow, however, it gets hung up because it \"Failed
    to parse block device name for '/dev/mapper/vgroup-root' unknown\"
    etc. etc.  Somehow it's not allowing me to unlock that (\"enter my passphrase\").
    \ \r\n\r\nThanks for your help"
- id: 39785
  author: lathqe
  author_url: ''
  date: '2009-03-31 21:54:18 +0200'
  date_gmt: '2009-03-31 19:54:18 +0200'
  content: "and of course I failed to answer your primary question. \r\nit's just
    one boot partition of 150 or 200meg (don't remember) and the rest is used for
    the encrypted chunk - all just as / - and I did this a couple times, so I
    don't remember if I ended up with ext2 or ext4 (I tried it both ways).  No swap"
- id: 39786
  author: fensterplatz
  author_url: http://
  date: '2009-04-01 23:36:58 +0200'
  date_gmt: '2009-04-01 21:36:58 +0200'
  content: "ERROR: Failed to parse block device name for '/dev/mapper/vgroup-root'
    \r\nunknown \r\nERROR: root fs cannot be detected...\r\n\r\nThis indicates that
    you forgot to add \"cryptdevice=/dev/sda2:vgroup\" between \"root=&acirc;&euro;&brvbar;\"
    and \"ro\" in /boot/grub/menu.lst\r\n\r\nOf course you have to adjust
    the device and volume group.\r\nThis is also described in Step 3 of the tutorial."
- id: 39788
  author: soldiar
  author_url: ''
  date: '2009-04-02 05:27:53 +0200'
  date_gmt: '2009-04-02 03:27:53 +0200'
  content: "Just to say that I was wrong about extended partitions. You can use extended
    partitions (/dev/sda5 and beyon) with this tutorial, I've just confirmed
    it.\r\n\r\nMy original problem was that I'm using a non-us keyboard and somehow,
    on boot, when the passphrase is asked, the keyboard isn't set to non-us yet. So
    beware with non-alphabatical keys in non-yankees keyboards when you are sure about
    the passphrase (doesn't happen on windows and debian, both encrypted, installed
    on the same computer, so it's an arch problem/misconfiguration, still have
    to verify).\r\n\r\nSo, great tutorial, fensterplatzm, thanks. It allows me to
    have several encrypted OS and several partitions on the same PC."
- id: 39791
  author: jean

  author_url: ''
  date: '2009-05-16 02:51:05 +0200'
  date_gmt: '2009-05-16 00:51:05 +0200'
  content: "As regards non-us keyboards, you just have to add the \"keymap\" hook
    before the \"encrypt\" one.\r\nI use a dvorak keyboard and it worked fine.\r\nAlso,
    set the right keymap in rc.conf"
- id: 39792
  author: fensterplatz
  author_url: http://
  date: '2009-06-06 19:28:08 +0200'
  date_gmt: '2009-06-06 17:28:08 +0200'
  content: Thanks Jean! I added the KEYMAP part as most people don't use standard
    us-layout.
- id: 39800
  author: Name
  author_url: ''
  date: '2009-07-12 02:56:59 +0200'
  date_gmt: '2009-07-12 00:56:59 +0200'
  content: "If you are using an USB keyboard, you will need to add MODULES to /etc/mkinitcpio.conf
    and regenerate your initcpio to be able to enter the passphrase:\r\n\r\nMODULES=\"usbcore
    uhci_hcd ehci_hcd hid usbhid\"\r\n\r\nYou might be able to trim that list but
    once working I stopped testing."
- id: 39801
  author: Dieter Plaetinck
  author_url: http://dieter.plaetinck.be
  date: '2009-08-27 18:26:29 +0200'
  date_gmt: '2009-08-27 16:26:29 +0200'
  content: "Note that all of this is not needed anymore with the new installer.  AIF
    supports lvm and dm_crypt out of the box.\r\nIt could be that you still need to
    update crypttab yourself but that should be it.   If you find anything that doesn't
    work on can be improved with aif, just report a bug.\r\n\r\nDieter"
- id: 39802
  author: Anonymous
  author_url: ''
  date: '2009-09-17 18:05:13 +0200'
  date_gmt: '2009-09-17 16:05:13 +0200'
  content: "hi, I liked your article a lot\r\nbut I had a problem with your dd comand,
    it was slow as hell\r\nI tried a if=/dev/urandom and with that it was
    a lot quicker to fill the disk with randomness\r\nyou should compare the output
    speed of 'cat /edv/random' versus the speed of 'cat /dev/urandom',
    the later spit garbage at a faster rate"
- id: 39803
  author: fensterplatz
  author_url: http://www.pindarsign.de/webblog
  date: '2009-09-18 00:01:09 +0200'
  date_gmt: '2009-09-17 22:01:09 +0200'
  content: "Hi\r\n\r\n>hi, I liked your article a lot\r\n\r\nthanks!\r\n\r\n>but I
    had a problem with your dd comand, it was slow as hell\r\n>I tried a if=/dev/urandom
    and with that it was a lot quicker \r\n>to fill the disk with randomness\r\n>you
    should compare the output speed of &acirc;&euro;&tilde;cat /edv/random&acirc;&euro;&trade;
    \r\n>versus the speed of &acirc;&euro;&tilde;cat /dev/urandom&acirc;&euro;&trade;,
    the later spit \r\n>garbage at a faster rate\r\n\r\nI've always referred to the
    /dev/urandom command, so I guess this is just a misunderstanding on your
    side.\r\n\r\nThanks for your comment anyway!"
- id: 39804
  author: Anonymous
  author_url: ''
  date: '2009-09-18 17:48:40 +0200'
  date_gmt: '2009-09-18 15:48:40 +0200'
  content: "you are right it's my mistake, I guess that happens when you read too
    fast :P\r\non a side note, using /dev/urandom it took me like 20 hours
    for my 320gb on my laptop, at the pace /dev/random was taking it would
    have taken over a thousand days to fill the same disk!"
- id: 39806
  author: paul
  author_url: ''
  date: '2009-10-12 10:40:18 +0200'
  date_gmt: '2009-10-12 08:40:18 +0200'
  content: "What an excellent guide! I printed it out and used this a couple of days
    ago to reconfigure my laptop and it went like a dream.\r\n\r\nthanks"
- id: 39807
  author: solsTiCe
  author_url: ''
  date: '2009-12-14 00:52:38 +0100'
  date_gmt: '2009-12-13 23:52:38 +0100'
  content: "i would suggest using frandom for filling partition before encryption.
    it is faster then /dev/urandom\r\n\r\nlook at frandom at AUR.\r\nonce
    installed, run /etc/rc.d/frandom start\r\nand then use /dev/frandom
    to dd your partition"
- id: 39808
  author: JD
  author_url: ''
  date: '2010-01-28 01:05:49 +0100'
  date_gmt: '2010-01-28 00:05:49 +0100'
  content: "I'm a bit confused.\r\nA separate boot partition has been created (sda1)
    but you say to install the boot loader to sda (the MBR right?) is this a typo.\r\nI
    don't understand the point of an /boot partition if GRUB is being installed
    to sda.\r\n\r\nAny help would be appreciated as I installed GRUB to sda1 (like
    I normally do when using encrypted *partitions* [I'm new to LVM]) and I can't
    boot to grub (black blinking dot appears) and so I have to use the GRUB on a USB
    to boot my harddrive."
- id: 39810
  author: fensterplatz
  author_url: http://www.pindarsign.de/webblog
  date: '2010-01-31 14:16:14 +0100'
  date_gmt: '2010-01-31 13:16:14 +0100'
  content: "Hi JD,\r\n\r\nThis is a mistake that took me some while as well. Installing
    Grub on a disk means to which disk's MBR the link to the bootloader is written.
    The files needed for boot are automatically written to the partition which is
    currently mounted as /boot (the mounting is done earlier). By \"installing\"
    Grub to /dev/sda1, the MBR of /dev/sda is not changed and the
    system won't boot Grub.\r\n\r\nHope that this explanation helps.\r\n\r\nfensterplatz"
- id: 39811
  author: johannes
  author_url: http://www.i-tiger.de
  date: '2010-03-26 10:13:00 +0100'
  date_gmt: '2010-03-26 09:13:00 +0100'
  content: "Hi, I tried to follow the installer with plain dm-crypt volumes without
    LVM. Everything works fine, but I don't know how to modify the grub: menu.lst
    \r\nI have 2 hard drives, \r\n/dev/sda1 = /boot (no dm-crypt)\r\n/dev/sda5
    = /    (dm-crypt) label: sda5crypt\r\n/dev/sdb1 = /home  (dm-crypt)
    label: sdb1crypt\r\n\r\nI tried several options in the menu.lst, but I didn't
    succeed. Any proposals? \r\n\r\nThanks."
- id: 39812
  author: fensterplatz
  author_url: http://www.pindarsign.de/webblog
  date: '2010-03-26 12:54:12 +0100'
  date_gmt: '2010-03-26 11:54:12 +0100'
  content: 'have u tried something like: "root=/dev/sda5 cryptdevice=/dev/sda5"
    or "root=/dev/sda5 cryptdevice=/dev/sda5:"?'
- id: 39813
  author: johannes
  author_url: http://www.i-tiger.de
  date: '2010-03-26 16:19:36 +0100'
  date_gmt: '2010-03-26 15:19:36 +0100'
  content: "Hi, yes I tried both versions, didn't work. I looked at the /etc/crypttab
    and the /etc/fstab and the installer didn't touch these files either.
    I didn't find a file (like in debian) /etc/default/cryptdisk \r\nI
    created the files, but I still can't get into my system, it won't boot.\r\n\r\nThanks
    for your help"
- id: 39819
  author: JD
  author_url: ''
  date: '2010-05-25 18:05:51 +0200'
  date_gmt: '2010-05-25 16:05:51 +0200'
  content: "I'm new to LVM, but how would I go about splitting a hard drive as follows:\r\nI
    would like a partition for Arch Linux, which is split up into 5 volumes (/,/var,/home,swap,
    and /tmp) which is encrypted with one key.\r\n\r\nI would then like another
    partition for my data, which is split up into 4 volumes (music, vidoes, pictures,
    documents) which is encrypted with a different key.\r\n\r\nAnd, another 2 paritions,
    for the installation of backtrack and debian each of which are encrypted with
    a different key for each.\r\n\r\nSo in essence, I have 4 partitions (well 5 including
    my boot partition), and each of these partitions are encrypted with different
    keys, and split up into volumes.\r\n\r\nHow would I go about implementing this?\r\nWould
    I need to create multiple physical volumes (pvArch, pvData, pvBacktrack, pvDebian),
    or just one phsyical volume with multiple volume groups.\r\nThanks."
- id: 39820
  author: vio
  author_url: ''
  date: '2010-06-16 22:30:30 +0200'
  date_gmt: '2010-06-16 20:30:30 +0200'
  content: "Well, nice tut, but....\r\n\r\nUsing the following setup i have some problem
    booting into the system:\r\n\r\nsda1 > /boot\r\nsda2 > dm_crypt (sda2crypt)\r\nsdb1
    > dm_crypt (sdb1crypt)\r\n\r\nI have a lvm volume group using both crypted partitions
    as physical volumes, which contains several logical volumes - one of those is
    the root partition.\r\n\r\nHow can i tell the Kernel at boot-time to decrypt BOTH
    luks partitions (by keyfile) in order for lvm to be able to work?\r\n\r\nCurrently
    just one of the crypted partitions is opened via keyfile/passphrase - then
    the system drops into a recovery shell: if i decrypt the second partition manually
    and do a pvscan and vgchange -ay , then exiting the recovery shell the system
    continues booting as expected.\r\n\r\nthx for your help in advance ;)"
- id: 39821
  author: vio
  author_url: ''
  date: '2010-06-16 23:52:54 +0200'
  date_gmt: '2010-06-16 21:52:54 +0200'
  content: 'hmmm... seems i have found the reason: The ''encrypt'' hook-script is
    not capable handling multiple crypted partition at once - I will rework it myself
    (and maybe submit a patch: using volume groups consisting of several PVs HAS to
    be possible at all...)'
- id: 39822
  author: Mervyn
  author_url: ''
  date: '2010-06-22 11:35:39 +0200'
  date_gmt: '2010-06-22 09:35:39 +0200'
  content: "Thanks for your guide, really nice. But I've discovered a point which
    differs from the howto on wiki.archlinux.org(http://wiki.archlinux.org/index.php/LUKS).\r\n\r\nThe
    Arch guide said, \"...In /etc/rc.conf set USELVM=\"yes\" In /etc/mkinitcpio.conf
    add lvm2 before encrypt in the HOOKS variable if you set up LVM on top of the
    encrypted partition.\" \r\n\r\nThat's where I got confused. It doesn't make sense.
    Actually, I'm new to LVM and dm-crypt so I did as what the official guide on their
    release iso said--encrypt before lvm2, which is generated by the aif program.
    However I get the error saying \"no key available with this passphrase\" when
    booting the new installation. I wonder if it is really needed to add lvm2 before
    encrypt or the problem was just caused by wrong settings. Anyway, I'll keep trying
    to find it out."
- id: 39826
  author: AE
  author_url: ''
  date: '2010-09-30 22:25:50 +0200'
  date_gmt: '2010-09-30 20:25:50 +0200'
  content: I'm thinking of doing this on my ppc machine. I'm guessing that I need
    to make additions to /etc/yaboot.conf (comparable to editing /boot/grub/menu.lst,
    I suppose). What do I need to put in there?
- id: 39832
  author: Kyle Reid
  author_url: http://computerotaku.com
  date: '2011-01-10 04:01:51 +0100'
  date_gmt: '2011-01-10 03:01:51 +0100'
  content: Thanks for this, after a day of setting up the encryption method off the
    arch wiki and breaking it repeatedly playing with mkinitcpio for early user land
    framebuffer support I found this in the discussion page. Clean straightforward
    and concise, thanks!
- id: 39834
  author: Der mit dem Tux tanzt
  author_url: ''
  date: '2011-02-15 22:08:58 +0100'
  date_gmt: '2011-02-15 21:08:58 +0100'
  content: "Thank you very much. Works perfectly. Should be on Arch wiki.\r\n\r\nKeep
    up the good work. :)"
- id: 39844
  author: Stella
  author_url: http://www.google.com/
  date: '2011-07-07 20:29:36 +0200'
  date_gmt: '2011-07-07 18:29:36 +0200'
  content: Was totally stuck until I read this, now back up and rnuinng.
- id: 39846
  author: Robbie
  author_url: http://www.bing.com/
  date: '2011-07-07 21:45:57 +0200'
  date_gmt: '2011-07-07 19:45:57 +0200'
  content: I relaly wish there were more articles like this on the web.
- id: 39850
  author: Marilu
  author_url: http://www.google.com/
  date: '2011-07-08 02:47:01 +0200'
  date_gmt: '2011-07-08 00:47:01 +0200'
  content: I sraeched a bunch of sites and this was the best.
- id: 39881
  author: Dotty
  author_url: http://www.bing.com/
  date: '2011-07-09 14:44:23 +0200'
  date_gmt: '2011-07-09 12:44:23 +0200'
  content: HHIS I should have thoguht of that!
- id: 39930
  author: ignotus
  author_url: ''
  date: '2011-09-23 05:26:49 +0200'
  date_gmt: '2011-09-23 05:26:49 +0200'
  content: "I've followed your directions to the letter, twice, both times with the
    same result. \r\n\r\nkernel /vmlinuz26 root=/dev/mapper/vgroup-root
    cryptdevice=/dev/sda6:vgroup ro\r\n\r\nError 15: File not found\r\n\r\nAnyone
    else have this problem?"
- id: 39932
  author: Duxon
  author_url: ''
  date: '2011-11-11 07:06:55 +0100'
  date_gmt: '2011-11-11 07:06:55 +0100'
  content: "Since kernel 3.1 we can optionally activate TRIM support for SSDs using
    dm-crypts parameter '--enable-discards'. Where do I have to put this command in
    order to open my device with TRIM using your guide?\r\n\r\nSee here: http://www.redhat.com/archives/dm-devel/2011-October/msg00134.html\r\n\r\nVery
    nice work btw, helped me a lot!"
- id: 39950
  author: T Buitenhuis
  author_url: ''
  date: '2011-12-09 14:42:49 +0100'
  date_gmt: '2011-12-09 14:42:49 +0100'
  content: "I ended up with this:\r\n\r\n(etc etc)\r\n:: Running Hook [udev]\r\nTriggering
    uevents... done\r\n:: Running Hook [encrypt]\r\nWaiting 10 seconds for device
    /dev/mapper/vgroup-root ...\r\n:: Running Hook [lvm2]\r\nActivating
    logical volumes...\r\n  No volume groups found\r\nWaiting 10 seconds for device
    /dev/mapper/vgroup-root ...\r\nERROR: Unable to determine major/minor
    number of root device '/dev/mapper/vgroup-root'.\r\nYou are being
    dropped to a recovery shell\r\n(etc etc)\r\n\r\nThe passphrase was never asked
    for.\r\n\r\nThe differences: I created swap before /, and I used aes-xts-plain64
    with cryptsetup. Neither should be a problem :/\r\n\r\nHelp?"
- id: 39952
  author: chris
  author_url: ''
  date: '2012-01-29 10:57:10 +0100'
  date_gmt: '2012-01-29 10:57:10 +0100'
  content: "badass. really simple, but you wouldn't have known it until you see it
    spelled out like you did here.\r\n\r\nI had the right idea, but the order of operations
    was tough because I knew that I wanted lvm on top of luks, but wasn't sure what
    the proper order of steps was.\r\n\r\nThanks a lot!"
- id: 39953
  author: Anon
  author_url: ''
  date: '2012-02-05 00:07:40 +0100'
  date_gmt: '2012-02-05 00:07:40 +0100'
  content: Thanks a ton for this guide you should put it in the arch wiki!!
- id: 39954
  author: Anon
  author_url: ''
  date: '2012-02-05 00:10:59 +0100'
  date_gmt: '2012-02-05 00:10:59 +0100'
  content: Awesome howto! Should for sure be added to the archlinux wiki.
- id: 39958
  author: Stephen Tanner
  author_url: http://StephenTanner.net
  date: '2012-08-22 13:49:26 +0200'
  date_gmt: '2012-08-22 13:49:26 +0200'
  content: "Just thought you might want to know, LRW has been mostly replaced by XTS
    due to security concerns.\r\n\r\nhttps://en.wikipedia.org/wiki/Disk_encryption_theory#Liskov.2C_Rivest.2C_and_Wagner_.28LRW.29\r\n\r\ncryptsetup
    -c aes-xts-plain -y -s 512 luksFormat /dev/sda2"
- id: 39959
  author: Stephen Tanner
  author_url: http://StephenTanner.net
  date: '2012-08-22 14:04:48 +0200'
  date_gmt: '2012-08-22 14:04:48 +0200'
  content: "**Correction** \r\ncryptsetup create -c aes-xts-plain -y -s 512 luksFormat
    /dev/sda2"
- id: 39960
  author: Stephen Tanner
  author_url: http://StephenTanner.net
  date: '2012-08-22 15:15:14 +0200'
  date_gmt: '2012-08-22 15:15:14 +0200'
  content: Actually, ignore previous two posts.
- id: 39963
  author: Chargeling
  author_url: ''
  date: '2012-11-06 18:59:53 +0100'
  date_gmt: '2012-11-06 18:59:53 +0100'
  content: "I'm running a similar setup and I'm a little dissatisfied by the reaction
    time. ls can take more than a second if the folder hasn't been accessed for a
    longer time. (ecryptfs felt a lot 'jumpier', I didn't really like the idea behind
    it though.) Is there anything I could do about that?\r\n\r\nOh, and as we have
    seen, /dev/urandom isn't necessarily as secure as /dev/random.
    It probably won't have any effect, though."
- id: 39964
  author: LVM on LUKS on Raid1 on Arch Linux
  author_url: http://found.devsite.pl/?p=20
  date: '2012-11-19 18:47:01 +0100'
  date_gmt: '2012-11-19 18:47:01 +0100'
  content: "[...] gleaned gratefully from other sources; principally the Arch Wiki
    entries on LUKS and LVM and this helpful blog post. This post (and the next) are
    notes to remind me how I got here and, in the follow-up, what I need [...]"
- id: 39977
  author: schtiehve
  author_url: ''
  date: '2013-07-03 21:27:51 +0200'
  date_gmt: '2013-07-03 21:27:51 +0200'
  content: 'Nice Howto like it much better than the wiki. Till Part 3: installation
    because they removed the Arch installer from the iso so sadly back to the wiki'
- id: 39978
  author: Amanda Person
  author_url: ''
  date: '2013-10-03 02:16:54 +0200'
  date_gmt: '2013-10-03 02:16:54 +0200'
  content: Thank for the guide, this area is a bit lacking on the Arch Wiki but it's
    getting better. I used to use the Fedora installer to set up all of the LVM and
    whatnot then quit/reboot and start the arch installer and continue from there
    (which was still complicated).
- id: 39979
  author: horny
  author_url: http://www.MHyzKpN7h4ERauvS72jUbdI0HeKxuZom.com
  date: '2014-01-10 15:48:08 +0100'
  date_gmt: '2014-01-10 15:48:08 +0100'
  content: CkR2Be http://www.MHyzKpN7h4ERauvS72jUbdI0HeKxuZom.com
- id: 39980
  author: Qczeepqz
  author_url: http://paydayzabc.co.uk/
  date: '2014-02-08 11:47:43 +0100'
  date_gmt: '2014-02-08 11:47:43 +0100'
  content: The bankers huddled to decide how it's allocated., <a href="http://paydayzabc.co.uk/"
    rel="nofollow">uk payday loan</a>,  :)),
- id: 39981
  author: matt
  author_url: http://www.QS3PE5ZGdxC9IoVKTAPT2DBYpPkMKqfz.com
  date: '2014-04-05 22:17:58 +0200'
  date_gmt: '2014-04-05 22:17:58 +0200'
  content: FQ3Alx http://www.QS3PE5ZGdxC9IoVKTAPT2DBYpPkMKqfz.com
- id: 39982
  author: barons 9s for sale
  author_url: http://www.pinterest.com/airjordan5laney/buy-authentic-jordan-9-barons-for-sale-cheap/
  date: '2014-04-26 19:51:09 +0200'
  date_gmt: '2014-04-26 19:51:09 +0200'
  content: "infancy. And, do I need to say, how sad your chances of getting promoted
    and getting salary raises\r\n[url=http://www.pinterest.com/airjordan5laney/buy-authentic-jordan-9-barons-for-sale-cheap/]barons
    9s for sale[/url]"
- id: 39984
  author: Cheap Nike Air Jordan 7 Retro Bordeaux Shoes

  author_url: http://www.nikeshoessneaker.com/nike-air-jordan-7-shoes/6451-nike-air-jordan-7-retro-bordeaux-shoes.html
  date: '2014-06-30 20:52:04 +0200'
  date_gmt: '2014-06-30 20:52:04 +0200'
  content: "<a href=\"http://www.nikeshoessneaker.com/cheap-womens-nike-air-rifts/6482-women-nike-air-rift-yellow-red-shoes.html\"
    rel=\"nofollow\">Women Nike Air Rift Yellow Red Shoes</a>\tArch Linux: LVM
    on top of an encrypted partition at  circle of friends | blog\t<a href=\"http://www.nikeshoessneaker.com/cheap-mens-nike-shox-tl/7306-nike-shox-tl1-white-red-shoes.html\"
    rel=\"nofollow\">Cheap Nike Shox TL1 White Red Shoes</a>"
- id: 39985
  author: Dolce&amp;Gabbana Bikini (6) south africa

  author_url: http://www.sexybikinioutlet.com/cheap-dolce-gabbana-bikini/663-dolcegabbana-bikini-6-south-africa.html
  date: '2014-07-01 02:28:06 +0200'
  date_gmt: '2014-07-01 02:28:06 +0200'
  content: "Arch Linux: LVM on top of an encrypted partition at  circle of friends
    | blog\t         <a href=\"http://www.sexybikinioutlet.com/cheap-polo-bikini/840-polo-bikini-38-2014.html\"
    rel=\"nofollow\">polo bikini (38) 2014</a> \t    Arch Linux: LVM on top of
    an encrypted partition at  circle of friends | blog"
---
<p><strong>Introduction</strong><br />
Here, I'm describing how to set up full disk encryption using dm-crypt combined with logical volumes with Arch Linux. Most people use encryption to avoid physical access to their data by people who aren't explicitly allowed. It makes quite much sense to set up encryption at a notebook in case it's getting lost or stolen - the finder/thief has the hardware but not your data! For this scenario, it is not necessary to have all copies of that data encrypted because you usually keep the copies on a safe place (i.e. if you are using a home server for backups). In the other case, if you explicitly don't want anybody to access your data at any time at any place you have to make sure that all copies of the data are either erased or stored encrypted. Also don't forget: A running system which uses full disk encryption is still vulnerable to network/Internet attacks!</p>
<p>There are two ways of setting up an encrypted disk using LVM:<br />
1. Create the LVM and encrypt every volume separately<br />
2. Set up LVM on top of an encrypted partition<br />
<a id="more"></a><a id="more-767"></a></p>
<p>The first method is described in the <a href="http://wiki.archlinux.org/index.php/System_Encryption_with_LUKS_for_dm-crypt">Arch Wiki</a></p>
<p>I'll explain the second way (which is even easier):</p>
<p><strong>Step 0: Preparing the hard drive</strong><br />
At the start we have to talk about the hard disk. I know, it is mentioned very often but it's important: BACKUP your data before you execute any of the commands below!<br />
After that we can start. To ensure that all sensible data is erased I'd suggest to overwrite the disk first. There are two options to erase data:<br />
1. Overwrite with zeros<br />
2. Overwrite with random data</p>
<p>In our case the second is the method of choice. This is because we are going to store data on the disk and in most cases the disk won't get full. The main point is here, that someone could see where your encrypted data ends because of the zeros at the end - an ideal starting point for an attack.<br />
The command to overwrite the disk with random data is:</p>
<p><code>dd if=/dev/urandom of=/dev/HARDDRIVE</code></p>
<p>This can take quite long depending on the size of your disk. Then we can setup the partitions, where we have to mention that we need at least one boot partition (~150 MB) and a partition for the LVM.<br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/pic3.jpg"><img class="aligncenter size-medium wp-image-785" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/pic3-300x186.jpg" alt="pic3" width="300" height="186" /></a><br />
The partitioning can be done with cfdisk. Don't forget to select "Write" before "Quit" and to mark the boot parition as "Bootable".<br />
Now, we are going to set up the encryption and the LVM.<br />
From now on, we call the partition where we want to have the encrypted LVM on <em>/dev/sda2</em> and the boot partition <em>/dev/sda1</em>.</p>
<p><strong>Step 1: Encryption</strong><br />
To encrypt /dev/sda2 we can use the following commands:</p>
<p>Load the encryption module:<br />
<code>modprobe dm-crypt</code></p>
<p>Set up encryption (aes-xts-plain is just a suggestion):<br />
<code>cryptsetup -c&Acirc;&nbsp;aes-xts-plain -y -s 512 luksFormat /dev/sda2</code></p>
<p>To explain what it does:<br />
-c is for the chiper algorithm (which is lrw)<br />
-y is for typing in passphrase a second time (as confirmation)<br />
-s is the length of the key (whereas in our case (lrw) just 256 are used)<br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/pic6.jpg"><img class="aligncenter size-medium wp-image-788" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/pic6-300x186.jpg" alt="pic6" width="300" height="186" /></a><br />
Now we have to access the encrypted volume:</p>
<p><code>cryptsetup luksOpen /dev/sda2 lvm</code></p>
<p>Of course, all the steps above work as well with different settings and a different chiper algorithm.</p>
<p><strong>Step 2: LVM</strong><br />
First of all we have to initialize the physical volume (in our case the reference to the encrypted volume) and create a volume group:</p>
<p><code>lvm pvcreate /dev/mapper/lvm<br />
lvm vgcreate vgroup /dev/mapper/lvm</code></p>
<p>You can adjust the following commands to your needs but be aware that you need at least a root and a swap partition. The command <em>lvm lvcreate</em> adds logical volumes to the volume group we just created:</p>
<p><code>lvm lvcreate -L 2GB -n root vgroup<br />
lvm lvcreate -L 512MB -n swap vgroup<br />
lvm lvcreate -L 512MB -n tmp vgroup<br />
lvm lvcreate -l 100%FREE -n home vgroup</code><br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch1.jpg"><img class="aligncenter size-medium wp-image-876" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch1-300x186.jpg" alt="arch1" width="300" height="186" /></a></p>
<p><strong>Step 3: Installation and configuration of Arch Linux</strong><br />
IMPORTANT: If you changed your keyboard layout by using the "km"-command you have to follow the <span style="color: #ff0000">KEYMAP</span> instructions below. If you are using standard us keyboard layout, you can ignore these instructions!</p>
<p>Start the Arch installer:</p>
<p><code>/arch/setup</code></p>
<p>-> Prepare Hard Drive -> Set Filesystem Mountpoints</p>
<p>First, you have to choose the mountpoints of <em>/</em> (root) and <em>/swap</em>. The other mountpoints are not mandatory but we already set up partitions for /home, /tmp and /boot. It is important to understand that the boot partition has to be unencrypted, so we choose <em>/dev/sda1</em> in our case. Then you can install Arch. There is an installation guide in the <a href="http://wiki.archlinux.org/index.php/Official_Arch_Linux_Install_Guide">Arch Wiki</a>.<br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch2.jpg"><img class="aligncenter size-medium wp-image-877" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch2-300x186.jpg" alt="arch2" width="300" height="186" /></a><br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/pic7.jpg"><img class="aligncenter size-medium wp-image-789" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/pic7-300x186.jpg" alt="pic7" width="300" height="186" /></a></p>
<p>After install we have to alter several configuration files:</p>
<p><em>/etc/rc.conf</em><br />
Set USELVM="no" to USELVM="yes"<br />
<span style="color: #ff0000">KEYMAP: </span> Change the KEYMAP field to the same as you chose with command "km". You can find a list of available KEYMAPS at the <a href="http://wiki.archlinux.org/index.php/KEYMAP">Arch Wiki</a>. The extension ".map.gz" should be removed.<br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch5-mod.jpg"><img class="aligncenter size-medium wp-image-885" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch5-mod-300x186.jpg" alt="arch5-mod" width="300" height="186" /></a><br />
<em><br />
/etc/mkinitcpio.conf</em><br />
Alter this line:<br />
<code>HOOKS="base udev autodetect pata scsi sata filesystems"</code><br />
to this:<br />
<code>HOOKS="base udev autodetect pata scsi sata encrypt lvm2 filesystems"<br />
</code><br />
It is important that <em>encrypt</em> is loaded BEFORE <em>lvm2</em>.</p>
<p><span style="color: #ff0000">KEYMAP: </span> Add <em>keymap</em> BEFORE encrypt:<br />
HOOKS="base udev autodetect pata scsi sata keymap encrypt lvm2 filesystems"<br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch4-mod.jpg"><img class="aligncenter size-medium wp-image-879" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch4-mod-300x186.jpg" alt="arch4-mod" width="300" height="186" /></a><br />
<em>/boot/grub/menu.lst</em><br />
Then, before installing grub you have to change the file <em>/boot/grub/menu.lst</em> at two points:<br />
Add "cryptdevice=/dev/sda2:vgroup" between "root=..." and "ro" in the paragraphs "Arch Linux" and "Arch Linux Fallback"<br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/pic1.jpg"><img class="aligncenter size-medium wp-image-783" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/pic1-300x186.jpg" alt="pic1" width="300" height="186" /></a><br />
Then install the bootloader to <em>/dev/sda</em></p>
<p>You can exit the installer now and restart with a fully encrypted system (except boot partition). No further changes are necessary.<br />
<a href="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch6-mod.jpg"><img class="aligncenter size-medium wp-image-886" src="http://www.pindarsign.de/webblog/wp-content/uploads/2009/02/arch6-mod-300x186.jpg" alt="arch6-mod" width="300" height="186" /></a></p>
<p>And remember:<br />
<img src="http://imgs.xkcd.com/comics/security.png" alt="" /><br />
(Source: http://xkcd.com/538/)</p>
<p><em>Changelog:<br />
- 6th June 2009: Added new screen shots, added the KEYMAP part (thanks to Jean's hint!) and altered the structure.</em></p>
<p><em>- 18th September 2012: Changed suggested cipher from aes-lrw to&Acirc;&nbsp; aes-xts (thanks to Stephen).</em></p>
