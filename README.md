# ENV/Prerequisites
- cURL — latest version
- Docker — version 17.06.2-ce or greater [DOCKER INSTALLATION](https://github.com/KRIISHSHARMA/DOCKER)
- Docker Compose — version 1.14.0 or greater
- Golang — version 1.11.x [GOLANG INSTALLATION](https://github.com/KRIISHSHARMA/go-installation)
- Nodejs — version 8.x (other versions are not in support yet)
- NPM — version 5.x
- Python 

- Check Docker and Docker Compose versions / if installed properly
  
![image](https://github.com/KRIISHSHARMA/hyperledger-fabric-installation/assets/86760658/c31b4447-25cd-4fc4-8a0b-23b3c4a7d9b6)

# Installing Samples, Binaries and Docker Images

- `mkdir fabric`
- `cd fabric`
- To get the install script:

```sh
curl -sSLO https://raw.githubusercontent.com/hyperledger/fabric/main/scripts/install-fabric.sh && chmod +x install-fabric.sh
```
- To pull the Docker containers and clone the samples repo, run one of these commands for example

``` sh
./install-fabric.sh docker samples binary
or
./install-fabric.sh d s b
```

## Errors faced : 
- if you get permission denied error , become a super user `sudo su` then again try above cmd

- If done correctly :

![image](https://github.com/KRIISHSHARMA/hyperledger-fabric-installation/assets/86760658/a5d87571-b4ff-4e94-8484-d17463dda684)

# Running a test network

- `cd fabric-samples/test-network` (inside fabric direc)
  
- In this directory, you can find an annotated script, network.sh, that stands up a Fabric network using the Docker images on your local machine
- From inside the test-network directory, run the following command to remove any containers or artifacts from any previous runs:
``` sh
./network.sh down
```
You can then bring up the network by issuing the following command. You will experience problems if you try to run the script from another directory:
``` sh
./network.sh up
```
- OR you can also bring up the network with Certificate Authorities.
``` sh
./network.sh up -ca
```

![image](https://github.com/KRIISHSHARMA/hyperledger-fabric-installation/assets/86760658/5d2797cf-4d68-4b02-9b1d-91ec4d11cac6)

# Creating a Channel 
- Error in creating a channel (have to troubleshoot)
``` sh
Error: Post "https://localhost:7053/participation/v1/channels": dial tcp 127.0.0.1:7053: connect: connection refused

Channel 'mychannel' created
Joining org1 peer to the channel...
Using organization 1
+ peer channel join -b ./channel-artifacts/mychannel.block
+ res=1
+ peer channel join -b ./channel-artifacts/mychannel.block
+ res=1
+ peer channel join -b ./channel-artifacts/mychannel.block
+ res=1
+ peer channel join -b ./channel-artifacts/mychannel.block
+ res=1
Error: error getting endorser client for channel: endorser client failed to connect to localhost:7051: failed to create new connection: connection error: desc = "transport: error while dialing: dial tcp 127.0.0.1:7051: connect: connection refused"
After 5 attempts, peer0.org1 has failed to join channel 'mychannel' 
```
- Solution : was running old version of HLF (2.2) 

- You can use the network.sh script to create a channel between Org1 and Org2 and join their peers to the channel. Run the following command to create a channel with the default name of mychannel:
``` sh
./network.sh createChannel
```

# Deploying a smart contract to a channel


- If done correctly , you will see following message in logs :

![image](https://github.com/KRIISHSHARMA/hyperledger-fabric-installation/assets/86760658/abcea161-beca-4fab-ae80-f4bfa574b7b8)

