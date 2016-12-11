# Movable Type Dev Box

## Install

Prerequisite: 
- MT-<version>.zip file
- Change `mt_source_path` to approriate filepath
- [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest)

Go to http://192.168.33.17/cgi-bin/mt/mt.cgi to test.

## Backup

```sh
mysqldump -umt -p mt_db > mt_db.sql
(cd /var/www && tar zcf www.tar.gz *)
```

## Restore

```sh
mysql -umt -p mt_db < mt_db.sql
(cd /var/www && tar zxf www.tar.gz)
```

## Troubleshoot

### Restart Apache server

```sh
# kill all httpd process
sudo pidof httpd | xargs sudo kill -9

sudo rm /run/httpd/httpd.pid

apachectl start
```
