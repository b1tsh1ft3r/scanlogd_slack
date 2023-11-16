* ScanLogD Slack


These instructions are for CentOS 7 because this is what it was developed and tested on.

See scanlogd.c source for webhook implementation and calls to it.

* Install / Testing process

yum install gcc and libcurl-devel
add a user called scanlogd with nologin ability
Copy over source for linux version to a folder

Cd into the folder with the linux source and run "make linux".
copy the compiled scanlogd binary to /opt/scanlogd/
make a systemd unit file to start/stop /opt/scanlogd/scanlogd binary.
Call systemctl daemon-reload and enable the systemd service

when compiling binary, you need to run "make linux" to use raw linux sockets so we
dont use libpcap library. Keep this in mind. 

* Ansible deployment
Currently at the time of writing this, this playbook is in-complete.