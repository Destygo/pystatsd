.. Python StatsD documentation master file, created by
   sphinx-quickstart on Mon Apr  9 15:47:23 2012.
   You can adapt this file completely to your liking, but it should at
   least contain the root `toctree` directive.

Welcome to Python StatsD's documentation!
=========================================

statsd_ is a friendly front-end to Graphite_. This is a Python client
for the statsd daemon, with added support for tags (as defined in the
Datadog protocol extension).

Forked from https://github.com/jsocol/pystatsd.

Quickly, to use::

    >>> import statsd
    >>> c = statsd.StatsClient('localhost', 8125)
    >>> c.incr('foo')  # Increment the 'foo' counter.
    >>> c.timing('stats.timed', 320)  # Record a 320ms 'stats.timed'.

You can also add a prefix or tags to all your stats::

    >>> import statsd
    >>> c = statsd.StatsClient('localhost', 8125, prefix='foo',
    ... tags={'environment:production'})
    >>> c.incr('bar')  # Will be 'foo.bar' in statsd/graphite.


Installing
----------

The easiest way to install statsd is with pip!

From GitHub::

    $ pip install -e git+https://github.com/jsocol/pystatsd#egg=statsd

Or from source::

    $ git clone https://github.com/jsocol/pystatsd
    $ cd statsd
    $ python setup.py install


Contents
--------

.. toctree::
   :maxdepth: 2

   configure.rst
   types.rst
   timing.rst
   pipeline.rst
   tcp.rst
   reference.rst
   contributing.rst


Indices and tables
------------------

* :ref:`search`

.. _statsd: https://github.com/etsy/statsd
.. _Graphite: https://graphite.readthedocs.io/
