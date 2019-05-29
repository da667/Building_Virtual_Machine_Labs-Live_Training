This repo is to host content for the Building Virtual Machine labs training. It contains a slide deck in pptx and PDF format. This material is unofficially related under the MIT license. If you're unfamiliar with the MIT license, it more or less means "Do whatever comes natural, but don't expect me to support it in ANY way. I am in no way liable if this."

Want to modify the slide deck? add/remove things, change distros, host a hackathon for your Defcon group, hacker/makerspace, CTF meet-up group, student club or whatever? Do whatever you want. the PPTX has been supplied so you can change it however you see fit. Knowledge wants to be shared.


==DETAILS==

This training is more or less a refreshed adaptation of Building Virtual Labs: A hands-on guide exclusively utilizing Oracle virtualbox.

Why virtualbox? Because, its the lowest common denominator:

-Its free

-It runs on every major operating system (Windows, Linux, and OSX)

-And so long as your hardware is 64-bit and supports virtualization extensions (e.g. Intel VT-x, AMD-V), it'll run mostly okay.

-Virtualbox is the most commonly used hosted hypervisor for most other trainings I have been to for exactly the same reasons I mentioned above. This means the lab we build together here can easily be adapted for when you attend other training events

-Most virtual machine images are either VMDK(VMware) or VDI (virtual disk image) files, both of which virtualbox supports seamlessly, allow you to easily take those VM images from vulnhub or wherever else and adapt them to your lab environment with little effort

==SOFTWARE REQUIREMENTS==

This class is meant to support students/users who want to run Virtualbox on Linux, OSX, or Windows. In order to successfully participate in this class, there are some software packages/programs that I recommend you have on-hand that vary by your host operating system. If the software I recommend is a third party tool, I will provide links on where you can download the software. If the software I recommend is integrated into the operating system (or /should/ be integrated in the operating system), I will denote that.

Note: for OS integrated software applications on OSX/Linux, you can open a terminal session and use the which command to confirm that the application is available and listed on your shell's PATH variable (e.g. which [list of commands to check for, separated by spaces])

Windows:

-Virtualbox: https://www.virtualbox.org/wiki/Downloads (click the "Windows hosts" link under "Virtualbox X.X.X platform packages")

-mRemoteNG: https://mremoteng.org/download 

-WinSCP: https://winscp.net/eng/download.php 

-7-zip (64-bit): https://www.7-zip.org/download.html 

-puttygen (64-bit): https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html 

-Notepad++ (64-bit): https://notepad-plus-plus.org/download/ 

-KeePassXC (64-bit): https://keepassxc.org/download/#windows

Linux:

-Virtualbox: https://www.virtualbox.org/wiki/Linux_Downloads (recommended: Click the "All distributions" link under "Virtualbox X.X.X for Linux", and download the .run file for easy install)

-vi/vim (OS Integrated)

-ssh (OS Integrated)

-ssh-keygen (OS Integrated)

-scp (OS Integrated)

-zip/unzip (OS Integrated)

-gzip/gunzip (OS Integrated)

-alias (OS Integrated)
-KeePassXC: https://keepassxc.org/download/#linux (Recommended: click the "Official AppImage" link, and download the 
appimage for easy install)

-Some sort of a graphical text editor, in case you don't like vi/vim (e.g. leafpad, gedit, kwrite, etc.)

-Some sort of a terminal application (e.g. konsole, terminal, gnome terminal, etc. Recommended: If your distro/package manager has the package, try installing Terminator[https://gnometerminator.blogspot.com/p/introduction.html])

OSX:

-Virtualbox: https://www.virtualbox.org/wiki/Downloads (click the "OS X hosts" link under "Virtualbox X.X.X platform packages"")

-vi/vim (OS Integrated)

-ssh (OS Integrated)

-ssh-keygen (OS Integrated)

-scp (OS Integrated)

-zip/unzip (OS Integrated)

-gzip/gunzip (OS Integrated)

-alias (OS Integrated)

-BBEdit: https://www.barebones.com/products/bbedit/download.html (the basic/free features will serve our purposes)

-iTerm2: https://www.iterm2.com/downloads.html

-KeepassXC: https://keepassxc.org/download/#mac

Now, In addition to the software packages for your host, you will need to download the following OS installation ISOs and Virtual Machine images:

-Ubuntu Server ISO (Download the latest "LTS" release. Currently, this is Ubuntu 18.04.x): https://www.ubuntu.com/download/server

-Kali Linux 64-bit ISO: https://www.kali.org/downloads

-pfSense: https://www.pfsense.org/download/ (select “AMD64 (64-bit)” as the Architecture, and “CD Image (ISO) Installer” as the Installer)

-Metasploitable2: https://sourceforge.net/projects/metasploitable/files/Metasploitable2/ (download metasploitable-linux-2.0.0.zip)

Now, we need to download our Splunk components. In order to do this, you need to register to their website. Visit:
https://www.splunk.com/page/sign_up

-Fill out the form, splunk will send you a confirmation email, document your credentials (preferably in KeePassXC), and log in. Once you have logged in, you'll need to download the following items:

-Splunk Enterprise, 64-bit Linux, 2.6+ kernel, ".deb" package: https://www.splunk.com/en_us/download/splunk-enterprise.html#tabs/linux

-Splunk Universal Forwarder, 64-bit Linux, 2.6+ kernel, ".deb" package: https://www.splunk.com/en_us/download/universal-forwarder.html#tabs/linux

You'll need one of the following apps, depending on if you're going to install Snort or Suricata IDS/IPS software in your lab? Not sure? Confused? Just download both of them for now:

-Splunk TA for Suricata: https://splunkbase.splunk.com/app/2760/

-Hurricane Labs Add-On for Unified2: https://splunkbase.splunk.com/app/1858/

This section isn't exactly mandatory, but you'll thank me later. Request a "Developer" license for Splunk Enterprise. This will increased the amount of data you are allowed to index from the default of only 500MB to 10GB per day. Perfect for a learning environment.

-https://splunkbase.splunk.com/develop/ (Click the link labeled "Request Free Developer License"). Please note that developer licenses have to be "approved" by Splunk, and that this process takes anywhere from 1 to 3+ business days. However, I have *yet* to be denied.

Finally, I have some github projects for you to download:

If you want to install Snort IDS/IPS for your lab environment, download this:

-Autosnort: github.com/da667/Autosnort

If you want to install Suricata IDS/IPS for your lab environment, download this:

-Autosuricata: github.com/da667/Autosuricata

This is a script for setting up update automation on the Linux lab VMs eventually:

-updater: https://gist.github.com/da667/20f1c67c264f7823c7139f5c835a7026

Linux Users, This is a script for configuring vboxnet0 for connecting to our lab VMs over the virtual network:

-flightcheck-Linux.sh: https://gist.github.com/da667/ce39d245bd9d6bd30a205156a48ec67e

OSX Users, This is a script for configuring vboxnet0 to connect to our lab VMs over the virtual network:

-flightcheck-OSX.sh: https://gist.github.com/da667/1a71ac4e85867a75785291c53306237f

This github repo contains a bookmarks.html and JSON file (exported from Firefox) with links to other free/cheap 
training resources. Run into something that confused you in this training, trying digging through the resources here:
 https://github.com/da667/Training_Materials_Bookmarks

==HARDWARE REQUIREMENTS==
Here are the hardware requirements I recommend:

-RAM: minimum of 8GB of RAM, with 16GB+ recommended.

-Disk Space: minimum of 500GB+ of free disk space to account for ISOs, applications, snapshots and VM disk images.

-CPU: CPU needs to support 64-bit operation and either needs to have AMD’s AMD-V or Intel’s VT-x capability. Recommend something with at least 4+ cores

-Motherboard: BIOS/UEFI needs to support AMD-V or VT-x

==HAVE ANYTHING TO SAY?==

I know this is rich coming from a shitposter, but please limit your input to constructive criticism. What did you like, what didn't you like, what could be improved, etc. Heres a link to a google form:
-https://forms.gle/ALVYgqwogN5jCjyc8 

==WANNA GIVE ME MONEY FOR NO REASON?==

-paypal.me/da667

