# AppArmor Manipulation Detection

AppArmor is a Linux security module that enforces fine-grained access control policies.  
Disabling AppArmor is a high-severity alert, typically indicating a targeted attack that requires immediate response.

## Challenge Objective

Write detection rules that identify behaviors attempting to disable or shut down AppArmor.

---

## Sample Data

Located in `sample_data/sysmon_apparmor_sample.json`

```json
{
  "Image": "/usr/bin/systemctl",
  "CommandLine": "systemctl disable apparmor",
  "ParentImage": "/usr/bin/bash",
  "User": "root"
}
