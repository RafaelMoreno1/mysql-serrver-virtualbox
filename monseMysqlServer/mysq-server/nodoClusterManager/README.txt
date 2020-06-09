cambie las ip por las suyas 
    198.51.100.0 será el primer nodo de datos de MySQL Cluster
        198.51.100.1 será el segundo nodo de datos
            198.51.100.2 será el nodo del servidor de Cluster Manager y MySQL

adnistrador de clústeres debe ser el primer componente lanzado en cualquier clúster MySQL. Requiere un archivo de configuración, pasado como argumento a su ejecutable. Vamos a crear y utilizar el archivo de configuración siguiente: /var/lib/mysql-cluster/config.ini.

En el Droplet de Cluster Manager, cree el /var/lib/mysql-clusterdirectorio donde residirá este archivo:

    sudo mkdir /var/lib/mysql-cluster

    Luego cree y edite el archivo de configuración utilizando su editor de texto preferido:

        sudo nano /var/lib/mysql-cluster/config.ini

        Pegue el siguiente texto en su editor:El Administrador de clústeres debe ser el primer componente lanzado en cualquier clúster MySQL. Requiere un archivo de configuración, pasado como argumento a su ejecutable. Vamos a crear y utilizar el archivo de configuración siguiente: /var/lib/mysql-cluster/config.ini.

        En el Droplet de Cluster Manager, cree el /var/lib/mysql-clusterdirectorio donde residirá este archivo:

            sudo mkdir /var/lib/mysql-cluster

            Luego cree y edite el archivo de configuración utilizando su editor de texto preferido:

                sudo nano /var/lib/mysql-cluster/config.ini

                Pegue el siguiente texto en su editor

sudo ndb_mgmd -f /var/lib/mysql-cluster/config.ini
sudo pkill -f ndb_mgmd

sudo nano /etc/systemd/system/ndb_mgmd.service
sudo nano /etc/systemd/system/ndb_mgmd.service
sudo systemctl daemon-reload
sudo systemctl enable ndb_mgmd
sudo systemctl start ndb_mgmd
sudo systemctl status ndb_mgmd
 sudo ufw allow from 198.51.100.0
sudo ufw allow from 198.51.100.1

