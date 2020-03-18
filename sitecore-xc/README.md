## Get Started with Docker and Sitecore JSS 9.3 and JSS 13

## Step 1 Create the necessary images and containers

```
# Clone official repo

git clone https://github.com/Sitecore/docker-images

# Build Images 
.\Build.ps1 -IncludeJSS

# Veryfy you got all the images that you need
docker image ls | Select-String "jss"

# sitecore-xp-jss-sqldev                      
# sitecore-xp-jss-standalone                  
# sitecore-xp-jss-cd                           
# sitecore-xm-sxa-jss-sqldev                   
# sitecore-xm-sxa-jss-cm                       
# sitecore-xm-sxa-jss-cd                       
# sitecore-xm-jss-sqldev                       
# sitecore-xm-jss-cm                          
# sitecore-xm-jss-cd   
```
## Created docker contrainers from the templates file
```
## Build your container
docker-compose -f .\docker-compose.xp.jss.yml up -d

## Tear it down
docker-compose -f .\docker-compose.xp.jss.yml down
```
## Clean up your computer

`Keep in mind you will loose everything that you have been working with, thats why you got deploy folder, those files will stay`

```
docker image prune --all --force

docker rmi $(docker images -a -q) // delete everything
```

## Get Going with GraphQL

for the GraphQl

http://localhost:44001/sitecore/api/graph/items/master

http://localhost:44001/sitecore/api/graph/items/master/ui

## To fix the CORS issue. Copy the web.config locally and modify it.
```
docker cp sitecore-jss_cm_1:C:/inetpub/wwwroot/web.config . 
```