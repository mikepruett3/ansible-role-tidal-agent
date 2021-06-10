Ansible Role: Tidal Workload Automation agent
=========

Ansible role to install [Tidal Workload Automation](https://www.tidalsoftware.com) agent on Linux Servers.

Requirements
------------

The role does not require anyting to run on RHEL and its derivatives. It will install OpenJDK to satisfy the Tidal Workload Automation agents Java requirement. This role also assumes that you have the software package located on a web server somewhere in your environment.

Role Variables
--------------

Available variables are listed below, along with default values ```(see defaults/main.yml)```:

``` yaml
software_url: "http://www.example.org"
package_name: "tidal-agent-installer.zip"
```

```software_url``` **(Required)** The URL that hosts the Installer package. This should be either **http** or **https**.

```package_name``` **(Required)** The Installer package name.

Role variables can be stored with the hosts.yaml file, or in the main variables file.

Dependencies
------------

Any Java or JDK (including OpenJDK and OracleJDK). Role will install OpenJDK by default. Run update-alternatives to change the default java after role installation.

Example Playbook
----------------

``` yaml
    - hosts: servers
      roles:
         - role: mikepruett3.rapid7_agent
           vars:
             software_url: "http://www.example.org"
             package_name: "tidal-agent-installer.zip"
```

License
-------

MIT

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3/ansible-role-tidal-agent)
