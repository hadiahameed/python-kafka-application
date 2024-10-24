## Install JDK:

```brew install openjdk@17```

## Install Kafka:

```brew install kafka```

## Start Zookeeper:  
```zookeeper-server-start /usr/local/etc/kafka/zookeeper.properties```

## Start kafka server:  

## Create kafka topic:  
```kafka-topics --create --topic my-first-topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1```




## Mac was denying permission to add PATH to brew in the source file:
```sudo chown $(whoami) /Users/hadiahameed/.zshrc```

## After I installed kafka, it couldn't find kafka directory
```sudo mkdir -p /usr/local/etc/kafka```  
```sudo chown -R $(whoami) /usr/local/etc/kafka```  

## Zookeeper failed to start:
```nano /usr/local/etc/kafka/zookeeper.properties```  

Copy the following properties to the nano file:  
```
# The directory where the snapshot is stored.
dataDir=/usr/local/var/lib/zookeeper

# The port at which the clients will connect
clientPort=2181

# Enable auto-purge of old data
autopurge.snapRetainCount=3
autopurge.purgeInterval=1  

```

## Running jupyter in a conda environment

Let's see conda env is called "kafka", run the following commands:  

```conda activate kafka```  

```conda install ipykernel```  

``` python-kafka-application % python -m ipykernel install --user --name kafka --display-name "Python (kafka)" ```