# Attempting to Disable the Syslog Service (rsyslog) Detection

Adversaries may attempt to disable or stop the Syslog service (rsyslog) to hide their activities or prevent critical logging. Disabling or killing syslog daemons is a high-risk action and should be investigated.

## Challenge Objective

Write detection rules that identify behaviors attempting to disable, stop, or kill Syslog services (e.g., `rsyslog`, `syslog-ng`, `systemd-journald`) on Linux systems.  
The goal is to create Sigma-compatible rules that reliably trigger on common attack and admin commands while minimising false positives.

---

## Sample Data

Located in `sample_data/sysmon_syslog_sample.json`

```json
{
  "Image": "/usr/bin/systemctl",
  "CommandLine": "systemctl disable rsyslog",
  "ParentImage": "/usr/bin/bash",
  "User": "root",
  "Computer": "ubuntu-soclabs",
  "UtcTime": "2025-03-20 06:36:41.585",
  "ProcessId": "45236"
}

