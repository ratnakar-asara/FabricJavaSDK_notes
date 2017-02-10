##Steps to test end-to-end Java test

###Pre-requsite:
1. Generate the below images with `make docker` as per the commit levels mentioned below

  *Image   ----   commit level*
  -----------------------------------------------------------
  fabric	----    5d9e4ede298ab646ac918dc5b034c7d319dd1d9a

  fabric-ca   ----    bf8fb4d5e497217cd6125025830aa6870de442aa

2. Install JDK 1.8 or above
3. Install Apache Maven

   Follow the instructions [here](https://github.com/hyperledger/fabric-sdk-java#compiling)

###Steps to run End - to -End Java SDK test

```
git clone https://github.com/hyperledger/fabric-sdk-java.git

cd fabric-sdk-java

export GOPATH=$PWD/src/test/fixtures

cd /opt/gopath/src/github.com/hyperledger/fabric-sdk-java/src/test/fixture/src

rm -rf  /tmp/keyValStore*; rm -rf  /tmp/kvs-hfc-e2e ~/test.properties; rm -rf /var/hyperledger/*  ; docker-compose up -d

cd /opt/gopath/src/github.com/hyperledger/fabric-sdk-java/

mvn install

```

Execute end-to-end testcase

```
mvn failsafe:integration-test -DskipITs=false
```
