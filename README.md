[![Build Status](https://travis-ci.org/CSCfi/ansible-role-cuda.svg)](https://travis-ci.org/CSCfi/ansible-role-cuda)
[![Galaxy Role](https://img.shields.io/badge/ansible--galaxy-cuda-blue.svg)](https://galaxy.ansible.com/CSCfi/cuda/)

ansible-role-cuda
=========

Installs CUDA

Tested with Tesla P100, K80, Tesla M40, CentOS7, Ubuntu 16.04, Cuda 7.5 and 8.0

Requirements
------------

Outbound access to http://developer.download.nvidia.com/compute/cuda/repos/

Role Variables
--------------

    cuda_packages:
     - cuda
    cuda_restart_node_on_install: True
    cuda_bash_profile: True

- cuda_packages: List that can be updated to include more packages that are installed after nvidia cuda repo is installed, or to a specific cuda package (e.g. `cuda-7-5`)
- cuda_restart_node_on_install: restarts the system when packages are installed or updated


Example Playbook
----------------

`playbook.yml`:

    - hosts: cuda
      roles:
        - narfman0.cuda

`inventory`:

    [cuda]
    cuda1

Example Errors
--------------

This error means you are not using a supported OS (like Ubuntu 17.04 which does not have a cuda URL)
<pre>
   "msg": "No file was found when using with_first_found. Use the 'skip: true' option to allow this task to be skipped if no files are found"
</pre>

License
-------

MIT
