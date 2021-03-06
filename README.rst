===================
Dogpile Elasticache
===================

Dogpile backend for AWS Elasticache Memcache service. Uses
`pymemcache <https://github.com/Pinterest/pymemcache>`_ to connect to
nodes of the Elasticache cluster with
`auto-discovery <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/AutoDiscovery.html>`_.

* PyPI: https://pypi.python.org/pypi/dogpile_elasticache
* Github: https://github.com/ludia/dogpile_elasticache


Usage
=====

Install with pip::

   $ pip install dogpile_elasticache

Configure a region to use dogpile_elasticache::

   from dogpile.cache import make_region

   region = make_region().configure(
       'elasticache_pymemcache',
       arguments = {
           'configuration.host': 'XX.XX.cfg.use1.cache.amazonaws.com',
           'configuration.port': '11211',
       }
   )


Development
===========

Install environment::

   $ pip install -e .[test]

Run tests (with Nose)::

   $ nosetests

Release (with zest.releaser)::

   $ fullrelease


Thanks
======

Thanks to https://github.com/gusdan/django-elasticache for the cluster
discovery code.
