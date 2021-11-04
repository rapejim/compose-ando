# Otras cosas para experimentar

## Uso de variables comunes (version minima 3.4)

```yaml
####################
## Utiles comunes ##
####################
x-environment-puid:
  &default-puid
  # PUID: ${UID:-1000}
  PUID: ${UID:?  ¡IMPORTANTE! Falta el UID, ejecuta --> export UID=$UID}

x-environment-pgid:
  &default-pgid
  # PGID: ${GID:-1000}
  PGID: ${GID:?  ¡IMPORTANTE! Falta el GID, ejecuta --> export GID=$(id -g)}

x-environment-userid:
  &default-userid
  # USER_ID: ${UID:-1000}
  USER_ID: ${UID:?  ¡IMPORTANTE! Falta el UID, ejecuta --> export UID=$UID}

x-environment-groupid:
  &default-groupid
  # GROUP_ID: ${GID:-1000}
  GROUP_ID: ${GID:?  ¡IMPORTANTE! Falta el GID, ejecuta --> export GID=$(id -g)}


# Se usaría tal que...
    environment:
      << : *default-puid
      << : *default-pgid
      TZ: Europe/Madrid
```