## Utilització

    docker build -t nomImatge .

### Si s'ha especificat CMD ["/bin/bash"] podem cridar-lo així i s'executarà el bash sol.

    docker run --name nomContenidor -h nomContenidor -it nomImatge

### Sinó, caldrà afegir-ho

    docker run --name nomContenidor -h nomContenidor -it nomImatge /bin/bash

### Per iniciar el contenidor de ldap com a deamon, caldrà iniciar-lo de la següent manera
  
    docker run --name nomContenidor -h nomContenidor -it -d nomImatge

### Per executar en una altra consola el bash d'un contenidor
  
    docker exec -it nomContenidor /bin/bash
