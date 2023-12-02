1. At first, you should install the proxy software. Just take an example for the popular one. You should download it at first. Someone may develop version with UI and if we just want the proxy to run at background, make sure to choose the one for backend. Because the startup process may fail when UI initilized.
2. Then put the executable file to some where. Just test running it. It may need some dependencies. If you only have a subscribe link, it may not be working. You use convert it to config.yaml, maybe the software on windows and just copy it. Download it to some path.
3. Try to start it up directly like ```"executable" -d "config path"```. Make sure it is working. Maybe to set the proxy in firefox.
4. Then just register the command as a systemd service because we want it run at all time.

```
[Unit]
Description=Proxy Service
After=network.target
StartLimitIntervalSec=0

[Service]
Type=simple
User=0
ExecStart="your executable" -d "path" # It depends on your proxy software

[Install]
WantedBy=multi-user.target
```

Then try to run `systemctl start ""` to start. Run `systemctl status ""` to see if it is running well. Run `systemctl enable ""` to make it starts up when system starts up.

5. Then we should set it to the proxy for system proxy. We want it works for all. So change the "/etc/environment" like below.

```
http_proxy=http://localhost:1111
https_proxy=http://localhost:1111
no_proxy="localhost,127.0.*,192.168.*,::1"
```
