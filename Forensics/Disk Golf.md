# Disk Golf

**Category: FORENSICS**

**Description:**

>Let's play some disk golf!

### Solving the challenge

Looks like we are given a disk image to analyze. We can use tools like sleuthkit to look through what's inside. We first use `fls` to list all files and directories inside (grep out `flag.txt` after looking through it once), then we can use `icat` to print the data inside a node:

So we have a disk image, I've opened it using autopsy : 

![autopsy](/images/DiskGolf1.JPG)

We have some octals, I've used an online tool to convert those back to text :

![solve](/images/DiskGolf2.JPG)

### Flag

```n00bz{7h3_l0ng_4w41t3d_d15k_f0r3ns1c5}```
