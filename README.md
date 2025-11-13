# nut-ntfy
Send ntfy notification when your UPS is disconnected - and reconnected

![screenshot](nut_ntfy.png)

The script is tested on an EATON UPS

/etc/ups.conf :
```console
[EATON]
driver = usbhid-ups
port = auto
desc = "EATON usb driver"
```


## 1 - Install
Copy the file send_ntfy to /etc/nut/

Set the permission on the file :
```console
chown root:nut /etc/nut/send_ntfy
chmod 774 /etc/nut/send_ntfy
 ```

## 2 - Configure
Edit the file /etc/nut/upsmon.conf and set the script location to NOTIFYCMD line

NOTIFYCMD "/etc/nut/send_ntfy"

Edit the file /etc/nut/send_ntfy

- Line 3 : replace line YOUR_NTFY_TOPIC by your ntfy.sh topic
- Line 4 : Add your UPS name on : UPS_name="YOUR_UPS_NAME" (You can find it with "upsc -l")



## 3 - Test
Send a test message to your ntfy.sh topic with this command
```console
 /etc/nut/send_ntfy test
```

## 4 - modify script
By default, the script will send a notification when the UPS reaches the % below, change as you wish !
```console
alert_at=(25 50 75 85 90 95 98)
```

## 4 - Star me :)
