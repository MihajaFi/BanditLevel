

                            ----------------Take a password-------------------

BANDIT

Niveau 0
ssh bandit0@bandit.labs.overthewire.org -p 2220
mot de passe: bandit0

Niveau 0 → Niveau 1
ssh bandit0@bandit.labs.overthewire.org -p 2220
bandit0@bandit:~$ ls -alps
bandit0@bandit:~$ cat readme mot de passe : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$ exit

Niveau 1 → Niveau 2
ssh bandit1@bandit.labs.overthewire.org -p 2220
bandit1@bandit:~$ ls -alps
bandit1@bandit:~$ cat ./- mot de passe : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ exit


Niveau 2 → Niveau 3
ssh bandit2@bandit.labs.overthewire.org -p 2220
bandit2@bandit:~$ ls -alps
spaces in this filename

bandit2@bandit:~$ cat ‘spaces in this filename’
mot de passe : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$ exit
Niveau 3→ Niveau 4
ssh bandit3@bandit.labs.overthewire.org -p 2220
bandit3@bandit:~$ ls
inhere

bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -a
… .hidden

bandit3@bandit:~/inhere$ cat .hidden
mot de passe : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~$ exit

Niveau 4 → Niveau 5
ssh bandit4@bandit.labs.overthewire.org -p 2220
bandit4@bandit:~$ ls
inhere

bandit4@bandit:~$ file inhere/*
bandit4@bandit:~$ cat inhere/-file07
mot de passe : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

bandit4@bandit:~$ exit
Niveau 5 → Niveau 6

bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
bandit5@bandit:~/inhere$ find -maxdepth 2 -type f -size 1033c
/maybehere07/.file2

bandit5@bandit:~/inhere$ cat ./maybehere07/file2
cat: ./maybehere07/file2: No such file or directory

bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
mot de passe : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

Niveau 6 → Niveau 7
bandit6@bandit:~$ pwd
‘/home/bandit6’

bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password

bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
mot de passe : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
Niveau 7 → Niveau 8
bandit7@bandit:~$ ls v data.txt
bandit7@bandit:~$ nano data.txt

search : millionth
mot de passe :TESKZC0XvTetK0S9xNwm25STk5iWrBvP
Niveau 8 → Niveau 9
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
Niveau 9 → Niveau 10
bandit9@bandit:~$ strings data.txt
==========
mot de passe : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
Niveau 10 → Niveau 11
bandit10@bandit:~$ ls
data.txt

bandit10@bandit:~$ cat data.txt v VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ base64 -d data.txt
The password is : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
Niveau 11 → Niveau 12
bandit11@bandit:~$ ls
data.txt

bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi

bandit11@bandit:~$ echo | cat data.txt | tr ‘A-Za-z’ ‘N-ZA-Mn-za-m’
The password is : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
Niveau 12 → Niveau 13
bandit12@bandit:mkdir /tmp/gxuvimr$
bandit12@bandit:cd /tmp/gxuvimr$
bandit12@bandit:/tmp/gxuvimr$ xxd -r data.txt > data
bandit12@bandit:/tmp/gxuvimr$ ls
data data.txt

bandit12@bandit:/tmp/gxuvimr$ file data
data: gzip compressed data, was “data2.bin”, last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix

bandit12@bandit:/tmp/gxuvimr$ mv data data.gz
bandit12@bandit:/tmp/gxuvimr$ gzip -d data.gz
bandit12@bandit:/tmp/gxuvimr$ file data
data: bzip2 compressed data, block size = 900k

bandit12@bandit:/tmp/gxuvimr$ mv data data.bz2
bandit12@bandit:/tmp/gxuvimr$ bzip2 -d data.bz2
bandit12@bandit:/tmp/gxuvimr$ file data
data: gzip compressed data, was “data4.bin”, last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix

bandit12@bandit:/tmp/gxuvimr$ mv data data.gz
bandit12@bandit:/tmp/gxuvimr$ gzip -d data.gz
bandit12@bandit:/tmp/gxuvimr$ file data
data: POSIX tar archive (GNU)

bandit12@bandit:/tmp/gxuvimr$ mv data data.tar
bandit12@bandit:/tmp/gxuvimr$ tar -xvf data.tar
data5.bin

bandit12@bandit:/tmp/gxuvimr$ ls
data5.bin data.tar data.txt

bandit12@bandit:/tmp/gxuvimr$ file data5.bin
data5.bin: POSIX tar archive (GNU)

bandit12@bandit:/tmp/gxuvimr$ mv data5.bin data5.tar
bandit12@bandit:/tmp/gxuvimr$ tar -xvf data5.tar
data6.bin

bandit12@bandit:/tmp/gxuvimr$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k

bandit12@bandit:/tmp/gxuvimr$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/gxuvimr$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/gxuvimr$ file data6
data6: POSIX tar archive (GNU)

bandit12@bandit:/tmp/gxuvimr$ mv data6 data6.tar
bandit12@bandit:/tmp/gxuvimr$ tar -xvf data6.tar
data8.bin

bandit12@bandit:/tmp/gxuvimr$ file data8.bin
data8.bin: gzip compressed data, was “data9.bin”, last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix

bandit12@bandit:/tmp/gxuvimr$ mv data8.bin data8.gz
bandit12@bandit:/tmp/gxuvimr$ gzip -d data8.gz
bandit12@bandit:/tmp/gxuvimr$ file data8
data8: ASCII text

bandit12@bandit:/tmp/gxuvimr$ cat data8
The password is : wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
Niveau 13 → Niveau 14
bandit13@bandit:~$ ls
sshkey.private ssh -i sshkey.private -p 2220 bandit14@localhost

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
mot de passe :fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Niveau 14 → Niveau 15
bandit14@bandit:~$ nc localhost 30000 < /etc/bandit_pass/bandit14 Correct!
mot de passe : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Niveau 15→ Niveau 16
bandit15@bandit:~$ openssl s_client -connect localhost:30001 -quiet < /etc/bandit_pass/bandit15
Can’t use SSL_get_servername depth=0 CN = localhost verify error:num=18:self-signed certificate verify return:1 depth=0 CN = localhost verify error:num=10:certificate has expired notAfter=May 5 11:21:25 2023 GMT verify return:1 depth=0 CN = localhost notAfter=May 5 11:21:25 2023 GMT verify return:1 Correct!

mot de passe :JQttfApK4SeyHwDlI9SXGR50qclOAil1
Niveau 16 → Niveau 17
bandit16@bandit:~$ nmap -sV -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-05-06 19:52 UTC Stats: 0:01:07 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan Service scan Timing: About 80.00% done; ETC: 19:54 (0:00:17 remaining) Nmap scan report for localhost (127.0.0.1) Host is up (0.00012s latency). Not shown: 996 closed ports PORT STATE SERVICE VERSION 31046/tcp open echo 31518/tcp open ssl/echo 31691/tcp open echo 31790/tcp open ssl/unknown 31960/tcp open echo Service detection performed. Please report any incorrect results at https://nmap.org/submit/ . Nmap done: 1 IP address (1 host up) scanned in 98.11 seconds

bandit16@bandit:~$ openssl s_client -connect localhost:31790 -quiet < /etc/bandit_pass/bandit16
Can’t use SSL_get_servername depth=0 CN = localhost verify error:num=18:self-signed certificate verify return:1 depth=0 CN = localhost verify error:num=10:certificate has expired notAfter=May 5 11:21:24 2023 GMT verify return:1 depth=0 CN = localhost notAfter=May 5 11:21:24 2023 GMT verify return:1 Correct! -----BEGIN RSA PRIVATE KEY----- – -----END RSA PRIVATE KEY-----

bandit16@bandit:~$ PRIVATE_KEY=$(mktemp)
bandit16@bandit:~$ openssl s_client
-connect localhost:31790
-quiet < /etc/bandit_pass/bandit16 > $PRIVATE_KEY Can’t use SSL_get_servername depth=0 CN = localhost verify error:num=18:self-signed certificate verify return:1 depth=0 CN = localhost verify error:num=10:certificate has expired notAfter=May 5 11:21:24 2023 GMT verify return:1 depth=0 CN = localhost notAfter=May 5 11:21:24 2023 GMT verify return:1 bandit16@bandit:~$ ssh -i $PRIVATE_KEY -p 2220 bandit17@localhost

connect : bandit17@bandit:~$
Niveau 17 → Niveau 18
bandit17@bandit:~$ diff passwords.old passwords.new
42c42 < glZreTEH1V3cGKL6g4conYqZqaEj0mte Good password : hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

Niveau 18 → Niveau 19
Byebye ! Connection to bandit.labs.overthewire.org closed. ssh -p 2220 bandit18@bandit.labs.overthewire.org cat readme bandit18@bandit.labs.overthewire.org's password:

mot de passe :awhqfNnAbc1naukrpqDYcF95h7HoMTrC
Niveau 19 → Niveau 20
bandit19@bandit:~$ ls bandit20-do
bandit19@bandit:~$ ./bandit20-do
Run a command as another user. Example: ./bandit20-do id

bandit19@bandit:~$ id uid=11019(bandit19) gid=11019(bandit19) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do id uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
mot de passe :VxCazJaVykI6W36BkBU0mJTCM8rR95XT

                    --------------------En cours----------------------------