# Sitecore Docker Notes

Few Easy steps

## Clone
```
git clone https://github.com/Sitecore/docker-images/
```
## Enter the directory
```
cd docker-images
```
## Build the images
```
.\Build.ps1
```
## Set license location
```
.\Set-LicenseEnvironmentVariable.ps1 -Path D:\license\license.xml
```
## Create a docker image from the directory
```
cd .\windows\tests\9.3.x

docker-compose -f .\docker-compose.xp.yml up

http://localhost:44001/sitecore/

docker-compose -f .\docker-compose.xp.yml down
```

## Additional commands
```C#
docker container ls // list containers

docker images // list docker images

docker images purge // purge images

docker rmi $(docker images -a -q) // delete everything
```

