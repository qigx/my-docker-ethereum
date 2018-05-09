# docker-ethereum

This is the repository for the kunstmaan/ethereum-{g}eth docker images.

## Images

* [kunstmaan/ethereum-eth](https://hub.docker.com/r/kunstmaan/ethereum-eth/): An Ubuntu 16.04 image with the Ethereum C++ eth binaries installed.
* [kunstmaan/ethereum-geth](https://hub.docker.com/r/kunstmaan/ethereum-geth/): An Ubuntu 16.04 image with the Ethereum Go geth binaries installed.
* [kunstmaan/ethereum-geth-devnet](https://hub.docker.com/r/kunstmaan/ethereum-geth-devnet/): The geth image running a devnet
* [kunstmaan/ethereum-geth-testnet](https://hub.docker.com/r/kunstmaan/ethereum-geth-testnet/): The geth image running a testnet
* [kunstmaan/ethereum-geth-console](https://hub.docker.com/r/kunstmaan/ethereum-geth-console/): The geth image with two helper commands to connect to the test or devnet


## Running

Use this [docker-compose.yml](https://github.com/Kunstmaan/docker-ethereum/blob/master/docker-compose.yml) and run:

```
docker-compose up -d
```

## Connecting to an image

Run `docker ps`to find the name of the container and attach to it by running `docker attach <containername>`

## 追记
* docker-machine
```
docker-machine create --driver=parallels geth
docker-machine start geth
eval $(docker-machine env geth)
docker-machine stop geth
```
* docker-compose
```
docker-compose up -d
docker-compose down
docker-compose exec devnet sh
docker attach dockerethereum_devnet_1
^+pq
```
* geth
```
geth attach rpc:http://10.211.55.11:8545
```
* Mist
```
/Applications/Mist.app/Contents/MacOS/Mist --rpc http://10.211.55.11:8545
```
## linux 命令
* 插看端口
```
sudo netstat -apn
nc -v 10.211.55.7 8545
```
