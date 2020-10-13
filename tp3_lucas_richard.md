## TP3_Systemd_LINUX: SERVICES

:::info
**Commandes pour afficher les services systemd actifs**
```.
[vagrant@tp3 sysconfig]$ systemctl --type=service --state=running
UNIT                     LOAD   ACTIVE SUB     DESCRIPTION
auditd.service           loaded active running Security Auditing Service
chronyd.service          loaded active running NTP client/server
crond.service            loaded active running Command Scheduler
dbus.service             loaded active running D-Bus System Message Bus
getty@tty1.service       loaded active running Getty on tty1
gssproxy.service         loaded active running GSSAPI Proxy Daemon
NetworkManager.service   loaded active running Network Manager
polkit.service           loaded active running Authorization Manager
postfix.service          loaded active running Postfix Mail Transport Agent
rpcbind.service          loaded active running RPC bind service
rsyslog.service          loaded active running System Logging Service
sshd.service             loaded active running OpenSSH server daemon
systemd-journald.service loaded active running Journal Service
systemd-logind.service   loaded active running Login Service
systemd-udevd.service    loaded active running udev Kernel Device Manager
tuned.service            loaded active running Dynamic System Tuning Daemon

LOAD   = Reflects whether the unit definition was properly loaded.
ACTIVE = The high-level unit activation state, i.e. generalization of SUB.
SUB    = The low-level unit activation state, values depend on unit type.

16 loaded units listed. Pass --all to see loaded but inactive units, too.
To show all installed unit files use 'systemctl list-unit-files'
```

:::

:::info
**Lister les services dispos sur la machine
```.
[vagrant@tp3 sysconfig]$ systemctl list-units --type=service
  UNIT                                                  LOAD   ACTIVE SUB     DESCRIPTION
  auditd.service                                        loaded active running Security Auditing Service
  chronyd.service                                       loaded active running NTP client/server
  crond.service                                         loaded active running Command Scheduler
  dbus.service                                          loaded active running D-Bus System Message Bus
  getty@tty1.service                                    loaded active running Getty on tty1
  gssproxy.service                                      loaded active running GSSAPI Proxy Daemon
  kmod-static-nodes.service                             loaded active exited  Create list of required static device nodes for the current kernel
  network.service                                       loaded active exited  LSB: Bring up/down networking
<E2><97><8F> NetworkManager-wait-online.service                    loaded failed failed  Network Manager Wait Online
  NetworkManager.service                                loaded active running Network Manager
  polkit.service                                        loaded active running Authorization Manager
  postfix.service                                       loaded active running Postfix Mail Transport Agent
  rhel-dmesg.service                                    loaded active exited  Dump dmesg to /var/log/dmesg
  rhel-domainname.service                               loaded active exited  Read and set NIS domainname from /etc/sysconfig/network
  rhel-readonly.service                                 loaded active exited  Configure read-only root support
  rpcbind.service                                       loaded active running RPC bind service
  rsyslog.service                                       loaded active running System Logging Service
<E2><97><8F> selinux-policy-migrate-local-changes@targeted.service loaded failed failed  Migrate local SELinux policy changes from the old store structure to the new structure
  sshd.service                                          loaded active running OpenSSH server daemon
  systemd-journal-flush.service                         loaded active exited  Flush Journal to Persistent Storage
  systemd-journald.service                              loaded active running Journal Service
  systemd-logind.service                                loaded active running Login Service
  systemd-random-seed.service                           loaded active exited  Load/Save Random Seed
  systemd-remount-fs.service                            loaded active exited  Remount Root and Kernel File Systems
  systemd-sysctl.service                                loaded active exited  Apply Kernel Variables
  systemd-tmpfiles-setup-dev.service                    loaded active exited  Create Static Device Nodes in /dev
  systemd-tmpfiles-setup.service                        loaded active exited  Create Volatile Files and Directories
  systemd-udev-trigger.service                          loaded active exited  udev Coldplug all Devices
  systemd-udevd.service                                 loaded active running udev Kernel Device Manager
  systemd-update-utmp.service                           loaded active exited  Update UTMP about System Boot/Shutdown
  systemd-user-sessions.service                         loaded active exited  Permit User Sessions
  systemd-vconsole-setup.service                        loaded active exited  Setup Virtual Console
  tuned.service                                         loaded active running Dynamic System Tuning Daemon

LOAD   = Reflects whether the unit definition was properly loaded.
ACTIVE = The high-level unit activation state, i.e. generalization of SUB.
SUB    = The low-level unit activation state, values depend on unit type.

33 loaded units listed. Pass --all to see loaded but inactive units, too.
To show all installed unit files use 'systemctl list-unit-files'.
```
:::

:::info
**Lister les services échoués**

```.
[vagrant@tp3 sysconfig]$ systemctl list-units --type=service --failed
  UNIT                                                  LOAD   ACTIVE SUB    DESCRIPTION
<E2><97><8F> NetworkManager-wait-online.service                    loaded failed failed Network Manager Wait Online
<E2><97><8F> selinux-policy-migrate-local-changes@targeted.service loaded failed failed Migrate local SELinux policy changes from the old store structure to the new structure

LOAD   = Reflects whether the unit definition was properly loaded.
ACTIVE = The high-level unit activation state, i.e. generalization of SUB.
SUB    = The low-level unit activation state, values depend on unit type.

2 loaded units listed. Pass --all to see loaded but inactive units, too.
To show all installed unit files use 'systemctl list-unit-files'.
```
:::

:::info
**Lister les services inactifs**

```.
[vagrant@tp3 sysconfig]$ systemctl list-units --type=service --state=exited
UNIT                               LOAD   ACTIVE SUB    DESCRIPTION
kmod-static-nodes.service          loaded active exited Create list of required static device nodes for the current kernel
network.service                    loaded active exited LSB: Bring up/down networking
rhel-dmesg.service                 loaded active exited Dump dmesg to /var/log/dmesg
rhel-domainname.service            loaded active exited Read and set NIS domainname from /etc/sysconfig/network
rhel-readonly.service              loaded active exited Configure read-only root support
systemd-journal-flush.service      loaded active exited Flush Journal to Persistent Storage
systemd-random-seed.service        loaded active exited Load/Save Random Seed
systemd-remount-fs.service         loaded active exited Remount Root and Kernel File Systems
systemd-sysctl.service             loaded active exited Apply Kernel Variables
systemd-tmpfiles-setup-dev.service loaded active exited Create Static Device Nodes in /dev
systemd-tmpfiles-setup.service     loaded active exited Create Volatile Files and Directories
systemd-udev-trigger.service       loaded active exited udev Coldplug all Devices
systemd-update-utmp.service        loaded active exited Update UTMP about System Boot/Shutdown
systemd-user-sessions.service      loaded active exited Permit User Sessions
systemd-vconsole-setup.service     loaded active exited Setup Virtual Console

LOAD   = Reflects whether the unit definition was properly loaded.
ACTIVE = The high-level unit activation state, i.e. generalization of SUB.
SUB    = The low-level unit activation state, values depend on unit type.

15 loaded units listed. Pass --all to see loaded but inactive units, too.
To show all installed unit files use 'systemctl list-unit-files'.
```
:::

:::info
**Lister les services qui échouent au boot**
```.
[vagrant@tp3 sysconfig]$ systemctl list-units --type=service --state=enabled
0 loaded units listed. Pass --all to see loaded but inactive units, too.
To show all installed unit files use 'systemctl list-unit-files'.
```
:::

:::info
**Nginx est bien actif**
```.
[vagrant@tp3 sysconfig]$ systemctl status nginx
● nginx.service - The nginx HTTP and reverse proxy server
   Loaded: loaded (/usr/lib/systemd/system/nginx.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
   ```
(je sais que c'est pas utile mais c'est peut être mieux de le préciser)

:::

:::info
**Contenu de Nginx**
```.
[vagrant@tp3 nginx]$ systemctl cat nginx.service
# /usr/lib/systemd/system/nginx.service
[Unit]
Description=The nginx HTTP and reverse proxy server
After=network.target remote-fs.target nss-lookup.target

[Service]
Type=forking
PIDFile=/run/nginx.pid
# Nginx will fail to start if /run/nginx.pid already exists but has the wrong
# SELinux context. This might happen when running `nginx -t` from the cmdline.
# https://bugzilla.redhat.com/show_bug.cgi?id=1268621
ExecStartPre=/usr/bin/rm -f /run/nginx.pid
ExecStartPre=/usr/sbin/nginx -t
ExecStart=/usr/sbin/nginx
ExecReload=/bin/kill -s HUP $MAINPID
KillSignal=SIGQUIT
TimeoutStopSec=5
KillMode=process
PrivateTmp=true

[Install]
WantedBy=multi-user.target
```

**Vu plus haut, le path de nginx.service: /usr/lib/systemd/system/nginx.service**

:::success
***Explications du contenu***

**(Infos récupérées depuis `man systemd.service`**

**ExecStart**: 
```.
Commands with their arguments that are executed when this service is started. 
The value is split into zero or more command lines is according to the rules described below
```

Commandes executées pour lancer le service nginx


**ExecStartPre**:
```.
Additional commands that are executed before or after the command in ExecStart=, respectively. 
Syntax is the same as for ExecStart=, except that multiple command lines are allowed and the commands are executed one after the other, serially.
```
Commandes nécessairement executées avant le lancement du service.

**PIDFile**:
```.
Takes an absolute path referring to the PID file of the service. 
Usage of this option is recommended for services where Type= is set to forking.
```
(Process identification number). Le path ```
/run/nginx.pid```indique l'endroit ou est stocké ce PID.


**Type**: 
```.
If set to forking, it is expected that the process configured with ExecStart= will call fork() as part of its start-up. 
The parent process is expected to exit
when start-up is complete and all communication channels are set up. 
The child continues to run as the main daemon process. This is the behavior of traditional UNIX daemons. 
If this setting is used, it is recommended to also use the PIDFile= option, so that systemd can identify the main process of the daemon. systemd will proceed with starting follow-up units as soon as the parent process exits
```

Le Type est `fork`mais je ne comprends pas ce que cela signifie sinon que le process `ExecStart` va appeler une **fork()** lors du lancement du service. Si j'ai bien compris, le type permet de définir le fonctionnement de running du service. Ici, le service va poursuivre son running en background(Juste?)

**ExecReload**:
```.
Commands to execute to trigger a configuration reload in the service.
```
Commande permettant de déclencher une configuration de reboot 

**(Infos récupérées depuis `man systemd.unit`)**

**Description**:
```.
A free-form string describing the unit. 
This is intended for use in UIs to show descriptive information along with the unit name. 
The description should contain a name that means something to the end user
```
Une description précise mais compréhensible pour l'utilisateur final. Le but étant que cette information soit accessible à M. Tout le monde.



**After**:
```.
A space-separated list of unit names. 
Configures ordering dependencies between units
```
Liste des noms des unités. Configure un ordre entre les dépendances (à priori nécessaire au lancement du service j'imagine).
:::


:::info
**3. Création d'un service**
Pour la création du fichier: 

```.
sudo touch /etc/systemd/system/webserv.service
```

Lancer serveur web: 
```.
python3 -m http.server 2200
Serving HTTP on 0.0.0.0 port 2200 (http://0.0.0.0:2200/) ...
```
Configuration du service webserv.service que j'ai créé:

```.
[Unit]
Description=web_server

[Service]
ExecStartPre= sudo firewall-cmd --add-port=2200/tcp
ExecStart=python3 -m http.server 2200
Type=forking
```
:::
Je sais que ce n'est pas bien fini mais je ne me sens pas capable de faire le reste. Je vais retenter un peu plus tard et te l'envoyer afin que tu me dises si les pratiques sont bien respectées ou non. 