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
  
