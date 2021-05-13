[@dwsclass](https://github.com/dwsclass) dws-ops-004-docker

###### **_ DWSCLASS - OPS - DOCKER _**

**Work with docker && containers.** 
 
 **__________________________**
 
 First pull following image:
```
1 - docker pull nginx:1.20.0
```

## **Question 1:**
 1 - Specify what version of Docker this image was made with?

Answer:
```
 1 - docker image inspect nginx:1.20.0 | jq .[0].DockerVersion
```
**Result:** 19.03.12

**__________________________**

## **Question 2:**
 1 - What ports it exposes?


Answer:
```
1 - docker image inspect nginx:1.20.0 | jq .[0].Config.ExposedPorts
```
**Result:** {
              "80/tcp": {}
            }

**__________________________**

## **Question 2:**
 1 - What ports it exposes?


Answer:
```
1 - docker image inspect nginx:1.20.0 | jq .[0].Config.ExposedPorts
```
**Result:** {
              "80/tcp": {}
            }
**__________________________**

## **Question 3:**
 1 - Save nginx:1.20.0 image with 'nginx.tar.gz' name and then load with this name : 'nginx:v1.20.0-test'

Answer:
```
1 - docker image save -o nginx.tar.gz nginx:1.20.0
2 - docker rmi -f nginx:1.20.0
3 - docker image load -i nginx.tar.gz
4 - docker tag nginx:1.20.0 nginx:v1.20.0-test
5 - docker rmi -f nginx:1.20.0

```

**__________________________**

## **Question 4:**
 1 - Create a new container based on the previous image and run on 8081 port.
 2 - How many processes does this container consist of?

Answer:
```
1 - docker run --rm -d --name nginx -p 8081:80 nginx:v1.20.0-test
2 - docker top nginx
```
**Result:** 5



