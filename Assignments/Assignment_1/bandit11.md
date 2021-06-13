# Bandit Level 11 to 12 Writeup


Author: [Naman Singla](https://github.com/nsingla20)

Problem Page: [bandit11](https://overthewire.org/wargames/bandit/bandit12.html)

## List of Commands Used
```
sshpass - For Authentucating ssh with scripts
ssh	- To login to remote server using user id
clear	- to clear the current screen for cleaner output
tr	- For rotating characters
exit	- To close the connection to ssh server
```

## Walkthrough
Just came to know about command base64 given in list on website. Then googled it to check its use.

## Password
`5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu`

## Bash/Python script to automate the process
```
#!/bin/bash
sshpass -p "IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR" ssh -tt -o StrictHostKeyChecking=no bandit11@bandit.labs.overthewire.org -p 2220 <<HERE
clear
cat data.txt | tr '[a-z]' '[n-za-m]' | tr '[A-Z]' '[N-ZA-M]'
exit
HERE

```

## Suggested modifications [Optional]
What can you do to make this level more difficult. The inherent idea should be similar.
