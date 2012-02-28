OMERO.web EMDB
==============
Open Microscopy Environment EMDB OMERO.web extension application.

Requirements
============

* OMERO 4.4.0 or later

Development Installation
========================

Clone the repository in to your OMERO.web installation:

    cd components/tools/OmeroWeb/omeroweb/
    git clone git://github.com/openmicroscopy/webemdb.git
    path/to/bin/omero config set omero.web.apps '["webemdb"]'

Now start up OMERO.web as normal in your development environment.

Production Installation
=======================

Install the latest version of OMERO.server and OMERO.web and then:

    cd $OMERO_HOME/lib/python/omeroweb
    wget -O master.zip https://github.com/openmicroscopy/webemdb/zipball/master
    unzip master.zip
    mv openmicroscopy-webemdb-* webemdb
    path/to/bin/omero config set omero.web.apps '["webemdb"]'

You can then configure OMERO.web EMDB as per normal:

* http://trac.openmicroscopy.org/ome/wiki/OmeroWebEmdb

In order to enable the EMAN2 and caching functionality required for some
pages of OMERO.web EMDB webemdb, you need to install EMAN2 so that:

    from EMAN2 import *

produces no errors and then configure the following options:

    $ bin/omero config set omero.web.use_eman2 True
    $ bin/omero config set omero.web.cache_backend 'file:///var/tmp/django_cache'

