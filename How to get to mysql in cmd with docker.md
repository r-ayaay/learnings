#docker #mysql #sql #cmd 

1. docker exec -it [docker-container] /bin/bash
		How to find docker container name?
			in the root, type “_docker ps”_

2. mysql {db_name} -u {username} -p
		Then you will be prompted to place a password.
			How do you find these stuff?
				.docker-compose.yml

mysql HR_DB -u user -p

3. And then you can run sql queries normally

Bash alies

**Format** 

alias my_alias=“alias”