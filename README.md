# satellite_content_publish
Code for automating Satellite content publishing after sync

The publich_content.yml file is the original monolithic playbook. You can run just this or main.yml with the same results.

The playbook(s) are designed to be run daily, after a sync has been completed on the Satellite repositories.

The plan is that all updated repositories are gathered, then the content views which contain them plus any composite content views they are in are evaluated and checked to make sure they haven't been updated in the last day and that composite views are not configured to auto-publish, then the remainder are published.

You need foreman_ansible_modules installed and working - see https://theforeman.org/plugins/foreman-ansible-modules/
The simplest way is to clone them into this working directory from git: https://github.com/theforeman/foreman-ansible-modules

You will also need the Pythin apypie module installed. Install it under Python3 as the ansible.cfg specifies this as the version to use.
