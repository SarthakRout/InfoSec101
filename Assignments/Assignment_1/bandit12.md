# Bandit Level 12 to 13 Writeup



Author: [Sarthak Goyal](https://github.com/sarthak759) 

Problem Page: [bandit11](https://overthewire.org/bandit/bandit12) 

## List of Commands Used
```
ls - list files in a directory
mkdir - make a new directory
cp - copy a file or directory to desired location
cd - move to another directory
xxd - make a hexdum of a file 
xxd -r - reverse hexdump
mv - rename a file
gzip - compress or expands a file
gzip -d - decompress the file
bzip2 - block-sorting file compressor
bzip2 -d - decompress the file
tar - an archiving utility
cat - read the contents of a file
file - returns the type of a file
```

## Walkthrough
We dont have overwrtie permissions in the current directory so first copy the file in /tmp/somedirectory the file is hexdum of a file so I revered the hexdump using xxd -r this returned the binary file data.txt. Then I checked the type of the file using file command, if it says gzip compressed file, rename the file to add gz extension using the mv command and then decompress it using gzip -d, similarly for bzip2 compressed files I added the extention bz2 and then decompressed it using bzip2 -d and for tar archive files added the extension tar and extract it using tar xvf. Repeat the process until the file type is ASCII

## Password
`8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL`

## Bash/Python script to automate the process
```
mkdir /tmp/sart123
cp data.txt /tmp/sart123
cd /tmp/sart123
xxd -r data.txt
mv data data.gz
gzip -d data.gz
mv data data.bz2
bzip2 -d data.bz2
mv data data.gz
gzip -d data.gz
mv data data.tar
tar xvf data.tar
mv data5.bin data5.tar
tar xvf data5.tar
mv data6.bin data.bz2
bzip2 -d data.bz2
mv data dat.tar
tar xvf dat.tar
mv data8.bin data.gz
gzip -d data.gz
cat data
```
## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.