# Squid

## Debug the actual machine

「環境設定」を開き、「メニューバー」の「詳細」タブに「開発」メニューを表示します。ケーブルを接続し、`Development` から対応するデバイスを選択し、ターゲットサイトを選択します。すると、MacでWebインスペクタが開きます。

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

事前準備として、「設定」を開き、「Safari」をタップします。 `Web インスペクタ` をオンにします。

