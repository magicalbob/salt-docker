Test set-up for saltstack using docker.

Building:
=========

    docker build -t local:salt-master salt-master
    docker build -t local:systemd     salt-systemd
    docker build -t local:salt-minion salt-minion

Edit docker-compose.yml to set paths of the volume maps, networks etc.

Running:
========

    docker-compose up
    docker exec saltdocker_salt_1 salt-key -Ay


