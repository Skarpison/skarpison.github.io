---
layout: default
title: Encrypting Files
---
If you want to comment about something on this page, [go here and create an issue please.](https://github.com/Skarpison/skarpison.github.io)

[Go back to the beginning of the site](/)

## Intro

Encrypting files is good to keep things from seeing what is inside the files. This is a quick introduction on how to encrypt and then decrypt a file. This will be using  symmetric encription which only requires a password to encrypt and decrypt a file.

## Steps to encrypt a file

1. Install [gnupg](https://gnupg.org/)(GNU Privacy Guard) with: `sudo pacman -S gnupg`
2. Go to a safe directory and do the following
   1. Open a new file the name 'junk_file' in the nano editor with: `nano junk_file`
   2. Type some stuff into the file
   3. Ctrl+O and 'enter' to save(aka "write out") the file(You can see that command in help of bottom of screen)
   4. Ctrl+X to close nano
3. Enrypt the file with `gpg --symmetric --cipher-algo AES256 junk_file`
   1. gpg = GnuPG program you installed in step 1
   2. --symmetric = parameter saying to use symmetric encryption
   3. --cipher-algo AES256 = parameter saying what encryption algorith to use.
   4. junk_file = path/name of the file to be encrypted
4. Create a password when prompted
5. A file is created in the same directory as the original file with a .pgp extension. So there will now be a junk_file.pgp file. Use `cat junk_file.gpg` to view the contents of the encrypted file
7. Delete the original file with `shred -u junk_file`
   1. shred = overwrites the file with random data
   2. -u = "unlinks" the file by deleting it
   3. junk_file = path/name of the file to be shred

## Steps to decrypt a file

1. Decrypt the file with `gpg --decrypt junk_file.gpg > whatever-new-file-name.txxt`

[Go back to the beginning of the site](/)
