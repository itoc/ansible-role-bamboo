Ansible Role for Bamboo
=======================

[![Build Status](https://travis-ci.org/pantarei/ansible-role-bamboo.svg?branch=master)](https://travis-ci.org/pantarei/ansible-role-bamboo)
 [![GitHub tag](https://img.shields.io/github/tag/pantarei/ansible-role-bamboo.svg)](https://github.com/pantarei/ansible-role-bamboo)
 [![GitHub license](https://img.shields.io/github/license/pantarei/ansible-role-bamboo.svg)](https://github.com/pantarei/ansible-role-bamboo/blob/master/LICENSE)
 [![Ansible Role](https://img.shields.io/ansible/role/5984.svg)](https://galaxy.ansible.com/detail#/role/5984)

Ansible Role for Atlassian Bamboo Installation.

Requirements
------------

This role require Ansible 1.9 or higher.

This role was designed for Ubuntu Server 14.04 LTS.

Role Variables
--------------

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">parameter</th>
<th align="left">required</th>
<th align="left">default</th>
<th align="left">choices</th>
<th align="left">comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">bamboo_archive</td>
<td align="left">yes</td>
<td align="left">/tmp/atlassian-bamboo-5.9.7.tar.gz</td>
<td align="left"></td>
<td align="left">Download archive filename for cache during (re)install.</td>
</tr>
<tr class="even">
<td align="left">bamboo_catalina</td>
<td align="left">yes</td>
<td align="left">/usr/share/bamboo</td>
<td align="left"></td>
<td align="left">Location for the Bamboo installation directory.</td>
</tr>
<tr class="odd">
<td align="left">bamboo_connector_port</td>
<td align="left">yes</td>
<td align="left">8085</td>
<td align="left"></td>
<td align="left">Bamboo Apache Tomcat connector port.</td>
</tr>
<tr class="even">
<td align="left">bamboo_home</td>
<td align="left">yes</td>
<td align="left">/var/lib/bamboo</td>
<td align="left"></td>
<td align="left">Location for the Bamboo home directory.</td>
</tr>
<tr class="odd">
<td align="left">bamboo_jvm_maximum_memory</td>
<td align="left">yes</td>
<td align="left">1024m</td>
<td align="left"></td>
<td align="left">Bamboo JVM maximum memory usage.</td>
</tr>
<tr class="even">
<td align="left">bamboo_jvm_minimum_memory</td>
<td align="left">yes</td>
<td align="left">512m</td>
<td align="left"></td>
<td align="left">Bamboo JVM minimum memory usage.</td>
</tr>
<tr class="odd">
<td align="left">bamboo_jvm_support_recommended_args</td>
<td align="left">no</td>
<td align="left">-Datlassian.plugins.enable.wait=300</td>
<td align="left"></td>
<td align="left">Atlassian Support recommended JVM arguments.</td>
</tr>
<tr class="even">
<td align="left">bamboo_pass</td>
<td align="left">yes</td>
<td align="left">yav0nooR</td>
<td align="left"></td>
<td align="left">Password for Bamboo system user.</td>
</tr>
<tr class="odd">
<td align="left">bamboo_proxy_name</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"></td>
<td align="left">Pass value as <code>proxyName</code> to <a href="https://github.com/pantarei/ansible-role-bamboo/blob/master/templates/usr/share/bamboo/conf/server.xml.j2">template</a>.</td>
</tr>
<tr class="even">
<td align="left">bamboo_scheme</td>
<td align="left">no</td>
<td align="left"><code>null</code></td>
<td align="left"><ul>
<li><code>null</code></li>
<li>http</li>
<li>https</li>
</ul></td>
<td align="left">Install Bamboo in standalone mode if <code>null</code>, or integrating with Apache using HTTP if <code>http</code>, or integrating with Apache using HTTPS if <code>https</code>.</td>
</tr>
<tr class="odd">
<td align="left">bamboo_server_port</td>
<td align="left">yes</td>
<td align="left">8007</td>
<td align="left"></td>
<td align="left">Bamboo Apache Tomcat server port.</td>
</tr>
<tr class="even">
<td align="left">bamboo_sha256</td>
<td align="left">yes</td>
<td align="left">4efd7ed85e1b0886ff262ed388aa9049651b2bccffa60bdc59db73fb1609982f</td>
<td align="left"></td>
<td align="left">Download archive sha256 checksum for cache during (re)install.</td>
</tr>
<tr class="odd">
<td align="left">bamboo_upgrade</td>
<td align="left">no</td>
<td align="left"><code>false</code></td>
<td align="left"><ul>
<li><code>true</code></li>
<li><code>false</code></li>
</ul></td>
<td align="left">If <code>true</code>, trigger upgrade by stop existing Bamboo service, purge existing Bamboo installation direcoty before normal tasks.</td>
</tr>
<tr class="even">
<td align="left">bamboo_url</td>
<td align="left">yes</td>
<td align="left">https://downloads.atlassian.com/software/bamboo/downloads/atlassian-bamboo-5.9.7.tar.gz</td>
<td align="left"></td>
<td align="left">URL for download archive.</td>
</tr>
<tr class="odd">
<td align="left">bamboo_user</td>
<td align="left">yes</td>
<td align="left">bamboo</td>
<td align="left"></td>
<td align="left">Username for Bamboo system user.</td>
</tr>
</tbody>
</table>

Dependencies
------------

-   [hswong3i.java](https://galaxy.ansible.com/detail#/role/5971)

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: hswong3i.bamboo, bamboo_user: 'bamboo', bamboo_pass: 'yav0nooR', bamboo_upgrade: 'false' }

License
-------

-   Code released under [MIT](https://github.com/hswong3i/ansible-role-bamboo/blob/master/LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

