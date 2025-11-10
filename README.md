# Project 2: Auditing
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
1. Rules
- In `/etc/audit/rules.d/audit.rules` I added a **watch** rule for each file in `/protected_files` (`cloudia.txt`, `car_sales.csv`, `dolly.txt`, `precipitation.csv`, `earthquakes.csv`, `loggy.txt`, `oakley.txt`, `squeaky.txt`, `tosty.txt`, `website.txt`)
- **-w** states that the file will be watched for any alterations
- **-p** sets the type of permissions to be monitored, in this case, checking **write** permissions as each of the three attacks modify one of the above files
- **-k** attaches a **filter key**, which is an important identifier to help search through the logs for each file and see exactly who altered them
- For each file, I added a rule in the following format: `-w <filepath> <filename> -p w -k <filter_key>`, each rule with a unique filter key
2. Searching Logs
-   Made each attack executable (`chmod u+x attack-X`) and ran the attacks (`./attack-X`)
-   Searched through the Audit logs using `ausearch`, a command used to search Linux audit logs for specific events based on an identifier, in our case, the unique filter key
-   Entered `sudo ausearch -k <filter_key>` to retrieve the specific logs for each file
## Key Findings
## Reflection
