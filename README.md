Test set-up for saltstack using docker.

Building:
=========

  docker build -t local:salt-master salt-master

  docker build -t local:systemd     salt-systemd

  docker build -t local:salt-minion salt-minion

Move salt-docker.conf to /etc and amend paths to where your saltstack states and pillar are.

Put salt-docker in your path.


Running:
========

  salt-docker my-minion-hostname

  docker exec minion bash

  salt-call state.sls some_state

