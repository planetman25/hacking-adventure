# Running BeEF in the background

If you want to run BeEF in the background you can do so by generating a service in /etc/systemd/system/*

Follow steps to create a service for BeEF and allow it to run as a service in your VM.

1- Create the file.
sudo nano /etc/systemd/system/beef.service

2- Edit the file and add this:
[Unit]
Description=BeEF Browser Exploitation Framework
After=network.target

[Service]
Type=simple
User=kali
WorkingDirectory=/home/kali/beef
ExecStart=/home/kali/beef/beef
Restart=on-failure

[Install]
WantedBy=multi-user.target

*Replace "kali" with the actual user you are using in your VM.

3- Enable the service with daemon reload and start it.
sudo systemctl daemon-reload
sudo systemctl enable beef.service
sudo systemctl start beef.service

Verify status of the service.
sudo systemctl status beef.service

4 - Audit logs to see if there is any problem with the service.
sudo journalctl -u beef.service -f

5 - Use systemctl to start, stop, enable, disable, restart, etc.
