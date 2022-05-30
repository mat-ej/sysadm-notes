# PSQL


#### Installation using docker
    docker run --name postgresql -e POSTGRES_USER=myusername -e POSTGRES_PASSWORD=mypassword -p 5432:5432 -v /data:/var/lib/postgresql/data -d postgres
    docker ps -a
    docker start postgresql
    docker inspect postgresql -f "{{json .NetworkSettings.Networks }}"
    
    # remove unnecessary databases
    alter database template0 is_template false;


#### CLI through ssh tunnel
    ssh -L 1111:172.16.2.15:5432 uhrinmat@ida-postgres
    psql -h localhost -p 1111 -U uhrinmat bet

- 1111 - local port
- 172.16.2.15:5432 - remote IP + port
- uhrinmat - username 
- ida-postgres - SSH frontend