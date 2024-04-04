# nut-ntfy
Send ntfy notification when your UPS is disconnected - and reconnected

![screenshot](nut_ntfy.png)

The script is configured for my EATON UPS
/etc/ups.conf :
```console
[EATON]
driver = usbhid-ups
port = auto
desc = "EATON usb driver"
```


## 1 - Install
Put the file send_ntfy in /etc/nut/

chmod 740 /etc/nut/send_ntfy

## 2 - Configure
Edit the file /etc/nut/upsmon.conf and set the script location to NOTIFYCMD line

NOTIFYCMD "/etc/nut/send_ntfy"

Edit the file /etc/nut/send_ntfy
Replace line 63 and 74 YOUR_NTFY_TOPIC by your ntfy topic

## 3 - Test
Use this command and a message should appear on your ntfy topic
```console
 /etc/nut/send_ntfy
```

## 4 - modify script

By default, the script will send a notification when the UPS reaches the % below, change as you will !
```console
alert_at=(25 50 75 85 90 95 98)
```

## 4 - Star me :)
