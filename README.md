# Docker Robot framework

```sh
$ docker pull pitchanon/robot-framework
```

## Use Selenium chrome

### Selenium container

Create container with docker images `selenium/standalone-chrome`

```sh
$ docker run -d -p 4444:4444 --name selenium-chrome selenium/standalone-chrome  
```

## Run test

```sh
$ docker run --rm --name robot \
--link selenium-chrome:local \
-v $PWD:/acceptance_tests \
-w /acceptance_tests pitchanon/robot-framework \
--exitonfailure -v ENV:uat -v remote_url:http://local:4444/wd/hub .
```
