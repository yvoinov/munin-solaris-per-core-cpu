# Munin plugin for Solaris per-core CPU utilization monitoring
[![License](https://img.shields.io/badge/License-MIT--Clause-blue.svg)](https://github.com/yvoinov/munin-solaris-per-core-cpu/blob/main/LICENSE)
## Motivation

This simple plugin was written due to the fact that there is no plugin for per-core monitoring of CPU utilization on Solaris for Munin.

The plugin allows you to detect overloads of individual processor cores or sudden load surges.

It is very useful for deep performance optimization tasks.

## Using plugin

Place the solaris_per_core_cpu plugin file in the Munin plugins directory, for example, `/opt/csw/libexec/munin/plugins`. Grant it execute permissions. Create a symbolic link in the active plugins directory, for example, `/etc/opt/csw/munin/plugins`:
```sh
ln -s /opt/csw/libexec/munin/plugins/solaris_per_core_cpu /etc/opt/csw/munin/plugins/solaris_per_core_cpu
```
Add the lines from the plugins.conf file to your plugins.conf file, for example, `/etc/opt/csw/munin/plugin-conf.d/plugins.conf`.

and restart the Munin node:
```sh
svcadm restart cswmuninnode
```
The configuration parameters have the following meanings:

- env.graph_ticks - statistics type; by default (0) it is a percentage; can be switched to the number of CPU cycles for optimization purposes and more accurate core utilization assessment

The plugin works on all Solaris-based platforms.

<img width="623" height="572" alt="изображение" src="https://github.com/user-attachments/assets/6f40eae1-4ea9-4364-b593-e05310b5bd7f" />
