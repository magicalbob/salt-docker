Test set-up for saltstack using docker.

Building:
=========

    docker-compose build

Edit docker-compose.yml to set paths of the volume maps, networks etc.

Running:
========

    # Bring up the "machines"
    docker-compose up
    # Register the salt minion(s) with the salt master
    docker exec saltdocker_salt_1 salt-key -Ay
    # Run example ntp state to install ntpd on minion
    docker exec saltdocker_salt_1 salt 'dt-box-01' state.sls ntp

You can combine building and running with `docker-compose up --build`.

