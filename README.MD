# My workstation

I run RHEL9, which you can [get for free](https://developers.redhat.com/articles/faqs-no-cost-red-hat-enterprise-linux#general).

The following playbook installs the software I need and customizes the enviroment for any time I need to go back to square one.

```
$ ansible-galaxy collection install community.general --upgrade
```

```
$ ansible-playbook workstation.yml -vK -e "ansible_user=nleiva"
```

```
$ python3 -m pip install --user ansible-core
$ python3 -m pip show ansible-core
```