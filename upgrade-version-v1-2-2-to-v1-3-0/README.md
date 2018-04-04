![Polis](https://github.com/polispay/polis-doc/raw/master/resources/polis.png "Polis")

# Upgrade Masternode v1.2.2 to v1.3.0

In this guide you will learn how to upgrade your Polis Masternode in Ubuntu version 16.04 VPS.

Before you start, you need to meet the initial requirements:
* Local: Windows 8.1 64 bit.
* Remote: Ubuntu 16.04 64 bit.
* Polis Version: 1.2.1 (Installed using guide from polis-doc).

Note: Upgrade to v1.3.0 from v1.2.2 is not a mandatory upgrade.

## Upgrade steps

### Polis Daemon

This steps are going to be following:
* Stop Polis daemon.
* Download new version.
* Upgrade current version.
* Run again daemon.

```
polis-cli stop
```

```
cd
```

```
wget https://github.com/polispay/polis/releases/download/v1.3.0/poliscore-1.3.0-x86_64-linux-gnu.tar.gz
```

```
tar -xvf poliscore-1.3.0-x86_64-linux-gnu.tar.gz
```

```
rm poliscore-1.3.0-x86_64-linux-gnu.tar.gz
```

```
cp poliscore-1.3.0/bin/polis{d,-cli} /usr/local/bin
```

Run again Polis daemon:

```
polisd &
```

If you have Polis running as a service, you have to run following command:

```
systemctl stop polisd
```

```
systemctl start polisd
```

If you write following command:

```
watch polis-cli getinfo
```

Version field should be "1030000".

```
{
  "version": 1030000,
...
  "errors": ""
}
```

### Sentinel

Now you have to upgrade Sentinel to last version:

```
cd /sentinel && git pull
```

### Masternode status

If you want to check your masternode status, you have to write following command on your VPS:

```
polis-cli masternode status
```
