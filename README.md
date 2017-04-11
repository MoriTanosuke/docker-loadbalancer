## Boot The App

From the root of the repository:

```shell
docker-compose up -d
```

## Inspection
### Consul Registered Services

```shell
curl http://localhost:8500/v1/catalog/services
```

or you can open http://localhost:8500 to go to the consul UI.

### Visit LB In Default Browser

Open http://localhost/ in your browser.

## Adding/Removing Backend Containers

```shell
docker-compose scale app=4
docker-compose app=1
```

## Gotchas
* The auto-detected advertise IP for Consul-in-Docker on Boot2docker does not appear to be routable from the Nginx container. Use the following to look up the IP to set for `-advertise`:

```shell
ifconfig eth0 | grep 'inet addr'
```
