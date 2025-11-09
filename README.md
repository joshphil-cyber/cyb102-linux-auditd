# Project 2: Lets _wget_ This Bread
Host Intrusion Detection System (HIDS) provides a very efficient way to monitor one's host device for any suspicious activity. In this simulated activity, I used Linux Audit daemon (auditd), which is a HIDS that comes with preconfigured rules, to monitor file changes in directory `/protected_files` and launch three attacks, then track changes made to files in directory
***
## Goals
- Configure Audit rules to monitor file changes in `/protected_files`
- Launch 3 attacks (`attack-a`, `attack-b`, and `attack-c`) on some unknown files in `/protected_files`
- Use Audit to identify which files in `/protected_files` were changed and which attack made those changes

## Tools
- **Ubuntu VM (Microsoft Azure)**: safe cloud-based virtual environment to run attacks on text files and log any changes made to those files
- **Linux Audit daemon (auditd)**: background service (daemon) used to monitor activity on files with customizable rules, for the purpose of this activity, used for Intrusion Detection
## Process
## Key Findings
## Reflection
