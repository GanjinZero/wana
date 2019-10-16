# 问题描述
```
Traceback (most recent call last):
  File "test_db.py", line 7, in <module>
    conn = cx_Oracle.connect(conn_str)
cx_Oracle.DatabaseError: DPI-1047: Cannot locate a 64-bit Oracle Client library: "libclntsh.so: cannot open shared object file No such file or directory". See https://oracle.github.io/odpi/doc/installation.html#linux for help
```

# 解决方案
```
$ wget https://download.oracle.com/otn_software/linux/instantclient/193000/instantclient-basic-linux.x64-19.3.0.0.0dbru.zip
$ sudo mkdir -p /opt/oracle
$ sudo unzip ./instantclient-basic-linux.x64-19.3.0.0.0dbru.zip
$ sudo sh -c "echo /opt/oracle/instantclient_19_3 > /etc/ld.so.conf.d/oracle-instantclient.conf"
$ sudo ldconfig
```
