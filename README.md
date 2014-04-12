apli_template
=============

Template for quick bootstrapping of web applications

Serving
-------

* system-wide nginx with an enabled site config that includes * from a dir of enabled apli configs
* system-wide circus with an [include-dir](https://circus.readthedocs.org/en/latest/for-ops/configuration/) for a dir of enabled apli watchers
* per apli
  * chaussette running with fastgevent backend

Deploying
---------

For each apli:

* virtualenv
  * ipython
    * tornado, jinja2, pyzmq
  * chaussette
  * gevent
  * sqlalchemy, alembic


Installation and Setup
----

This should be handled via apli_cnc, but for now:

``` sh

git clone
cd apli_template
virtualenv --no-site-packages .
. bin/activate
pip install -r requirements.txt

chaussette --backend fastgevent --host 0.0.0.0 --port 8080
```

