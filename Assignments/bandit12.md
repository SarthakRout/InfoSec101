# Bandit Level 12 to 13 Writeup

Author: [Aarchie](https://github.com/aarchie-r)

Problem Page: [bandit12](https://overthewire.org/bandit/bandit12)

## List of Commands Used
```
ls - list files in a directory
cd - changes directory
mkdir - creates new directory
cp - copies content from one file to another
file - tells the type of file
cat - reads the content inside the file
xxd -r - revers the hexdump file to binary
mv - changes name and extension of the file
gunzip - decomprsses the gzip file
bzip2 -d - decompresses the compressed bzip2 files
tar -xvf - extracts the files compressed using tar

```

## Walkthrough

It is given that the data is stored in data.txt which is a hexdump of a file compressed repeatedly. To check it we used ls and got data.txt there. Now, it is given that we have to proceed by creating a directory under /tmp. Thus we, use mkdir to create a directory as-

mkdir /tmp/n

Thus new directory /tmp/n is created. As per hint given we need to copy the file data.txt in this newly created directory. For that, we used cp command.

cp data.txt /tmp/n


Furthur, we changed directory using "cd /tmp/n" and we are inside the new creater directory. Doing ls we checked the file we copied is present. Since, this file data.txt is hexdump file we converted it into binary using code -

xxd -r data.txt > w

This stores the converted file into new file named "w". To check the file type we used, "file w" and it gave the message as-

w: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix

This confirms the file is gzip compressed as the hint was given. Now, to decompress it we will use "gunzip" but before we need to change its extension to .gz as this command to work fine for that we used "mv" like-

mv w w.gz
gunzip w.gz

now w is decompressed. To check it again we used "file w" and got output as-

w: bzip2 compressed data, block size = 900k

Which shows this file "w" is now bzip2 compressed, which is what hint said the file is compressed repeadtedly. Now, to decompress it we first change the extension to bz2 (as the file is bzip2 comressed) using command "mv w w.bz2". Now the file is decompressed using command "bzip2 -d w.bz2". Then again used command "file w" to find the type of this decompressed file and got output as-

w: gzip compressed data, was "data4.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix

this says again the file is gzipped so again we used commands-
mv w w.gz
gunzip w
file w

now got output as-
w: POSIX tar archive (GNU)

which says the file is now compressed using tar. First, we changed extension to ".tar" using command "mv w w.tar" and furthur extracting the compressed file using-
tar -xvf w.tar

And got output as-
data5.bin

Now we checked the file type of data5.bin using command file and got output-
data5.bin: POSIX tar archive (GNU)

which says again the file data5.bin is tar compressed, thus we repeated same proceedure as before and got the extracted file as "data6.bin" and by checking file type we got-
data6.bin: bzip2 compressed data, block size = 900k

Thus data6.bin is bzip2 compressed for which we used same proceedure as before and after we checked the file type and got-
d6: POSIX tar archive (GNU)

Again we used same proceedure as we done before for tar compressed files and extracted the compressed file as- "data8.bin"
checking the file type of same we got -

data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix

again the file is gzip compressed we again repeated the same proceedure to decompress and furthur checked its file type and got output as-
d8: ASCII text

ASCII text means the file is now fully decompressed and readable. Thus using cat we read the content inside and got the password for next bandit level.


## Password
`8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

## Bash/Python script to automate the process
```
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ mkdir /tmp/n
bandit12@bandit:~$ cp -p data.txt /tmp/n
bandit12@bandit:~$ cd /tmp/n
bandit12@bandit:/tmp/n$ file data.txt
bandit12@bandit:/tmp/n$ xxd -r data.txt > w
bandit12@bandit:/tmp/n$ file w
w: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/n$ mv w w.gz
bandit12@bandit:/tmp/n$ gunzip w.gz
bandit12@bandit:/tmp/n$ file w
w: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/n$ mv w w.bz2
bandit12@bandit:/tmp/n$ bzip2 -d w.bz2
bandit12@bandit:/tmp/n$ file w
w: gzip compressed data, was "data4.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/n$ mv w w.gz
bandit12@bandit:/tmp/n$ gunzip w.gz
bandit12@bandit:/tmp/n$ file w
w: POSIX tar archive (GNU)
bandit12@bandit:/tmp/n$ mv w w.tar
bandit12@bandit:/tmp/n$ tar -xvf w.tar
data5.bin
bandit12@bandit:/tmp/n$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/n$ mv data5.bin d5.tar
bandit12@bandit:/tmp/n$ tar -xvf d5.tar
data6.bin
bandit12@bandit:/tmp/n$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/n$ mv data6.bin d6.bz2
bandit12@bandit:/tmp/n$ bzip2 -d d6.bz2
bandit12@bandit:/tmp/n$ file d6
d6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/n$ mv d6 d6.tar
bandit12@bandit:/tmp/n$ tar -xvf d6.tar
data8.bin
bandit12@bandit:/tmp/n$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/n$ mv data8.bin d8.gz
bandit12@bandit:/tmp/n$ gunzip d8.gz
bandit12@bandit:/tmp/n$ file d8
d8: ASCII text
bandit12@bandit:/tmp/n$ cat d8
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
--

```

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.


