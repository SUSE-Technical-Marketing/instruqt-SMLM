---
slug: welcome
id: xbxdnpsnbcr9
type: challenge
title: Welcome to the SMLM/S PoC
teaser: This is the final test challenge, only production changes, please use other challenges to try things
notes:
- type: text
  contents: |
    # Welcome to the SMLM/S PoC


    Please wait while we setup your lab environment.
tabs:
#- id: sdrmk64rbanj
#  title: SMLM UI
#  type: browser
#  hostname: ${SMLM_FQDN}
- title: SMLM UI
  type: website
  url: https://${SMLM_FQDN}
  new_window: true
- title: Bastion Terminal
  type: terminal
  hostname: bastion
difficulty: ""
enhanced_loading: null


difficulty: basic
timelimit: 600
---


Username:
```txt
[[ Instruqt-Var key="SMLM_ADMIN_PASSWORD" hostname="bastion" ]]
```

Password:
```txt
[[ Instruqt-Var key="SMLM_ADMIN_USER" hostname="bastion" ]]
```


> [!NOTE]
> It could be that the browser tab needs to be refreshed after the environment is started.

## Check everything looks ok

- Channels
- Environments
- ...

## Exercise 1

Onboard Ubuntu 24.04 LTS

## Exercise 2

Show we extend support for CentOS 7 by onboarding it with Liberate formula and showing there are new updates and the changes to centos-release, etc..


## Exercise 3

Onboard SLES 15 SP5, upgrade to SP6


Lifecycle Management:
Scheduling and then patching a machine
Recurring actions for all the registered VMs in a group
Ideally show automation with Ansible and salt stack.



## Exercise 4

Audit VMs with openSCAP


## Exercise 5

Lifecycle Management:
 - Scheduling and then patching a machine
 - Recurring actions for all the registered VMs in a group


## Exercise 6

Ideally show automation with Ansible and salt stack.

