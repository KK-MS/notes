# docker and virtual


## Docker
### Getting started

No containers running
Try running a container: Copy and paste this command into your terminal and then come back
```
docker run -d -p 80:80 docker/getting-started
```

Command log:

```
PS C:\prj\docker> ls
PS C:\prj\docker> docker run -d -p 80:80 docker/getting-started
Unable to find image 'docker/getting-started:latest' locally
latest: Pulling from docker/getting-started
aad63a933944: Pull complete
b14da7a62044: Pull complete
343784d40d66: Pull complete
6f617e610986: Pull complete
Digest: sha256:d2c4fb0641519ea208f20ab03dc40ec2a5a53fdfbccca90bef14f870158ed577
Status: Downloaded newer image for docker/getting-started:latest
4ccac7cb17c3ed8b5c2c630b042d2ff711198c013a60bb0b270e776a4512217d
PS C:\prj\docker>
```

## Virtual 

different virtual environment
* Virtual box
* VMWare
* Proxmox: https://proxmox.com/en/  (From AH)

## iOS emulator
Helpfull links: https://github.com/kholia/OSX-KVM
