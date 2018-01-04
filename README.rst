========================
Team and repository tags
========================

.. image:: http://governance.openstack.org/badges/openstack-ansible-os_cloudkitty.svg
    :target: http://governance.openstack.org/reference/tags/index.html

.. Change things from this point on

OpenStack-Ansible CloudKitty
############################
:tags: openstack, cloudkitty, cloud, ansible
:category: \*nix

This Ansible role installs and configures OpenStack cloudkitty.

This role will install the following Upstart services:
    * cloudkitty-api
    * cloudkitty-processor

Required Variables
==================
To use this role, define the following variables:

.. code-block:: yaml

    cloudkitty_service_password: "CLOUDKITTY_SERVICE_PASSWORD"
    cloudkitty_rabbitmq_password: "CLOUDKITTY_RABBITMQ_PASSWORD"
    cloudkitty_container_db_password: "CLOUDKITTY_CONTAINER_DB_PASSWORD"
    cloudkitty_galera_address: "CLOUDKITTY_GALERA_ADRESS"
    memcached_servers: 127.0.0.1
    memcached_encryption_key: "some_key"
    # Needed for cloudkitty to locate and connect to the RabbitMQ cluster
    rabbitmq_servers: "10.100.100.2"
    rabbitmq_use_ssl: true
    rabbitmq_port: 5671
    # Needed to setup the cloudkitty service in Keystone
    keystone_admin_user_name: admin
    keystone_admin_tenant_name: admin
    keystone_auth_admin_password: "SuperSecretePassword"
    keystone_service_adminuri_insecure: false
    keystone_service_internaluri_insecure: false
    keystone_service_internaluri: "http://1.2.3.4:5000"
    keystone_service_internalurl: "{{ keystone_service_internaluri }}/v3"
    keystone_service_adminuri: "http://5.6.7.8:35357"
    keystone_service_adminurl: "{{ keystone_service_adminuri }}/v3"
