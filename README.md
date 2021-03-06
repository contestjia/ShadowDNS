ShadowDNS
=========

[![PyPI version]][PyPI] [![Build Status]][Travis CI] 

A DNS forwarder using [Shadowsocks] as the server.

ShadowDNS creates a DNS server at localhost.

Experimental; use with caution.

Install
-------

#### OS X:

    brew install swig
    git clone https://github.com/clowwindy/M2Crypto.git
    cd M2Crypto
    pip install .
    pip install shadowdns

#### Windows:

Install M2Crypto (Google an M2Crypto Windows installer for your python version
 and install it. Might be complicated, need someone to write a help here).

    easy_install pip
    pip install shadowdns

#### Debian / Ubuntu:

    apt-get install python-pip python-m2crypto
    pip install shadowdns

#### CentOS:

    yum install m2crypto python-setuptools
    easy_install pip
    pip install shadowdns

Usage
-----

Create a config file `/etc/shadowdns.json` (or put it in other path).
Example:

    {
        "server":"my_server_ip",
        "server_port":8388,
        "local_address": "127.0.0.1",
        "password":"mypassword",
        "method":"aes-256-cfb",
        "dns":"8.8.8.8"
    }

Explanation of the fields:

| Name          | Explanation                                     |
| ------------- | ----------------------------------------------- |
| server        | the address your server listens                 |
| server_port   | server port                                     |
| local_address | the address your local listens                  |
| password      | password used for encryption                    |
| method        | encryption method, "aes-256-cfb" is recommended |
| dns           | DNS server to use                               |


Run `sudo ssdns -c /etc/shadowdns.json` on your local machine.

Set your DNS to 127.0.0.1.

License
-------
MIT

Bugs and Issues
----------------
Please visit [Issue Tracker]

Mailing list: http://groups.google.com/group/shadowsocks


[Build Status]:    https://img.shields.io/travis/clowwindy/ShadowDNS/master.svg?style=flat
[Issue Tracker]:   https://github.com/clowwindy/ShadowDNS/issues?state=open
[PyPI]:            https://pypi.python.org/pypi/shadowdns
[PyPI version]:    https://img.shields.io/pypi/v/shadowdns.svg?style=flat
[Shadowsocks]:     https://github.com/clowwindy/shadowsocks
[Travis CI]:       https://travis-ci.org/clowwindy/ShadowDNS
