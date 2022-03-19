# apache-php

Apache php Dockerfile with http2 enabled

Build 
```
docker build . -t apache-phpss 
```
Test
```
docker run -d -p 8000:80  \
  -v /your/php/source/code:/var/www/html \
  --name my-application  apache-phpss:latest
```

```

<Directory "/var/www/html/LDAPTest">
    Options all
    Order deny,allow
    #Allow from All
    AuthName "Company.com Intranet"
    AuthType Basic
    AuthBasicProvider ldap
    #AuthzLDAPAuthoritative off
    AuthLDAPUrl "ldap://DC.COM/DC=DC,DC=COM?sAMAccountName?sub?(objectClass=*)"
    AuthLDAPBindDN ::MANAGERDN/SERVICE-ACCOUNT::
    AuthLDAPBindPassword ::PASSWORD::
    #Require valid-user
    Require ldap-user :ADUSER1: :ADUSER2: :ADUSER3:
    #Satisfy any
</Directory>

``

