### run choreo connect with prometheus metrics exported

```
docker-compose up -d
```

### curls metrics

## adapter
```
curl 'http://localhost:12344/metrics'
```
## enforcer
```
curl 'http://localhost:12345/metrics'
```
## adapter
```
curl 'http://localhost:9000/stats/prometheus'
```

##INFO
not all metrics are available wihtout a api deployed and queried. Use the included apictl and deploy a api. query afterwards:
```
./apictl mg add env dev --adapter https://localhost:9843 -k
./apictl mg login dev -k
./apictl mg deploy api -f ./httpbin -e dev -k
curl -v -k 'http://localhost:9090/httpbin-test/1.0.0/get'
```
