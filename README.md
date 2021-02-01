# IMSIGULAR APP
- Web app in angular
- WebSocket app in python

## Repo GIT
    https://github.com/xmalmorthen/imsigularApp.git

#### AnyDesk install [ optional ]
- sudo su
- wget -qO - https://keys.anydesk.com/repos/DEB-GPG-KEY | apt-key add -
- echo "deb http://deb.anydesk.com/ all main" > /etc/apt/sources.list.d/anydesk-stable.list
- apt update
- apt install anydesk

#### Static IP
- 192.168.0.200

#### RESOLVE BUGS MANUALLY
    Error message: File or stream is not seekable.
    
    File: /usr/local/lib/python[ XXX ]/dist-packages/daemon/runner.py
        self.daemon_context.stdin = open(app.stdin_path, 'rt')
        self.daemon_context.stdout = open(app.stdout_path, 'w+t')
        self.daemon_context.stderr = open(app.stderr_path, 'w+t', buffering=0)			
        
    Change the following lines
        self.daemon_context.stdin = open(app.stdin_path, 'wb+',buffering=0)
        self.daemon_context.stdout = open(app.stdout_path,  'wb+',buffering=0)
        self.daemon_context.stderr = open(app.stderr_path, 'wb+', buffering=0)"

#### CONFIGURE SERVICE AT STARTUP
    /usr/bin/xterm -iconic -hold -e / [APPDIR] /scripts/imsigular-up &

#### COMMANDS
- See file log

        tail -f -n 5 /home/imsi/imsigular/wsServer/logs/{file}.log

- Get pid services
    
        ps -ef | grep 'imsigular-server'

- Down socket server

        / [APPDIR] /scripts/imsigular-down &