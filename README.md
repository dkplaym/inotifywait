e47995dc39da897d744530ed545a0d5c  inotifywait




1227652366d5cc0f3d66c43e9ff3da8c  libinotifytools.so.0



sudo cat    /proc/sys/fs/inotify/max_user_watches  ;
sudo sh -c  "echo 104857600  >  /proc/sys/fs/inotify/max_user_watches"  ;
sudo  cat    /proc/sys/fs/inotify/max_user_watches  ;

LD_LIBRARY_PATH=./ ./inotifywait  -mrq --timefmt '%d/%m/%y/%H:%M' --format '%T %w %f  %e ' -e modify,delete,create  --exclude '^/dev/'   /



dk@ubuntu:~/inotifywait$ LD_LIBRARY_PATH=./ ./inotifywait  -mrq --timefmt '%d/%m/%y/%H:%M' --format '%T %w %f  %e ' -e modify,delete,create  --exclude '^/dev/|^/run/'   /



LD_LIBRARY_PATH=./ ./inotifywait  -mrq --timefmt '%d/%m/%y/%H:%M' --format '%T %w %f  %e ' -e modify,delete,create,access,moved,delete,delete_self,unmount  --exclude '^/dev/|^/run/'   /   -o /dev/shm/noitfy.txt &  tail -f /dev/shm/noitfy.txt


LD_LIBRARY_PATH=./ ./inotifywait  -mrq --timefmt '%d/%m/%y/%H:%M' --format '%T %w %f  %e ' -e modify,delete,create,attrib,delete_self,unmount  --exclude '^/dev/|^/run/'   /   -o /dev/shm/noitfy.txt &  tail -f /dev/shm/noitfy.txt & tail -f /dev/shm/noitfy.txt





sudo mount -t tmpfs shmfs -o size=1500M /dev/shm




