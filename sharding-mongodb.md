# Sharding mongodb config
# 1. Replca
- replSet: "rs0"
- bind_ip: 10.148.0.2:27017,10.148.0.3:27017,10.148.0.3:27018
- configsvr: 10.148.0.2:27019,10.148.0.3:27019
- mongos: 10.148.0.3.27017

- start mongos:
```
sudo mongos --configdb configReplSet/10.148.0.2:27019,10.148.0.3:27019
```

- mongo shell
```
mongo --port
```

- mongos
```
mongo --host 10.148.0.3 --port 27017
```

Reference:
https://docs.mongodb.com/manual/tutorial/convert-replica-set-to-replicated-shard-cluster/
https://severalnines.com/blog/turning-mongodb-replica-set-sharded-cluster
