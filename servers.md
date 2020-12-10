# Servers
## Streaming: vidio audio live recording
### 1. Agora
https://www.agora.io/en/pricing/
Kk.contact.mail@gmail.com 

## Web Framework Benchmarks
* https://www.techempower.com/benchmarks/


https://w3techs.com/technologies/history_overview/web_server

https://www.simform.com/nodejs-vs-django/

https://swizec.com/blog/benchmarking-node-tornado-and-django-for-concurrency

https://dzone.com/articles/learn-python-django-in-4-hours

## Samba server setup

### Information
smb://ll-SRV-file.livinglab.local
FQDB -> 51_Messdaten: Not backed up.
livinglab\USERNAME

### Commands

Windows command window:

C:\Users\k.mayannavar>ping  LL-SRV-FILE.livinglab.local

Pinging LL-SRV-FILE.livinglab.local [10.5.10.5] with 32 bytes of data:
Reply from 10.5.10.5: bytes=32 time<1ms TTL=128
Reply from 10.5.10.5: bytes=32 time<1ms TTL=128

Linux terminal windows where we would like to access shared folder

nxp@livinglab-CELSIUS-W550power:~/data/dashboard/Karin_DB/25.08.20$ sudo mount -t cifs -o user=livinglab/k.mayannavar //10.5.10.5/Daten  /mnt/x
Password for livinglab/k.mayannavar@//10.5.10.5/Daten:  ********
mount error(13): Permission denied
Refer to the mount.cifs(8) manual page (e.g. man mount.cifs)
nxp@livinglab-CELSIUS-W550power:~/data/dashboard/Karin_DB/25.08.20$

#### Mount:

nxp@livinglab-CELSIUS-W550power:~/data/dashboard/Karin_DB/25.08.20$ sudo mount.cifs -v  //10.5.10.5/Daten /mnt/x --verbose -o user=k.mayannavar,domain=livinglab
Password for k.mayannavar@//10.5.10.5/Daten:  ********
nxp@livinglab-CELSIUS-W550power:~/data/dashboard/Karin_DB/25.08.20$ ls /mnt/x/
01_Administration             05_Finance & Purchasing        08_IT                   12_Knowledge Collection (e.g. Literature)  99_LRZ Datenstand
02_Organization               05_PROJECTS                    09_Research Teams       13_Lectures                                Erläuterung der Ordnerstruktur_03.06.2018.docx
03_Business Development       06_Human Ressources            10_Legal Affairs        50_Tauschordner                            ~$läuterung der Ordnerstruktur_03.06.2018.docx
04_Marketing & Communication  07_Infrastructure & Equipment  11_Processes & Quality  51_Messdaten                               Scanner
nxp@livinglab-CELSIUS-W550power:~/data/dashboard/Karin_DB/25.08.20$

nxp@livinglab-CELSIUS-W550power:~$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
...
gvfsd-fuse on /run/user/1001/gvfs type fuse.gvfsd-fuse (rw,nosuid,nodev,relatime,user_id=1001,group_id=1001)
//10.5.10.5/Daten on /mnt/x type cifs (rw,relatime,vers=default,cache=strict,username=k.mayannavar,domain=livinglab,uid=0,noforceuid,gid=0,noforcegid,addr=10.5.10.5,file_mode=0755,dir_mode=0755,soft,nounix,serverino,mapposix,rsize=1048576,wsize=1048576,echo_interval=60,actimeo=1)

nxp@livinglab-CELSIUS-W550power:~$ sudo umount /mnt/x
nxp@livinglab-CELSIUS-W550power:~$

nxp@livinglab-CELSIUS-W550power:~$ ls /mnt/x/
nxp@livinglab-CELSIUS-W550power:~$
