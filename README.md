# Riak Dev Cluster for OS X

Easily run a [Riak](http://wiki.basho.com/Riak.html) cluster on OS X.

* By default, 3 nodes are started
* The names of the nodes are riak[1-3]@127.0.0.1
* The HTTP port of riak1 is 11098: <http://127.0.0.1:11098>
* Riak Control (Admin UI) is available here: <http://127.0.0.1:11098/admin>
* All nodes use the [eleveldb](http://wiki.basho.com/LevelDB.html) storage backend
  to support [secondary indexes](http://wiki.basho.com/Secondary-Indexes.html)
* [Yokozuna]()is activated
* [Data Types]() are included.  
* To adjust the number of nodes (1-5), edit the `NUM_NODES` constant in `Rakefile`
* See riak[1-5]/etc/app.config for the other ports and settings

## Getting started

Clone the repository:

    $ git clone git://github.com/xing/riak-dev-cluster.git

Go to the riak-dev-cluster directory:

    $ cd riak-dev-cluster

There is a bootstrap command available that installs, starts and joins the riak cluster in one go:

    $ rake bootstrap

## Control commands

Start all nodes:

    $ rake start

Join all nodes as a cluster (only needed once):

    $ rake join

Stop all nodes:

    $ rake stop

Clear all data and restart the cluster:

    $ rake clear

## Other commands

Install riaknostic (the `riak-admin diag` command):

    $ rake install_riaknostic

See all available commands:

    $ rake -T

## Note

Depending on your erlang cookie, you may have to use the commands with `sudo`.

## Authors

