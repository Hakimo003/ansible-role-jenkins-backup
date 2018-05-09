## Ansible Role: Jenkins-Backup

This Ansible role for backup jenkins configuration.


## Requirements

* Installed Jenkins master
* exclusive-execution plugin for jenkins
* /home/admin/.jenkins/backup

## Backup Scope

The following files will be included into the backup archive:

* /home/admin/.jenkins/jenkins-jobs/*.xml
* /home/admin/.jenkins/jobs/*.xml
* /home/admin/.jenkins/jobs/*/*.xml
* /home/admin/.jenkins/userContent/*.xml
* /home/admin/.jenkins/users/*
* /home/admin/.jenkins/nodes/*
* /home/admin/.jenkins/plugins/*.jpi
* /home/admin/.jenkins/*.xml

## Role Variables

    backup_jenkins_home: "/home/admin/.jenkins"

The Jenkins home

    backup_script_dir: "{{ backup_jenkins_home }}/scripts/"

The default dir for the scripts

    backup_dir: "{{ backup_jenkins_home }}/backup/config"

The default dir for all the backup files

    backup_file_name: "jenkins-config-backup_`date +\"%Y%m%d%H%M%S\"`.tar.gz"

The default file name for any backup

## Dependencies

None

## Example Playbook
```

- hosts:
    - localhost
  become: True
  roles:
    - ansible-role-jenkins-backup

```


## License

HACH

## Author Information

This role was created in 2018 by [CHRIFI ALAOUI Hakim](https://github.com/Hakimo003/ansible-role-jenkins-backup)
