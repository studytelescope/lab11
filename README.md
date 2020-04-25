## Laboratory work XI

Данная лабораторная работа посвещена изучению процесса создания сеансов совместной разработки с использованием инструмента **ngrok**

```sh
$ open https://ngrok.com/
```

## Tasks

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```sh
$ cd ~
$ mkdir install
$ mkdir tmp
$ export HOME_PREFIX=`pwd`/install
$ echo $HOME_PREFIX
/home/johnsnow/install

$ export USERNAME=`whoami`
```

```sh
$ cd tmp
```

```sh
$ wget https://github.com/libevent/libevent/releases/download/release-2.1.8-stable/libevent-2.1.8-stable.tar.gz
--2020-04-23 10:56:27--  https://github.com/libevent/libevent/releases/download/release-2.1.8-stable/libevent-2.1.8-stable.tar.gz
Resolving github.com (github.com)... 140.82.118.4
Connecting to github.com (github.com)|140.82.118.4|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://github-production-release-asset-2e65be.s3.amazonaws.com/1856976/f9ea6922-e66b-11e6-9f5c-722c00daa657?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20200423%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20200423T075628Z&X-Amz-Expires=300&X-Amz-Signature=5a1caa42246ffa8dd8698da2ac2c8d89fb9b4ca1ee43c54c13d45d06f49acc3c&X-Amz-SignedHeaders=host&actor_id=0&repo_id=1856976&response-content-disposition=attachment%3B%20filename%3Dlibevent-2.1.8-stable.tar.gz&response-content-type=application%2Foctet-stream [following]
--2020-04-23 10:56:28--  https://github-production-release-asset-2e65be.s3.amazonaws.com/1856976/f9ea6922-e66b-11e6-9f5c-722c00daa657?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20200423%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20200423T075628Z&X-Amz-Expires=300&X-Amz-Signature=5a1caa42246ffa8dd8698da2ac2c8d89fb9b4ca1ee43c54c13d45d06f49acc3c&X-Amz-SignedHeaders=host&actor_id=0&repo_id=1856976&response-content-disposition=attachment%3B%20filename%3Dlibevent-2.1.8-stable.tar.gz&response-content-type=application%2Foctet-stream
Resolving github-production-release-asset-2e65be.s3.amazonaws.com (github-production-release-asset-2e65be.s3.amazonaws.com)... 52.216.20.195
Connecting to github-production-release-asset-2e65be.s3.amazonaws.com (github-production-release-asset-2e65be.s3.amazonaws.com)|52.216.20.195|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1026485 (1002K) [application/octet-stream]
Saving to: ‘libevent-2.1.8-stable.tar.gz’

libevent-2.1.8-stable.tar.gz          100%[=======================================================================>]   1002K   449KB/s    in 2,2s    

2020-04-23 10:56:31 (449 KB/s) - ‘libevent-2.1.8-stable.tar.gz’ saved [1026485/1026485]

$ tar -xvzf libevent-2.1.8-stable.tar.gz
libevent-2.1.8-stable/
libevent-2.1.8-stable/util-internal.h
libevent-2.1.8-stable/evmap.c
libevent-2.1.8-stable/epolltable-internal.h
libevent-2.1.8-stable/mm-internal.h
libevent-2.1.8-stable/libevent.pc.in
libevent-2.1.8-stable/http.c
libevent-2.1.8-stable/include/
libevent-2.1.8-stable/include/event.h
libevent-2.1.8-stable/include/evrpc.h
libevent-2.1.8-stable/include/event2/
libevent-2.1.8-stable/include/event2/tag_compat.h
libevent-2.1.8-stable/include/event2/event.h
libevent-2.1.8-stable/include/event2/rpc_struct.h
libevent-2.1.8-stable/include/event2/dns.h
libevent-2.1.8-stable/include/event2/rpc_compat.h
libevent-2.1.8-stable/include/event2/http_compat.h
libevent-2.1.8-stable/include/event2/util.h
libevent-2.1.8-stable/include/event2/event_struct.h
libevent-2.1.8-stable/include/event2/rpc.h
libevent-2.1.8-stable/include/event2/http_struct.h
libevent-2.1.8-stable/include/event2/http.h
libevent-2.1.8-stable/include/event2/tag.h
libevent-2.1.8-stable/include/event2/buffer_compat.h
libevent-2.1.8-stable/include/event2/dns_compat.h
libevent-2.1.8-stable/include/event2/bufferevent_ssl.h
libevent-2.1.8-stable/include/event2/listener.h
libevent-2.1.8-stable/include/event2/keyvalq_struct.h
libevent-2.1.8-stable/include/event2/thread.h
libevent-2.1.8-stable/include/event2/bufferevent_struct.h
libevent-2.1.8-stable/include/event2/bufferevent_compat.h
libevent-2.1.8-stable/include/event2/dns_struct.h
libevent-2.1.8-stable/include/event2/bufferevent.h
libevent-2.1.8-stable/include/event2/buffer.h
libevent-2.1.8-stable/include/event2/visibility.h
libevent-2.1.8-stable/include/event2/event_compat.h
libevent-2.1.8-stable/include/evdns.h
libevent-2.1.8-stable/include/include.am
libevent-2.1.8-stable/include/evhttp.h

$ cd libevent-2.1.8-stable
$ ./configure --prefix=${HOME_PREFIX}
checking for a BSD-compatible install... /usr/bin/install -c
checking whether build environment is sane... yes
checking for a thread-safe mkdir -p... /bin/mkdir -p
checking for gawk... gawk

...

config.status: executing depfiles commands
config.status: executing libtool commands

$ make && make install
Libraries have been installed in:
   /home/johnsnow/install/lib

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the '-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the 'LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the 'LD_RUN_PATH' environment variable
     during linking
   - use the '-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to '/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------
 /bin/mkdir -p '/home/johnsnow/install/include'
 /usr/bin/install -c -m 644 include/evdns.h include/event.h include/evhttp.h include/evrpc.h include/evutil.h '/home/johnsnow/install/include'
 /bin/mkdir -p '/home/johnsnow/install/include/event2'
 /usr/bin/install -c -m 644 include/event2/buffer.h include/event2/buffer_compat.h include/event2/bufferevent.h include/event2/bufferevent_compat.h include/event2/bufferevent_ssl.h include/event2/bufferevent_struct.h include/event2/dns.h include/event2/dns_compat.h include/event2/dns_struct.h include/event2/event.h include/event2/event_compat.h include/event2/event_struct.h include/event2/http.h include/event2/http_compat.h include/event2/http_struct.h include/event2/keyvalq_struct.h include/event2/listener.h include/event2/rpc.h include/event2/rpc_compat.h include/event2/rpc_struct.h include/event2/tag.h include/event2/tag_compat.h include/event2/thread.h include/event2/util.h include/event2/visibility.h '/home/johnsnow/install/include/event2'
 /bin/mkdir -p '/home/johnsnow/install/include/event2'
 /usr/bin/install -c -m 644 include/event2/event-config.h '/home/johnsnow/install/include/event2'
 /bin/mkdir -p '/home/johnsnow/install/lib/pkgconfig'
 /usr/bin/install -c -m 644 libevent.pc libevent_core.pc libevent_extra.pc libevent_pthreads.pc '/home/johnsnow/install/lib/pkgconfig'
make[2]: Leaving directory '/home/johnsnow/tmp/libevent-2.1.8-stable'
make[1]: Leaving directory '/home/johnsnow/tmp/libevent-2.1.8-stable'

$ cd ..
```

```sh
$ wget http://invisible-island.net/datafiles/release/ncurses.tar.gz
--2020-04-23 11:05:57--  http://invisible-island.net/datafiles/release/ncurses.tar.gz
Resolving invisible-island.net (invisible-island.net)... 192.124.249.12
Connecting to invisible-island.net (invisible-island.net)|192.124.249.12|:80... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://invisible-island.net/datafiles/release/ncurses.tar.gz [following]
--2020-04-23 11:05:58--  https://invisible-island.net/datafiles/release/ncurses.tar.gz
Connecting to invisible-island.net (invisible-island.net)|192.124.249.12|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3425862 (3,3M) [application/x-gzip]
Saving to: ‘ncurses.tar.gz’

ncurses.tar.gz                        100%[=======================================================================>]   3,27M  2,26MB/s    in 1,4s    

2020-04-23 11:05:59 (2,26 MB/s) - ‘ncurses.tar.gz’ saved [3425862/3425862]

$ tar -xvzf ncurses.tar.gz
ncurses-6.2/
ncurses-6.2/aclocal.m4
ncurses-6.2/Ada95/
ncurses-6.2/ANNOUNCE
ncurses-6.2/announce.html.in
ncurses-6.2/AUTHORS
ncurses-6.2/c++/
ncurses-6.2/config.guess
ncurses-6.2/config.sub
ncurses-6.2/configure
ncurses-6.2/configure.in
ncurses-6.2/convert_configure.pl
ncurses-6.2/COPYING
ncurses-6.2/dist.mk
ncurses-6.2/doc/

...

ncurses-6.2/Ada95/samples/status.adb
ncurses-6.2/Ada95/samples/sample-form_demo.adb
ncurses-6.2/Ada95/samples/ncurses2-flushinp_test.adb
ncurses-6.2/Ada95/samples/sample-curses_demo-attributes.ads
ncurses-6.2/Ada95/samples/README
ncurses-6.2/Ada95/samples/sample-form_demo-handler.ads
ncurses-6.2/Ada95/samples/ncurses2-demo_forms.adb
ncurses-6.2/Ada95/samples/ncurses2-getch_test.adb
ncurses-6.2/Ada95/samples/sample-my_field_type.ads
ncurses-6.2/Ada95/samples/sample-menu_demo-handler.adb
ncurses-6.2/Ada95/samples/sample-menu_demo.adb
ncurses-6.2/Ada95/samples/ncurses2-m.adb
ncurses-6.2/Ada95/samples/sample-my_field_type.adb
ncurses-6.2/Ada95/samples/ncurses2-trace_set.adb
ncurses-6.2/Ada95/samples/tour.adb

$ cd ncurses-5.9
used 6.2
$ ./configure --prefix=${HOME_PREFIX}
** Configuration summary for NCURSES 6.2 20200212:

       extended funcs: yes
       xterm terminfo: xterm-new

        bin directory: /home/johnsnow/install/bin
        lib directory: /home/johnsnow/install/lib
    include directory: /home/johnsnow/install/include/ncurses
        man directory: /home/johnsnow/install/share/man
   terminfo directory: /home/johnsnow/install/share/terminfo

** Include-directory is not in a standard location

$ make && make install
cd man && make DESTDIR="" RPATH_LIST="/home/johnsnow/install/lib" all
make[1]: Entering directory '/home/johnsnow/tmp/ncurses-6.2/man'
/bin/sh ./MKterminfo.sh ./terminfo.head ./../include/Caps ./../include/Caps-ncurses ./terminfo.tail >terminfo.5
make[1]: Leaving directory '/home/johnsnow/tmp/ncurses-6.2/man'
cd include && make DESTDIR="" RPATH_LIST="/home/johnsnow/install/lib" all
make[1]: Entering directory '/home/johnsnow/tmp/ncurses-6.2/include'
cat curses.head >curses.h
AWK=mawk /bin/sh ./MKkey_defs.sh ./Caps ./Caps-ncurses >>curses.h
/bin/sh -c 'if test "chtype" = s"cchar_t" ; then cat ./curses.wide >>curses.h ; fi'
cat ./curses.tail >>curses.h
/bin/sh ./MKhashsize.sh ./Caps ./Caps-ncurses >hashsize.h
AWK=mawk /bin/sh ./MKncurses_def.sh ./ncurses_defs >ncurses_def.h
AWK=mawk /bin/sh ./MKparametrized.sh ./Caps ./Caps-ncurses >parametrized.h
touch config.h
mawk -f MKterm.h.awk ./Caps ./Caps-ncurses > term.h
/bin/sh ./edit_cfg.sh ../include/ncurses_cfg.h term.h
** edit: HAVE_TCGETATTR 1

...

installing ./cursesf.h in /home/johnsnow/install/include/ncurses
installing ./cursesm.h in /home/johnsnow/install/include/ncurses
installing ./cursesp.h in /home/johnsnow/install/include/ncurses
installing ./cursesw.h in /home/johnsnow/install/include/ncurses
installing ./cursslk.h in /home/johnsnow/install/include/ncurses
installing etip.h in /home/johnsnow/install/include/ncurses
make[1]: Leaving directory '/home/johnsnow/tmp/ncurses-6.2/c++'
$ cd ..
```


```sh
$ wget https://github.com/tmux/tmux/releases/download/2.5/tmux-2.5.tar.gz
--2020-04-23 11:43:14--  https://github.com/tmux/tmux/releases/download/2.5/tmux-2.5.tar.gz
Resolving github.com (github.com)... 140.82.118.3
Connecting to github.com (github.com)|140.82.118.3|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://github-production-release-asset-2e65be.s3.amazonaws.com/36836475/2c975d56-4447-11e7-9b0d-546f71b509fc?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20200423%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20200423T084218Z&X-Amz-Expires=300&X-Amz-Signature=bd51e3f9d53ca38a3d01049c9a066a5382c1770022b7da6187b9bc2a98a73a01&X-Amz-SignedHeaders=host&actor_id=0&repo_id=36836475&response-content-disposition=attachment%3B%20filename%3Dtmux-2.5.tar.gz&response-content-type=application%2Foctet-stream [following]
--2020-04-23 11:43:14--  https://github-production-release-asset-2e65be.s3.amazonaws.com/36836475/2c975d56-4447-11e7-9b0d-546f71b509fc?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20200423%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20200423T084218Z&X-Amz-Expires=300&X-Amz-Signature=bd51e3f9d53ca38a3d01049c9a066a5382c1770022b7da6187b9bc2a98a73a01&X-Amz-SignedHeaders=host&actor_id=0&repo_id=36836475&response-content-disposition=attachment%3B%20filename%3Dtmux-2.5.tar.gz&response-content-type=application%2Foctet-stream
Resolving github-production-release-asset-2e65be.s3.amazonaws.com (github-production-release-asset-2e65be.s3.amazonaws.com)... 52.216.137.60
Connecting to github-production-release-asset-2e65be.s3.amazonaws.com (github-production-release-asset-2e65be.s3.amazonaws.com)|52.216.137.60|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 475717 (465K) [application/octet-stream]
Saving to: ‘tmux-2.5.tar.gz’

tmux-2.5.tar.gz                       100%[=======================================================================>] 464,57K   725KB/s    in 0,6s    

2020-04-23 11:43:16 (725 KB/s) - ‘tmux-2.5.tar.gz’ saved [475717/475717]

$ tar -xvzf tmux-2.5.tar.gz
$ cd tmux-2.5
$ ./configure --prefix=${HOME_PREFIX} CFLAGS="-I${HOME_PREFIX}/include -I${HOME_PREFIX}/include/ncurses" LDFLAGS="-L${HOME_PREFIX}/lib"
checking for a BSD-compatible install... /usr/bin/install -c
checking whether build environment is sane... yes
checking for a thread-safe mkdir -p... /bin/mkdir -p
checking for gawk... gawk
checking whether make sets $(MAKE)... yes
checking whether make supports nested variables... yes
checking build system type... x86_64-pc-linux-gnu
checking host system type... x86_64-pc-linux-gnu
checking for gcc... gcc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out

...

checking whether F_CLOSEM is declared... no
checking for /proc/$$... yes
checking platform... linux
checking that generated files are newer than configure... done
configure: creating ./config.status
config.status: creating Makefile
config.status: executing depfiles commands

$ make && make install
$ cd ..
```

```sh
$ wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip
--2020-04-23 12:19:16--  https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip
Resolving bin.equinox.io (bin.equinox.io)... 52.73.195.55, 3.228.72.85, 3.227.142.238, ...
Connecting to bin.equinox.io (bin.equinox.io)|52.73.195.55|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13773305 (13M) [application/octet-stream]
Saving to: ‘ngrok-stable-linux-amd64.zip’

ngrok-stable-linux-amd64.zip          100%[=======================================================================>]  13,13M  1,87MB/s    in 9,6s    

2020-04-23 12:19:27 (1,37 MB/s) - ‘ngrok-stable-linux-amd64.zip’ saved [13773305/13773305]
$ unzip ngrok-stable-linux-amd64.zip
Archive:  ngrok-stable-linux-amd64.zip
  inflating: ngrok  
$ mv ngrok ${HOME_PREFIX}/bin
```

```sh
$ export LD_LIBRARY_PATH=${HOME_PREFIX}/lib
$ export PATH="${HOME_PREFIX}/bin:${PATH}"
$ tmux

#many directories inside

[detached (from session 0)]

```

```sh
$ cd ~
$ rm -rf tmp install
```

```sh
$ brew install tmux ngrok # or use linuxbrew 🎉
```

```sh
$ tmux new -s session_with_group
```

```sh
# Alisa:
$ open https://ngrok.com/signup # get token
$ export NGROK_TOKEN=1adZTO7m5B6TMKmaUDxRIWyA8My_86sG3KcEb3YTqe4PDGV7A
$ ngrok authtoken ${NGROK_TOKEN} # authefication
$ ngrok tcp 22 # create ngrok server on 22 port
ngrok by @inconshreveable                                                                    (Ctrl+C to quit)
                                                                                                             
Session Status                online                                                                         
Account                       jonnyuz99@gmail.com (Plan: Free)                                               
Version                       2.3.35                                                                         
Region                        United States (us)                                                             
Web Interface                 http://127.0.0.1:4040                                                          
Forwarding                    tcp://0.tcp.ngrok.io:17393 -> localhost:22                                     
                                                                                                             
Connections                   ttl     opn     rt1     rt5     p50     p90                                    
                              2       0       0.00    0.00    222.41  324.81 
<порт_ngrok_сервера>
```

```sh
# Bob:
$ ssh ${USERNAME}@0.tcp.ngrok.io -p<порт_ngrok_сервера>
The authenticity of host '[0.tcp.ngrok.io]:17393 ([3.13.191.225]:17393)' can't be established.
ECDSA key fingerprint is SHA256:a3w2WRivSBwPkjM/RkrOV7RM+ckUL1xHhywCW5s/5yM.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '[0.tcp.ngrok.io]:17393,[3.13.191.225]:17393' (ECDSA) to the list of known hosts.
developer@0.tcp.ngrok.io's password: 
Welcome to Ubuntu 19.10 (GNU/Linux 5.3.0-45-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sat 25 Apr 2020 04:19:39 PM UTC

  System load:  0.0               Processes:           110
  Usage of /:   3.1% of 61.80GB   Users logged in:     2
  Memory usage: 9%                IP address for eth0: 10.0.2.15
  Swap usage:   0%                IP address for eth1: 192.168.1.5


25 updates can be installed immediately.
17 of these updates are security updates.
To see these additional updates run: apt list --upgradable

$ tmux a -t session_with_group
$ <C-B>"
```

## Report

```sh
$ cd ~/workspace/
$ export LAB_NUMBER=11
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER}.git tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```

## Links

- [Tmux](https://raw.githubusercontent.com/tmux/tmux/master/README)
- [Libevent](http://libevent.org)
- [Ncurses](http://invisible-island.net/ncurses/)

```
Copyright (c) 2015-2020 The ISC Authors
```
