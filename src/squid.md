# Squid

## Debug the actual machine

Open `Preferences`, show `Development` menu in Menu bar on the advanced tab. Connect the cable, select the corresponding device from `Development`, and select the target site. Then the Web Inspector opens on your Mac

```bash
sudo vi /usr/local/etc/squid.conf
```

### The following 3 points are changed

```bash
visible_hostname unknown
```

![](https://i.imgur.com/D9GZrZU.jpg)

```bash
acl hiro src 192.168.2.0/255.255.255.255
```

![](https://i.imgur.com/WrnFEaw.jpg)

```bash
http_access allow hiro
```

![](https://i.imgur.com/4VhRbcU.jpg)

### On devices

As a preliminary preparation, open `Settings` and tap Safari. Turn on `Web Inspector`.

