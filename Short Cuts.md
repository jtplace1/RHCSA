 Short cuts

| **Terminal command line shortcuts** |                                             |
| ----------------------------------- | ------------------------------------------- |
| cntrl x + backspace                 | Delete everything what is before the cursor |
| cntrl a                             | Move back to the beginning of the line      |
| cntrl e                             | Move to the end of the line                 |
| cntrl l                             | Clear screen                                |



Useful commands 

diff
df --total -h
df -i

ls -lR

cp -vR
cp -i

mkdir -p

$PATH

tar -tf file.tar
tar -cjf file.bz2
tar -czf file.tar.gz

find . -empty -type f -exec rm -i {} \;
find ~ -name " *.tar.\* " -exec cp -v {} /home/kenny/test \;

xargs
find test/ -empty | xargs rm -f 

grep -l
grep -l "junk" test/file_* | xargs -I {} mv {} test/bak/

find ~ -name " *.sh " | xargs ls -al 
 
killall
tmux terminal manager
nohup
jobs
fg
bg
File GLobbing
ps -o pid,nice,cmd,user
nice
renice

man 7 regex


VIm--
crt+v visual mode
shift a
gg (press g key twice)


