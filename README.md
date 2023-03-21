uclalib_role_libguidesindexer
=========

This Ansible role deploys the LibGuides Indexer application onto a RHEL system

Requirements
------------

The Role requires:
* RHEL >= 7
* Python >= 3.8

Role Variables
--------------

* `libguider_repo`: URL to the LibGuider GitHub repository
* `libguides_indexing_scripts_repo`: URL to the LibGuides indexing script repository
* `libguides_base_install_path`: Defines the base install path for the LibGuides files
* `libguides_user`: Defines the user that will run the LibGuides scripts
* `libguider_site_id`: Defines the SpringShare LibGuides site ID
* `libguide_api_key`: Defines the SpringShare LibGuides API Key
* `libguides_elasticsearch_url`: URL to the Elasticsearch Index where the LibGuides indexer will connect
* `elasticsearch_api_key`: Defines the Elasticsearch API key
* `libguides_index_env`: Defines the LibGuides Indexer environment (must be one of: TEST, STAGE, PROD)
* `libguides_index_test`: Defines the name of the test elasticsearch index
* `libguides_index_stage`: Defines the name of the stage elasticsearch index
* `libguides_index_prod`: Defines the name of the prod elasticsearch index
* `libguides_cron_minute`: Defines the minute the cron should run
* `libguides_cron_hour`: Defines the hour the cron should run
* `path_to_pip_exec`: Defines the path to the python pip package manager utility


Example Playbook
----------------

```
---

- name: uclalib_libguidesindexer.yml
  become: yes
  become_method: sudo
  hosts: all

  roles:
    - { role: uclalib_role_rhelscl }
    - { role: uclalib_role_libguidesindexer }
```
