# Introduction
  - Standardize the directory structure in linux.
  - Specify the directories that must or should exist.
  - According to the conditions of shareable/unshareable and static/variable, they can be roughly devided into 4 types.

---

# Directory tree
```
# Refs: https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard

/ -> Root directory 
 \
  + boot/ --> Boot loader files 
  |       \
  |        + e.g. kernel, grub2.
  |
  + etc/ ---> Host-specific system-wide configuration files.
  |       \
  |        + opt/ --> Configuration files for add-on packages stored in /opt/
  |        |
  |        + X11/ --> Configuration files for the X Window System, version 11.
  |        |
  |        + sgml/ -> Configuration files for software that processes SGML.
  |        |
  |        + xml/ --> Configuration files for software that processes XML.
  |
  + sbin/ --> Essential system binaries.
  |       \
  |        + e.g. fsck, init, route
  |        |        
  |        * link to /usr/sbin/
  |
  + bin/ ---> Essential command binaries available in single-user mode.
  |       \
  |        + e.g. cat, ls, cp
  |        |        
  |        * link to /usr/bin/
  |
  + lib/ ---> Libraries essential for the binaries in /bin/ and /sbin/.
  |       \
  |        + modules/ -> Exchangeable module drivers.
  |        |        
  |        * link to /usr/lib/
  |
  + opt/ ---> Add-on application software packages.
  |
  + srv/ ---> Site-specific data served by this system.
  |
  + run/ ---> Run-time variable data. (virtual)
  |
  + tmp/ ---> Directory for temporary files (see also /var/tmp/).
  |
  + dev/ ---> Device files.
  |       \
  |        + e.g. null, sd[:lower:]*, disk*, tty*, ram*
  |
  + media/ -> Mount points for removable media such as CD-ROMs.
  |
  + mnt/ ---> Temporarily mounted filesystems.
  |
  + usr/ ---> Secondary hierarchy for read-only user data.
  |       \
  |        + bin/ -----> Non-essential command binaries.
  |        |
  |        + sbin/ ----> Non-essential system binaries.
  |        |
  |        + lib/ -----> Libraries for the binaries in /usr/bin/ and /usr/sbin/
  |        |
  |        + include/ -> Standard include files.
  |        |
  |        + src/ -----> Source code.
  |        |
  |        + local/ ---> Other versions of linux.
  |        |
  |        + share/ ---> Architecture-independent (shared) data.
  |                  \
  |                   + e.g. man, doc, zoneinfo
  |
  + var/ ---> Variable files during normal operation of the system.
  |       \
  |        + cache/ -> Application cache data.
  |        | 
  |        + lib/ ---> Persistent data modified by programs as they run.
  |        |       \
  |        |        + e.g. mysql/ for MySQL
  |        |
  |        + lock/ --> Files keeping track of resources currently in use.
  |        | 
  |        + log/ ---> Log files. Various logs.
  |        | 
  |        + mail/ --> Mailbox files.
  |        | 
  |        + run/ ---> Run-time variable data.
  |        |       \
  |        |        * link to /run/
  |        | 
  |        + spool/ -> Spool for tasks waiting to be processed.
  |                \
  |                 * link to /var/mail/
  |
  + home/ --> Home directory for users.
  |
  + root/ --> Home directory for the root user.
  |
  + proc/ --> Provide process and kernel information. (virtual)
  |
  + sys/ ---> Information about devices, drivers, and kernel. (virtual)


```