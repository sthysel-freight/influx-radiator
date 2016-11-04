# Influx radiator


# Install stack on local dev machine
You can run the complete stack on your local dev machine.

## Dependencies
You need to have this installed and configured on your dev nachine
- docker
- virtualenvwrapper

Create a virtualenv for docker-compose and the python influx client libs:
```sh
mkvirtualenv influx
pip install docker-compose
```

Raise the stack
```sh
docker-compose up
```

All service are now available at their respective ports: 
- Graphana: http://localhost:3000
- Influx Admin: http://localhost:8083

