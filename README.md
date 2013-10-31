# RALUS-arch

RALUS (Remote Agent for Linux and UNIX Servers) is part of Symantec Backup Exec. It allows backing up linux and unix systems. RALUS officially only supports several enterprise linux distributions. This PKGBUILD should help to get RALUS working on arch linux systems. Its tested only on 64Bit for version 14.0.1798-0, however it should be easy to adopt to 32Bit or other versions.

# Where to get the installation files

To get the file follow this procedure:

1) Get the Backup Exec ISO or a installation medium
2) Unpack RALUS_RMALS_RAMS-1798.17.tar.gz (LinuxUnixMac-Subdirectory)
3) x86    -> Unpack VRTSralus.tar.gz from \pkgs\Linux\
   x86_64 -> Unpack VRTSralus.tar.gz from \RALUS64\pkgs\Linux\  
4) copy VRTSralus*.rpm to your source directory 

# Warning
This PKGBUILD includes a binary hack to allow RALUS to work on linux kernel <=3 - like the whole script: Use at your own risk!

# Thanks To
   http://blog.redweb.at/2012/08/howto-backupexec-2012-linux-agent-and-kernel-3-0-debian/
   http://www.css.washington.edu/wiki/BackupExec_on_Debian
     Philip Weber (Kernel 3.x patch guide)
     Jeremie (Automated patching)

