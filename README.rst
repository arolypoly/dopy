Digital Ocean API Python Wrapper
================================

Inspired by `dop <https://github.com/ahmontero/dop>`_.

Installation
============

.. code-block:: bash
    
    # pip install dopy

Getting Started
===============

To interact with Digital Ocean, you first need .. a digital ocean account with 
valid API keys.

Keys can be set either as Env variables, or within the code.

For API v.2.

.. code-block:: bash

    # export DO_API_VERSION='2'
    # export DO_API_TOKEN='api_token'

.. code-block:: pycon

    >>> from dopy.manager import DoManager
    >>> do = DoManager(None, 'api_token', api_version=2)


For API v.1.

.. code-block:: bash
    
    # export DO_CLIENT_ID='client_id'
    # export DO_API_KEY='long_api_key'

.. code-block:: pycon

    >>> from dopy.manager import DoManager
    >>> do = DoManager('client_id', 'long_api_key')

Methods
=======

The methods of the DoManager are self explanatory; ex.

.. code-block:: pycon

    >>> do.all_active_droplets()
    >>> do.show_droplet('12345')
    >>> do.destroy_droplet('12345')
    >>> do.all_regions()
    >>> do.all_images()
    >>> do.all_ssh_keys()
    >>> do.sizes()
    >>> do.all_domains()
    >>> do.new_droplet('new_droplet', 66, 1601, 1)

The methods for v.2 API are similar, the only difference
is using names instead of IDs for domains and slugs for
sizes, images and datacenters; ex.

.. code-block:: pycon

    >>> do.show_domain('exapmle.com')
    >>> do.new_droplet('new_droplet', '512mb', 'lamp', 'ams2')

Methods for Floating IPs are:

.. code-block:: pycon

    >>> do.all_floating_ips()
    >>> do.new_floating_ip(droplet_id, region)
    >>> do.destroy_floating_ip(ip_addr)
    >>> do.assign_floating_ip(ip_addr)
    >>> do.unassign_floating_ip(ip_addr)
    >>> do.list_floating_ip_actions(ip_addr)
    >>> do.get_floating_ip_action(ip_addr, action_id)
                                    


TODO
====

See github issue list - post if any needed

https://github.com/devo-ps/dopy/issues
