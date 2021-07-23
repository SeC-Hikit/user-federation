# user-federation
User Federation scripts

# Login Page theme

## Deploy
### On Docker
In order to get a custom login page, clone this repo and then run:
```docker cp ./sec-theme/ <container-id>:/opt/jboss/keycloak/themes/sec-theme```

## Development
If the login page development is intended, start by disabling the login caching mechanism:
```
sh bin/jboss-cli.sh 
connect
/subsystem=keycloak-server/theme=defaults/:write-attribute(name=staticMaxAge,value=-1)
/subsystem=keycloak-server/theme=defaults/:write-attribute(name=cacheTemplates,value=false)
/subsystem=keycloak-server/theme=defaults/:write-attribute(name=cacheThemes,value=false)
reload
```
