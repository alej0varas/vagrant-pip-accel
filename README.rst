=============
 pip cache's
=============

Shared pip download cache
=========================

vagrant file and instruction to host pip-proxy(https://github.com/wil/pip-proxy)

Install
-------
  vagrant up

  vagrant ssh

  sudo apt-get update

  sudo apt-get install git python-pip -y

  sudo pip install gunicorn

  git clone https://github.com/wil/pip-proxy.git

  mkdir ~/pip_proxy_cache

  cd pip-proxy

  PIPP_CACHE_DIR=~/pip_proxy_cache gunicorn -b 0.0.0.0:8008 --timeout=600 pipproxy.wsgi -D

Usage
-----
A forwarded port is set in Vagrantfile that allows you to use

  export PIP_INDEX_URL=http://localhost:8080/simple

from your host or inside another virtual machine

  export PIP_INDEX_URL=http://10.0.2.2:8080/simple
