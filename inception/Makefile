all:
	sudo docker-compose -f ./srcs/docker-compose.yaml up -d --build

down:
	sudo docker-compose -f ./srcs/docker-compose.yaml down

clean:
	sudo docker system prune -af
	sudo docker volume rm srcs_mariadb
	sudo docker volume rm srcs_wordpress