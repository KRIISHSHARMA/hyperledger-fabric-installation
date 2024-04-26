# ENV/Prerequisites
- cURL — latest version
- Docker — version 17.06.2-ce or greater
- Docker Compose — version 1.14.0 or greater
- Golang — version 1.11.x
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
