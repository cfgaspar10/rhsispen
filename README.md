Docker RHSISPEN Django_MariaDB_nginx_ versão desenvolvimento
=========
   
   ### Instalação Docker
   
   $ sudo apt-get update
   
   $ sudo apt install docker.io
   
   $ sudo systemctl start docker
   
   $ docker --version
   
   $ sudo systemctl enable docker
   
   $ sudo docker run hello-world
   
   ### Instalação docker-compose
   
   $ sudo apt-get update
   
   $ sudo curl -L https://github.com/docker/compose/releases/download/1.25.3/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
   
   $ sudo chmod +x /usr/local/bin/docker-compose
   
   $ sudo docker-compose --version
   
=========
   
    #Passos para executar a composição dos containers
    $ git clone https://github.com/cfgaspar10/rhsispen.git
    $ cd rhsispen   
    $ sudo docker-compose up -d --build
    $ sudo docker ps
    
    ### Criar crendenciais de acesso.
    $ sudo docker exec -ti rhsispen_app_1 /bin/bash
    $ python manage.py migrate && python manage.py createsuperuser && python manage.py collectstatic
     
    Browser -> [http://localhost/admin](http://localhost/admin)
  
=========
   
   - Acessar o banco de dados MariaDB

   $ docker exec -ti rhsispen_db_1 /bin/bash
   
   $ mysql -h localhost -u root -p
   ##### Inserir senha do banco: 'admin' 
   $ SHOW DATABASES;
