# ENV/Prerequisites
- cURL — latest version
- Docker — version 17.06.2-ce or greater [DOCKER INSTALLATION](https://github.com/KRIISHSHARMA/DOCKER)
- Docker Compose — version 1.14.0 or greater
- Golang — version 1.11.x [GOLANG INSTALLATION](https://github.com/KRIISHSHARMA/go-installation)
- Nodejs — version 8.x (other versions are not in support yet)
- NPM — version 5.x
- Python 


# Create a new sudo user

- add new user 'fabric'
``` sh
sudo adduser fabric
```
- Add the user “fabric” to the Sudo groups
``` sh
sudo usermod -aG sudo fabric
```
- Login to “fabric” user
``` sh
su  fabric
```

- add the user to docker group
``` sh
sudo usermod -aG docker fabric
```

- Logout using `exit` command and log in again. Check the groups' user is part of,using `id -nG` command.
![image](https://github.com/KRIISHSHARMA/hyperledger-fabric-installation/assets/86760658/a34b67c2-90e1-4cee-a952-d0c0265728d5)

- Check Docker and Docker Compose versions / if installed properly
  
![image](https://github.com/KRIISHSHARMA/hyperledger-fabric-installation/assets/86760658/c31b4447-25cd-4fc4-8a0b-23b3c4a7d9b6)

# Installing Samples, Binaries and Docker Images

- download the latest production release.
  
``` sh
curl -sSL http://bit.ly/2ysbOFE | bash -s
```

- OR install a specific version
``` sh
curl -sSL http://bit.ly/2ysbOFE | bash -s -- 1.4.1 1.4.1 0.4.15
```

## Errors faced : 
- if you get permission denied error , become a super user `sudo su` then again try above cmd

- If done correctly :

![image](https://github.com/KRIISHSHARMA/hyperledger-fabric-installation/assets/86760658/a5d87571-b4ff-4e94-8484-d17463dda684)

# Testing the fabric Network

Open the fabric-samples and go to the first-network.
``` sh
cd fabric-samples/first-network
```
- To test it, run the byfn.sh . It is a test script, 
- it first set up the network with 2 organizations org1 and org2 with 2 peers each and an orderer .
``` sh
./byfn.sh up
```
