< [Back](README.md)

配置文件
========

Shadowsocks accepts JSON format configs like this:

```
{
    "server":"my_server_ip",
    "server_port":8388,
    "local_port":1080,
    "password":"barfoo!",
    "timeout":600,
    "method":"table"
}
````

Explanation of each field:

* server: your hostname or server IP (IPv4/IPv6).
* server_port: server port number.
* local_port: local port number.
* password: a password used to encrypt transfer.
* timeout: connections timeout in seconds.
* method: encryption method, "bf-cfb", "aes-256-cfb", "des-cfb", "rc4", etc. Default is table, which is not secure. "aes-256-cfb" is recommended.
