# ldap_docker
Erste Schritte mit LDAP und iPython in Docker


```
git clone https://github.com/yunusabd/ldap_docker && cd ldap_docker
docker-compose up -d --build

# Direkter Zugriff auf den LDAP-Server:
docker-compose exec ldap /bin/bash

# Interaktive Shell in iPython:
docker-compose exec python ipython

```

In iPython:
```
In [1]: import ldap

In [2]: c = ldap.initialize('ldap://ldap') # default port 389

In [3]: c.search_s('dc=example,dc=org', ldap.SCOPE_SUBTREE)

Out[3]: 
[('dc=example,dc=org',
  {'objectClass': [b'top', b'dcObject', b'organization'],
   'o': [b'Example Inc.'],
   'dc': [b'example']})]
```

TODOS: 
* Script zum Erstellen von lokalen SSL-Zertifikaten für die TLS-Verbindung.
* Python-Paket ldap3 testen, evtl. besseres Interface als python-ldap
* Python-Scripts für CRUD-Operationen
