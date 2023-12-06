#Linux Terminal Compendium

Structure of this compendium:

1. List of books about Linux, Terminal, Bash
2. Iteration of books by listing their 'table of content'
3. Merge of 'table of content' and my personal journey_map

## List of Books

1. Das Linux Terminal Handbuch: Bash Kommandos fuer Einsteiger (Josef Moser)
	- private published - no table of content
1. Linux Kommandoreferenz. Shell-Befehle von A bis Z (Michael Kofler)
	- see alexandria
1. Linux Befehlreferenz kompakt: Thematisches Shellkommando-Verzeichnis (Klaus Utech)
	- private published - no table of content
1. Linux- die wichtigen Befehle kurz & gut (Daniel Barret)
	- not mention value
1. Shell-Programmierung: Das umfassende Handbuch (Frank Sommer)
	- see alexandria
1. Efficient Linux at the Command Line. Boost Your Command-Line Skills (Daniel Barret)
	- see alexandria
	- full pdf
1. Grundlagen und Praxis der Bash- und C-Programmierung in Unix/Linux (Antonova/Slaveva)
	- see alexandria
	- no important new input
1. The Linux Command Line (William Shotts)
	- see alexandria
	- full pdf
1. Pro Bash. Learn to Script and Program the GNU/Linux Shell (Jayant Varma)
	- see alexandria
1. bash Cookbook. Solutions and Examples for bash users (Albing/Vossen)
	- see alexandira
	- full pdf
1. Mastering Linux Shell Scripting. A practical guiede to Linux command-line (Ebrahim/Mallett)
	- table of content not found
1. bash Idioms. Write Powerful, Flexible, Readable Shell Scripts (Albing/Vossen)
-	- table of content not found
1. From Bash to Z Shell. Conquering the Command Line (Kiddle/Peek/Stephenson)
	- see alexandria
1. Advanced Bash-Scripting Guide (Mendel Cooper)
	- see alexandria
	- full pdf
1. Bash Guide for Beginners (Bachtelt Garrels)
	- see alexandira
	- full pdf
1. Bash Reference Manual
	- see alexandria
	- full pdf

## Iterativ listing of 'table of content'
### Linux Kommandoreferenz
- All terminal commands are listed. They are ordered in subthemes:
1. Dateien verwalten
  - cat, cd, chgrp, chmod, chown, cp, dircolors, file, inotifywait, j, ln, ls,
mkdir, mv, namei, rdfind, rename, rm rmdir, rsync, stat, tee, touch, tree, truncate,
umask
2. Dateien suchen
  - ack, egrep, find, grep, locate, updatedb, whereis, which
3. Dateien kompimieren und archivieren
  - bunzip2, bzip2, compress, cpio, gunzip, gzip, lzop, tar, uncompress, unxz,
unzip, xz, zip, zipinfo
4. Textdateien verarbeiten
  - awk, cat, column, csplit, cut, diff, expand, fold, grep, head, iconv, less,
more, multitail, paste, patch, recode, sed, sort, split, strings, tac, tail, tr,
unexpand, uniq, zcat, zless, zmore
5. Accress Control Lists (ACLs) and Extended Attributes (EAs)
  - attr, chacl, getcap, getfacl, getfattr, setcap, setfacl, setfattr
6. Konverter
  - avconc, convert, dvips, enscript, epstopdf, exiftool, ffmpeg, iconv, lame,
mogrify, mpage, pandoc, paps, pdf2ps, pdfimages, pdftk, pdftops, pdftotext, ps2pdf,
recode
7. Prozesse verwalten
  - at, atq, atrm, batch, bg, chroot, contab, disown, fg, fuser, glances, halt,
history, htop, iftop, ionice, iotop, kill, killall, ldconfig, ldd, lsof, nice,
nohup, parallel, pidof, powertop, ps, pstree, reboot, renice, sudo, timeout, top,
uptime, watch
8. Benutzer und Gruppen verwalten
  - addgroup, adduser, chage, chgrp, chown, chpasswd, chsh, delgroup, deluser,
groupadd, groupdel, groupmod, groups, gpasswd, id, last, lastb, makepasswd, mkpasswd,
newgrp, newusers, passws, pwgen, useradd, userdel, usermod, vigr, vipw, visudo, who
9. Dateisystem administrieren
  - badblocks, blkid, btrfs, cfdisk, cryptsetup, dd, df, du, dumpe2fs, e4defrag,
exfatlable, findmnt, fstrim, kpartx, lsblk, mdadm, mkfifo, mkfs, mknod, mkswap,
mount, ncdu, parted, partprobe, partx, resize2fs, sfdisk, sgdisk, smartctl, snapper, 
swapoff, swapon, sync, tune2fs, umount, xfs_admin, xfs_growfs, xfs_info, xfs_repair
10. Logical Volume Manager (LVM)
  - lvcreate, lvdisplay, lvextend, lvm, lvreduce, lvremove, lvrename, lvscan, pvcreate,
pvdisplay, pvremove, pvscan, vgchange, vgcreate, vgdisplay, vgextend, vgmerge,
vgreduce, vgrename, vgscan
11. SELinux und AppArmor
  - aa-complain, aa-disable, aa-enforce, aa-status, chcon, getenforce, restorecon, 
sealert, sestatus, setenforce, setsebool
12. Paketverwaltung
  - apk, apt, add-apt-repository, alien, alternatives, apt-cache, apt-get, apt-key,
aptitude, cnf, dnf, dpkg, flatpak, gdebi, pip, pkcon, ppa-purge, repoquery,
rpm, rpm2archive, rpm2cpio, snap, tasksel, ubuntu-security-status, update-alternatives,
yum. zypper
13. Netzwerk administrieren
  - cadaver, curl, dhclient, dig, etherwake, ethtool, exportfs, firewall-cmd, ftp,
host, hostname, hostnamectl,ifconfig, ifdown, ifup, ip, ipcalc, iptables, iptables-resotre,
iptables-save, iptables-xml, iw, iwconfig, iwlist, mtr, nft, netplan, netstat, networkctl, 
newaliases, nmap, rnmcli, openssl, ping pnuke, postconf, postqueue, pscp, pssh, rdiff-backup,
rfkill, route, rpcinfo, rsync, scp, sftp, showmount, smbclient, smbtree, ss, ssh, ssh-copy-id,
telnet, traceroute, ufw, wakeonlan, wget, whois, wol, wpa_passphrase
14. Hacking and Security
  - arp-scan, chkrootkit, fail2ban-client, hydra, john, nc, ngrep, nmap, rkhunter, tcpdump
15. Drucker-, Datenbank- und Server-Administration
  - acme.sh, certbot, htpasswd, lpadmin, lpinfo, lpoptions, lpq, lpr, lprm, lpstat,
mysql, mysqladmin, mysqlbinlog, mysqldump, smbpasswd, sqlite3
16. Audio-Funktionen und Hardware-Verwaltung
  - acpi, alsactl, alsamixer, amixer, boltctl, free, fwupdmgr, hwclock, kbdrate,
localectl, lscpu, lshw, lspci, lsscsi, lsusb, nproc, pactl, paplay, parecord, powertop,
speaker-test, timedatectl, vcgncmd
17. Bluetooth
  - bluethoothctl, hciconfig, hcitool, l2ping, rfkill, sdptool
18. Kernel
  - canocical-livepatch, depmod, dmesg, dracut, insmod, kexec, lsmod, modinfo,
modprobe, uname,update-initramfs
19. Systemstart und -stopp, Init-System, Logging und GRUB
  - efibootmgr, grub-install, grub-mkconfig, init, journalctl, logger, loginctl, 
needs-restarting, service, shutdown, systemctl, updsate-grub
20. Virtualisierung & Co. (Cloud, Docker, libvirt, KVM, Vagrant)
  - aws, docker, docker-compose, kvm, qemu-img, qemu-kvm, qemu-nbd, virsh, virt-clone,
virt-install, virt-viewer, wsl
21. Terminal und Textkonsole
  - echo, loadkeys, printf, reset, screen, setfront, setterm
22. Online-Hilfe
  - apropos, help, info, man, whatis
23. Grafiksystem und Gnome
  - chvt, dconf, fc-list, fgconsole, glxinfo, gnome-session-quit, gsettings,
gtf, nvidia-xconfig, tvservice, xdpyinfo, xhost, xinput, xkill, xrandr, xset, zenity
24. Sonstiges
  - alias, basename, cksum, date, dirname, expr, git, gpio, hash, ldd, lsb_release, mail,
md5sum, printenv, qalc, reapsi-gpio, raspisstill, raspivid, seq, set, sha512sum, sleep,
strace, svn, time, tty, type, unalias, uname, xargs
25. bash-Programming
  - break, case, continue, exit, for, function, if, local, source, test, until, while
26. bash-Variablenverwaltung
  - alias, declare, export, local, read, readonly, shift, unalias, unset
27. Weitere bash-Kommandos und -Sonderzeichen
  - dirs, disown, eval, popd, pushd, trap, ulimit, wait, #&%!
28. Konfigurationsdateien
  - adduser.conf, aliases, bashrc, config.txt, corontab, deluser.conf, dhcpcd.conf,
dnf.conf, fstab, group, grub, grub.cfg, gshadow, host.conf, hostname, hosts, ifcfg-xxx,
inittab, interfaces, journald.conf, locale.conf, login.defs, mdadm.conf, modules, netplan.yaml,
networkd.network, nsswitch.conf, os-release, passwd, profile, rc.local, resolv.conf, rsyslog.conf,
services, shadow, sources.list, sudoers, sysctl.conf, systemd.service, systemd.timer, vconsole.conf,
wpa_supplicant.conf, xorg.conf, yum.conf
29. Tastenkuerzel
  - bash, emacs, fdisk, gnome-terminal, grub, info, joe, konsole, less, man, mutt, nano, screen, vim 

### Shell-Programmierung
I: Einfuehrung
1. Was ist eine Shell?
  - Was ist ein Shellscript?
  - Vergleich mit anderen Sprachen
2. Kommando, Programm oder Shellscript?
  - Shell-eigene Kommandos (Builtin-Kommandos)
  - Aliase in der Shell
  - Funktionen in der Shell
  - Shellscripts (Shell-Prozeduren)
  - Programme (binaer)
3. Die Shell-Vielfalt
  - ksh (Korn-Shell), Bash (Bourne-Again-Shell), zsh (Z-Shell), ash (A-Shell),
rbash, rzsh (Restricted Shell), tcsh (TC-Shell), rsh, ssh
4. Crashkurs: einfacher Umgang mit der Kommandozeile
5. Shellscripts schreiben und ausfuehren
  - Der Editor
  - der Name des Shellscripts
  - Ausfuehren
  - Hintergrundprozesse starten
  - Ausfuehrende Shell festlegen
  - Stil
  - Ein Shellscript beenden
  - Testen und Debuggen von Shellscripten
  - Ein Shellscript, das ein Shellscript erstellt und ausfuehrt
6. Vom Shellscript zum Prozess
  - Ist das SHellscript ein Prozess?
  - Echte Login-Shell?
7. Datenstrom
  - Ausgabe umleiten
  - Standardfehlerausgabe umleiten
  - Eingabe umleiten
  - Pipes
  - Ein T-Stueck mit tee
  - Ersatzmuster (Wildcards)
  - Brace Extension
  - Muster-Alternativen
  - Tilde-Expansion
II: Variablen
8. Grundlagen
  - Zugriff aud den Wert einer Variablen
  - Variablen-Interpolation
9. Zahlen
  - Integer-Arithmetik
  - bc - Rechnen mit Fliesskommazahlen und mathematischen Funktionen
10. Zeichenketten
  - Stringverarbeitung
  - Erweiterte Funtkionen
11. Quaotings und Kommando-Substitution
  - Single und Double Quotings
  - Kommando-Substitution - Back Quotes
12. Arrays
13. Variablen exportieren
14. Umgebungsvariablen eines Prozesses
15. Shell-Variablen
16. Automatische Variablen der Shell
  - $0, $$, $?, $!, 
III: Parameter und Argumente
17. Kommandozeilenparameter $1 bis $9
18. Besondere Parameter: $\*, $@, $#
19. Der Befehl shift
20. Argumente und Leerzeichen
21. Argumente jenseits von $9
22. Argumente setzen mit set und Kommando-Substitution
23. getopts - Kommandozeilenoptionen auswerten
24. Vorgabewerte fuer Variablen
IV: Kontrollstrukturen
25. If, else, elif
26. Das Kommando test 
  - Ganze Zahlen vergleichen
  - Zeichenketten vergleichen
27. Status von Dateien erfragen
28. Logische Verknuepfung von Ausdruecken
  - Negationoperator !, UND (-a / &&), ODER (-o / ||)
29. Short Circuit-Tests - ergebnisabhaengige Befehlsausfuerhung
30. Case
  - Alternative Vergleichsmuster
  - Case und Wildcards
  - case und Optionen
31. Schleifen
  - For-Schleife
  - While-Schleife
  - unitl-Schleife
32. Kontrollierte Spruenge
  - continue
  - break
V: Terminal Ein- und Ausgabe
33. Ausgabe
  - Befehl echo
  - print
  - Befehl printf
  - Befehl tput - Terminalsteuerung
34. Eingabe
  - Befehl read : Zeilenweise lesen einer Datei/mit einer Pipe
  - Here-Dokumente
  - Variable IFS
  - Arrays einlesen
  - Einzelne Zeichen abfragen
  - Passworteingabe
35. Umlenken mit dem Befehl exec
36. Filedeskriptoren
37. Named Pipes
38. Menues mit select
VI: Funktionen
39. Definition
  - Funktionsaufruf
  - Funktionen exportieren
  - Aufrufreihenfolge
  - Aufrufe selbst bestimmen
  - Funktionen auflisten
40. Funktionen die Funktionen aufrufen
41.  Parameteruebergabe
  - FUNCNAME
42. Rueckgabewerte aus einer Funktion
  - return
  - echo / Kommando-Substitution
  - Funktionen und exit
43. Locale contra globale Variablen
44. alias und unalias
45. Autoload
VII: Signale
46. Gurndlagen zu den Signalen
47. Signale senden - kill
48. Eine Fallgrube fuer Signale - trap
  - Einen Signalhandler (Funktion) einrichten
  - Mit Signalen Schleifendurchlaeufe abbrechen
  - Mit Signalen das Script beenden
  - Das Beenden der Shell (oder eines Scripts) abfangen
  - Signale ignorieren
  - Signale zuruecksetzen
VIII: RUnd um die Ausfuehrung von Scripts und Prozessen
49. Prozessprioritaeten
50. Warten auf andere Prozesse
51. Hintergrundprozesse wieder hervorholen
52. Hindergrundprozesse schuetzen
53. Subshells
54. Mehrer Scripts verbinden und ausfuehren (Kommunikation zwischen Scripten)
  - Datenuebergabe
  - Rueckgabe von Daten
  - Scripts synchronosieren
55. Jobverwaltung
56. Shellscripts zeitgesteuert ausfuehren
57. Startprozess- und Profildaten der Shell
  - Arten von Initialisierungsdateien
  - Ausfuehren von Profildateien beim Start einer Login-Shell
  - Ausfuehren von Profildateien beim Start einer Nicht-Login-Shell
  - Zusammenfassung all Profil- und Startup-Dateien
58. Ein Shellscript bei der Ausfuehrung
  - Syntaxueberpruefung
  - Expansionen
  - Kommandos
IX: Nuetzliche Funktionen
  - eval, xargs, dirname/basename, umask, ulimit, time, typeset
X: Fehlersuche und Debugging
59. Stragegien zum Vermeiden von Fehlern
  - Planung, Testsystem bereitstellen, Ordnung
60. Fehlerarten
61. Fehlersuche
  - Trace mit set -x
  - DEBUG- und das ERR-Signal
  - Variablen und Syntax ueberpruefen
  - Debug-Ausgabe hinzufuegen
  - Debugging-Tools
XI: Regulaere Ausdruecke und grep
62. Regulaere Ausdruecke
63. grep
  - grep mit Regex, grep mit Pipes, grep mit Optionen, egrep, fgrep, rgrep
XII: Der Stream-Editor sed
64. Funktions- und Anwendungsweise von sed
  - Grundlegende Funktionsweise
  - Wohin mit der Ausgabe?
65. Adressen
66. Kommandos, Substitutionsflags, Optionen von sed
  - Kommandos: a, c, d, h/H/g/G/x (Puffer), i, p, q, r, w, s, y
  - sed-Scripts
XIII: awk-Programmierung
67. Einfuerhung und Grundlagen von awk
  - History und Versionen
  - Funktionsweise von awk
68. Aufruf von awk-Programmen
  - Aufbau eines awk-Kommandos
  - Kommandozeilen-Optionen
  - awk aus Kommandozeile aufrufen
  - awk in Shellscripts aufrufen
  - awk als eigenes script aufrufen
69. Grundlegende awk-Programme und -Elemente
  - Ausgabe von Zeilen und Zeilennummer
  - Felder
70. Muster (bzw. Adressen) von awk-Scripts
  - Zeichenkettenvergleich
  - Vergleichsausdruecke
  - Regulaere Ausdruecke
  - Zusammengesetzte Ausdruecke
71. Komponenten von awk-Scripts
  - Variablen, Arrays, Operatoren, Kontrollstrukturen
72. Funktionen
  - Mathematische Funktionen
  - Funktionen fuer Zeichenketten
  - Funktionen fuer Zeiten
  - Systemfunktionen
  - Ausgabefunktionen
  - Eingabefunktionen
XIV: Kommandoreferenz
  - Dateiorientierte Kommandos
  - Verzeichnisorientierte Kommandos
  - Verwaltung von Benutzern und Gruppen
  - Programm- und Prozessverwaltung
  - Speicherplatzinformationen
  - Dateisystem-Kommandos
  - Archivierung und Backup
  - Systeminformationen
  - System-Kommandos
  - Druckeradministration
  - Netzwerkbefehle
  - Benutzerkommunikation
  - Bildschirm- und Terminalkommandos
  - Online-Hilfen
XV: Praxis
73. Datei-Utilitys
  - Leerzeichen im Dateinamen ersetzen, Dateiendungen veraendern, Dateien in zwei 
Verzeichnissen vergleichen, Dateien in mehreren Verzeichnissen aendern
74. Systemadministration
  - Benutzerverwaltung, Systemueberwachung
75. Backup-Strategien
  - Varianten, bestimmte Bereiche, Backup ueber ssh mit tar, rsync
76. Das World Wide Web und HTML
  - Analysieren von access_log, error_log
77. CGI (Common Gateway Interface)
  - CGI-Scripts ausfuehren, CGI-Environment ausgeben
XVI: GUIs und Grafik
78. dialog und Xdialog
79. gnuplot - Visualisierung von Messdaten
XVII: Befehle
  - Shell-Builtin-Befehle
  - Externe Kommandos
  - Shell-Optionen
  - Shell-Variablen
  - Kommandozeile editieren
  - Wichtige Tastenkuerzel (Kontrolltasten)
  - Initialisierungsdateien der Shells
  - Signale
  - Sonderzeichen und Zeichenklassen 

### Pro Bash. Learn to Script and Program the GNU/Linux Shell
I:
1. Naming of Scripts
2. Selecting a directory for the Script
3. Creating the File and Running the Script
II: Input, Output and Throughput
4. Parameters and Variables
  - Positional Parameters
  - Special \*@#0$?\_! Parameters
  - Arguments and Options 
  - echo, and

