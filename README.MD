# My workstation
[![Ansible Lint](https://github.com/nleiva/ansible-workstation/actions/workflows/ansible_lint.yml/badge.svg)](https://github.com/nleiva/ansible-workstation/actions/workflows/ansible_lint.yml)

I run RHEL9, which you can [get for free](https://developers.redhat.com/articles/faqs-no-cost-red-hat-enterprise-linux#general).

The following playbook installs the software I need and customizes the enviroment for any time I need to go back to square one.

## Dependencies

```
$ ansible-galaxy collection install community.general --upgrade
```

## Running

Need a local user and `become` password. All inputs are in the [inputs.yml](inputs.yml) file.

```
$ ansible-playbook workstation.yml -vK -e "ansible_user=nleiva"
```

Use of tags example: Don't re-install RHEL additional repositories and skip RPM Fusion.

```
$ ansible-playbook workstation.yml -vK -e "ansible_user=nleiva" --skip-tags "rhel_repo, fusion_repo"
```

## Running on a new install

If you want to run it on a fresh system without Ansible.

```
$ python3 -m pip install --user ansible-core
$ python3 -m pip show ansible-core
```
