---
tags:
  - Articles that need to be expanded
  - Linux
  - Open Source Software
  - Security Software
  - Tools
---
AppArmor, found in Suse and [Ubuntu](ubuntu.md) Linux, is a system for letting
applications run according to the principle of least privilege. This can be a
useful for running forensic or other tools of questionable stability (what
according to many means almost all tools) on data that may constructed with
malicious intent against the specific tool, and mitigating the potential damage
to the forensic process. While AppArmor works with static profiles, it does not
intervene in communication of open files over unix sockets, that thus can be
used to dynamically communicate authority to an (untrusted) AppArmor confined
tool.
