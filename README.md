# Grafana Influx radiator

Here be a Influx time series DB with Grafana on top usefull for ad-hock
information radiation business.

In short:
 * Spin up the stack.
 * Start pumping data to Influx
 * Tune Grafana to your liking
 * Profit


# Install

You need to have this installed and configured on your dev nachine
- docker
- virtualenvwrapper

Create a virtualenv for docker-compose and the python influx client libs:

```sh
mkvirtualenv influx
pip install docker-compose
```

# Run

Raise the stack
```sh
docker-compose up
```

All service are now available at their respective ports: 
- Grafana: http://localhost:3000
- Influx Admin: http://localhost:8083

