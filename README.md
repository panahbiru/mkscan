MKSCAN
=====

Exploit and Webshell Scanner/Remover using ClamAV

* mkscan with auto-quarantine
```
cat <<EOF > /usr/local/bin/mkscan
#!/bin/bash
clamscan -d /usr/local/share/mkscan.db -l log.txt -r --max-filesize=100000 -o --move=/tmp/quarantine --detect-pua=yes $1
EOF
```

* mkscan WITHOUT auto-quarantine
```
cat <<EOF > /usr/local/bin/mkscan
#!/bin/bash
clamscan -d /usr/local/share/mkscan.db -l log.txt -r --max-filesize=100000 -o --detect-pua=yes $1
EOF
```
