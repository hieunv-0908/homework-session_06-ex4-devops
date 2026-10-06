
Admin@Admin MINGW64 ~
$ ssh zeno-one@127.0.0.1 -p 2222
Welcome to Ubuntu 22.04.5 LTS (GNU/Linux 5.15.0-198-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Tue Oct  6 06:33:15 PM UTC 2026

  System load:             0.13
  Usage of /:              36.9% of 9.75GB
  Memory usage:            6%
  Swap usage:              0%
  Processes:               135
  Users logged in:         1
  IPv4 address for enp0s3: 10.0.2.15
  IPv6 address for enp0s3: fd17:625c:f037:2:a00:27ff:fedb:ff3c

 * Canonical Workshop gives developers fast, composable, reproducible, and
   secure developer environments that are perfect for agentic workflows.

   https://ubuntu.com/workshop

Expanded Security Maintenance for Applications is not enabled.

70 updates can be applied immediately.
3 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status

New release '24.04.5 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Tue Oct  6 18:25:32 2026 from 10.0.2.2
zeno-one@my-dev-ops-edu:~$ mkdir -p homework/session_06/ex4
zeno-one@my-dev-ops-edu:~$ cd homework/session_06/ex4
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ cat << 'EOF' > loop-monitor.sh
#!/bin/bash
while true; do
    echo "System time: $(date)" >> /tmp/monitor.log
    sleep 5
done
EOF
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ chmod +x loop-monitor.sh
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ nohup ./loop-monitor.sh > /dev/null 2>&1 &
[1] 2370
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ ps aux | grep loop-monitor.sh
zeno-one    2370  0.0  0.0   7372  3600 pts/0    S    18:36   0:00 /bin/bash ./loop-monitor.sh
zeno-one    2378  0.0  0.0   6620  2236 pts/0    S+   18:36   0:00 grep --color=auto loop-monitor.sh
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ ps aux | grep loop-monitor.sh
zeno-one    2370  0.0  0.0   7372  3604 pts/0    S    18:36   0:00 /bin/bash ./loop-monitor.sh
zeno-one    2382  0.0  0.0   6620  2420 pts/0    S+   18:36   0:00 grep --color=auto loop-monitor.sh
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ ps aux | grep loop-monitor.sh
zeno-one    2370  0.0  0.0   7372  3608 pts/0    S    18:36   0:00 /bin/bash ./loop-monitor.sh
zeno-one    2388  0.0  0.0   6620  2252 pts/0    S+   18:36   0:00 grep --color=auto loop-monitor.sh
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ ps aux | grep loop-monitor.sh
zeno-one    2370  0.0  0.0   7372  3608 pts/0    S    18:36   0:00 /bin/bash ./loop-monitor.sh
zeno-one    2392  0.0  0.0   6620  2304 pts/0    S+   18:36   0:00 grep --color=auto loop-monitor.sh
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ pgrep -f loop-monitor.sh
2370
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ tail -f /tmp/monitor.log
System time: Tue Oct  6 06:36:12 PM UTC 2026
System time: Tue Oct  6 06:36:17 PM UTC 2026
System time: Tue Oct  6 06:36:22 PM UTC 2026
System time: Tue Oct  6 06:36:27 PM UTC 2026
System time: Tue Oct  6 06:36:32 PM UTC 2026
System time: Tue Oct  6 06:36:37 PM UTC 2026
System time: Tue Oct  6 06:36:42 PM UTC 2026
System time: Tue Oct  6 06:36:47 PM UTC 2026
System time: Tue Oct  6 06:36:52 PM UTC 2026
System time: Tue Oct  6 06:36:57 PM UTC 2026
System time: Tue Oct  6 06:37:03 PM UTC 2026
System time: Tue Oct  6 06:37:08 PM UTC 2026
kill -15 <PID_CUA_TIEN_TRINH>
System time: Tue Oct  6 06:37:13 PM UTC 2026
System time: Tue Oct  6 06:37:19 PM UTC 2026

System time: Tue Oct  6 06:37:24 PM UTC 2026
^C
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ kill -15 <PID_CUA_TIEN_TRINH>
-bash: syntax error near unexpected token `newline'
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ kill -15 2370
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ tail -f /tmp/monitor.log
System time: Tue Oct  6 06:37:03 PM UTC 2026
System time: Tue Oct  6 06:37:08 PM UTC 2026
System time: Tue Oct  6 06:37:13 PM UTC 2026
System time: Tue Oct  6 06:37:19 PM UTC 2026
System time: Tue Oct  6 06:37:24 PM UTC 2026
System time: Tue Oct  6 06:37:29 PM UTC 2026
System time: Tue Oct  6 06:37:34 PM UTC 2026
System time: Tue Oct  6 06:37:39 PM UTC 2026
System time: Tue Oct  6 06:37:44 PM UTC 2026
System time: Tue Oct  6 06:37:49 PM UTC 2026
^C
[1]+  Terminated              nohup ./loop-monitor.sh > /dev/null 2>&1
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ tail -f /tmp/monitor.log
System time: Tue Oct  6 06:37:03 PM UTC 2026
System time: Tue Oct  6 06:37:08 PM UTC 2026
System time: Tue Oct  6 06:37:13 PM UTC 2026
System time: Tue Oct  6 06:37:19 PM UTC 2026
System time: Tue Oct  6 06:37:24 PM UTC 2026
System time: Tue Oct  6 06:37:29 PM UTC 2026
System time: Tue Oct  6 06:37:34 PM UTC 2026
System time: Tue Oct  6 06:37:39 PM UTC 2026
System time: Tue Oct  6 06:37:44 PM UTC 2026
System time: Tue Oct  6 06:37:49 PM UTC 2026
^C
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$ ps aux | grep loop-monitor.sh
zeno-one    2431  0.0  0.0   6620  2224 pts/0    S+   18:38   0:00 grep --color=auto loop-monitor.sh
zeno-one@my-dev-ops-edu:~/homework/session_06/ex4$
