# Sample hack (lang) project

https://docs.hhvm.com/hack/getting-started/starting-a-real-project

## Typechecker
```
hh_client
```
Must first have .hhconfig at repo root

## Run hack file
```
hhvm src/first.hack
```

## Executable
```
chmod +x bin/square_some_things.hack
bin/square_some_things.hack
```

## Linting
```
vendor/bin/hhast-lint
```
Config file: hhast-lint.json

## Autoload
Regenerate the autoloadmap (with hh-autoload) to add classes to autoloadmap. Used to resolve exceptions about reflected classes not existing.

```
vendor/bin/hh-autoload
```
 
## Unit test
```
vendor/bin/hacktest tests/
```

## Developing from a docker container

A workaround when developing on a windows workstation.
https://medium.com/@potatowagon/develop-hack-lang-projects-with-vscode-on-windows-host-with-linux-docker-container-ce70335c01a2

Use docker toolbox to run a ready made image with everything all set up
```
docker pull potatowagon/hhvm-vscode
docker run -it -e "DISPLAY=192.168.99.1:0.0" hhvm-vscode bin/bash
```
Replace `192.168.99.1` with your docker host IP. 

Once container is started
```
code --user-data-dir=/home/vscode-user /home/hack
```

To exit and stop container
```
exit
```

To find stopped container id
```
docker ps -a
```

To resume stopped container
```
docker start <container id>
docker exec -it <container id> bin/bash
```
