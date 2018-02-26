## Utilització
docker build -t nomImatge
docker run --name nomContenidor -h nomContenidor -d nomImatge
docker exec -it nomContenidor /bin/bash
