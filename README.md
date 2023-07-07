# Ansible Open OnDemand example

This is a very simple example of a starter playbook to install
and configure Open OnDemand.

This repository is meant to just be an example of how to get started
with ansible and the Open OnDemand role that OSC provides.

Install the role through galaxy with this command:

```
ansible-galaxy install osc.open_ondemand
```

## Running

Use and insepect the `run` script to run this playbook against this inventory
with the extra variables file.

```
./run
```

## Doesn't work out of the box

It uses a container as the inventory host and `podman` to start
that container. As such it doens't even fully work becuase the container
does not come with `sudo` which is required.  So if you do run this role
against this container, you will fail at this step with this error:

```
TASK [osc.open_ondemand : Install the rpm repo's key] ***********************************************************************************************************************************
fatal: [rocky]: FAILED! => {"changed": false, "module_stderr": "/bin/sh: sudo: command not found\n", "module_stdout": "", "msg": "MODULE FAILURE\nSee stdout/stderr for the exact error", "rc": 127}

PLAY RECAP ******************************************************************************************************************************************************************************
rocky                      : ok=2    changed=0    unreachable=0    failed=1    skipped=33   rescued=0    ignored=0
```

That's OK becuase this is only meant to be an example to get started
so that you can run the real role against a real inventory.