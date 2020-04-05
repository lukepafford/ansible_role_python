python
=========
The goal is to provide a reliable way of ensuring a specific Python executable
exists at a known path, which can be used as the `executable` argument for the 
`pip` module.

You do not need to worry about setting any 'become' values. The role will
install the package correctly for the `python_user` variable.


The role downloads the `python_version` (Default: 3.8.2),
for the `python_user` (Default: `ansible_user_id`) into the 
`python_downloadDir` (Default: `ansible_user_dir`/Downloads) directory.

The archive is then compiled and installed into the 
`python_installDir` (Default: `ansible_user_dir`/Python-`python_version`).


The Python executable will be located at "`python_installDir`/bin/python3"


Requirements
-------------
The user must have sudo access to install system level library dependencies 
in order to build Python.


Role Variables
--------------

* python_version
* python_user
* python_downloadDir
* python_installDir

Dependencies
------------
None

Example Playbook
----------------
- hosts: servers
  roles:
		- python

License
-------
BSD

Author Information
------------------
Email: lukepafford@gmail.com
