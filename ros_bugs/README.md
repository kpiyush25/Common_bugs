The following error came while installing ros using the command `sudo apt-get install ros-melodic-desktop-full`

E: Failed to fetch http://in.archive.ubuntu.com/ubuntu/pool/universe/q/qhull/libqhull7_2015.2-4_amd64.deb  Hash Sum mismatch    Hashes of expected file:     - 
SHA256:317ad1b04476c76271253b75dd25d4611d6f564df40dc51186c882d0428a0aea     - SHA1:2f1d4e92cdc6c80a31abca7d0186cc72da5c7479 [weak]     - MD5Sum:75d09d7b1c05f016b1a07affa55a8268 
[weak]     - Filesize:151848 [weak]    Hashes of received file:     - SHA256:82b66f948fe4e180005ac322f2d46f00271f0175a22f0faa0c4cd5912d7649b5     - SHA1:0e5dc8b1900189c2b5c84ddaeb4c3111486afeb6 
[weak]     - MD5Sum:4197d89215623975cc928bb5ab401d00 [weak]     - Filesize:151848 [weak]    Last modification reported: Sat, 09 Dec 2017 23:29:29 +0000 E: Failed to fetch 
http://in.archive.ubuntu.com/ubuntu/pool/universe/g/gl2ps/libgl2ps-dev_1.4.0+dfsg1-1_amd64.deb  Hash Sum mismatch    Hashes of expected file:     - 
SHA256:debd520098c8c9af95adadce5c5b6f2cf11f3b1c0903492530f4028a798ef2e6     - SHA1:08d2162378fd42255d8f44428439c9cf6f51b147 [weak]     - MD5Sum:23d3c8
E: Failed to fetch http://in.archive.ubuntu.com/ubuntu/pool/universe/q/qhull/libqhull7_2015.2-4_amd64.deb  Hash Sum mismatch
   Hashes of expected file:
    - SHA256:317ad1b04476c76271253b75dd25d4611d6f564df40dc51186c882d0428a0aea
    - SHA1:2f1d4e92cdc6c80a31abca7d0186cc72da5c7479 [weak]
    - MD5Sum:75d09d7b1c05f016b1a07affa55a8268 [weak]
    - Filesize:151848 [weak]
   Hashes of received file:
    - SHA256:82b66f948fe4e180005ac322f2d46f00271f0175a22f0faa0c4cd5912d7649b5
    - SHA1:0e5dc8b1900189c2b5c84ddaeb4c3111486afeb6 [weak]
    - MD5Sum:4197d89215623975cc928bb5ab401d00 [weak]
    - Filesize:151848 [weak]
   Last modification reported: Sat, 09 Dec 2017 23:29:29 +0000
E: Failed to fetch http://in.archive.ubuntu.com/ubuntu/pool/universe/g/gl2ps/libgl2ps-dev_1.4.0+dfsg1-1_amd64.deb  Hash Sum mismatch
   Hashes of expected file:
    - SHA256:debd520098c8c9af95adadce5c5b6f2cf11f3b1c0903492530f4028a798ef2e6
    - SHA1:08d2162378fd42255d8f44428439c9cf6f51b147 [weak]
    - MD5Sum:23d3c8366a62a76669f82d8c74ebdad4 [weak]
    - Filesize:239588 [weak]
   Hashes of received file:
    - SHA256:303f7285710e7faaf2f6b0133b5986d9c6dc4a2370e965cd0ab7913c439f54be
    - SHA1:d37bc723cd63e0ea579fb0cb09f9dcebdb1e86d7 [weak]
    - MD5Sum:37832ffd78e29d87693c88090bccdc1b [weak]
    - Filesize:239588 [weak]
   Last modification reported: Thu, 02 Nov 2017 23:13:20 +0000
E: Failed to fetch http://in.archive.ubuntu.com/ubuntu/pool/universe/l/leptonlib/liblept5_1.75.3-3_amd64.deb  Hash Sum mismatch
   Hashes of expected file:
    - SHA256:3f0a4bbb34d0096eed2760e5c72ccfe2cd1d897bb0ba2c2a54be28dd9d4c38c9
    - SHA1:12efa14896d61c4713bbb9a75eedffe2e5c12ac4 [weak]
    - MD5Sum:efc35a946788a4d745af6f8e051d0127 [weak]
    - Filesize:928940 [weak]
   Hashes of received file:
    - SHA256:807670989b81c1b3c606f0460026d4925f2c6dcf9be1e649d32bd24b031d36ee
    - SHA1:bcddb877da0b378f20d41c393081c5db4d8132d7 [weak]
    - MD5Sum:22c2ca19d271f9d0b1fd8321e2c4f881 [weak]
    - Filesize:928940 [weak]
   Last modification reported: Thu, 19 Apr 2018 09:05:27 +0000
E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
---------------------------------------------------
Then on running `sudo apt-get upgrade` the following error came:
Processing triggers for initramfs-tools (0.130ubuntu3.12) ...
update-initramfs: Generating /boot/initrd.img-5.4.0-42-generic
W: Possible missing firmware /lib/firmware/rtl_nic/rtl8125a-3.fw for module r8169
--------------------------------------------------
 Solution:
`sudo update-grub`
then
`sudo apt-get upgrade`
then `sudo apt-get install ros-melodic-desktop-full`
And the error was resolved


## Issue 2

Command used: `roslaunch talker-listener talker-listener_node`

Terminal Output:

`
[talker-2] process has finished cleanly

log file: /home/piyush/.ros/log/fd72e3ca-c15f-11eb-abbe-d0abd521f44e/talker-2*.log`

After this the node was being killed automatically.

(Took a lot of time to debug and what we found was embarassing, that person had 
put `return 0;` in the while loop itself whose condition is `ros::ok()`)

Solution : Remove that `return 0;` line from while loop ;-;

       
