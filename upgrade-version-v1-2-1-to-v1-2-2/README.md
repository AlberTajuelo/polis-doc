![Polis](https://github.com/polispay/polis-doc/raw/master/resources/polis.png "Polis")

# Upgrade Masternode v1.2.1 to v1.2.2

In this guide you will learn how to upgrade your Polis Masternode in Ubuntu version 16.04 VPS. 

Before you start, you need to meet the initial requirements:
* Local: Windows 8.1 64 bit.
* Remote: Ubuntu 16.04 64 bit.
* Polis Version: 1.2.1 (Installed using guide from polis-doc).

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
wget https://github.com/polispay/polis/releases/download/v1.2.2/poliscore-1.2.2-linux64.tar.gz
```

```
tar -xvf poliscore-1.2.2-linux64.tar.gz
```

```
rm poliscore-1.2.2-linux64.tar.gz
```

```
cp poliscore-1.2.2/bin/polis{d,-cli} /usr/local/bin
```

Run again Polis daemon:

```
polisd &
```

If you write following command:

```
watch polis-cli getinfò
```

Version field should be "1020200".

```
{
  "version": 1020200,
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
