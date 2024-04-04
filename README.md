# nut-ntfy
Send ntfy notification when your UPS is disconnected


## 1 - Install
Put the file send_ntfy in /etc/nut/

chmod 740 /etc/nut/send_ntfy

## 2 - Configure
Edit the file /etc/nut/upsmon.conf and set the script location to NOTIFYCMD line

NOTIFYCMD "/etc/nut/send_ntfy"

Edit the file /etc/nut/send_ntfy
Replace line 63 and 74 YOUR_NTFY_TOPIC by your ntfy topic

## 3 - Test
Use this command and be a message should appear on your ntfy topic
```console
 /etc/nut/send_ntfy
```

## 4 - Star me :)
