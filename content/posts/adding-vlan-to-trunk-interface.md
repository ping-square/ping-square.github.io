+++
title = 'Adding Vlan to Trunk Interface'
date = 2024-09-14T14:58:52-05:00
draft = true
+++

# What is all about
When you are scripting configuration changes, it is best to use the add and remove keywords because they are more prescriptive. A common mistake is to use the switchport trunk allowed vlan vlan-ids command to list only the VLAN that is being added. This results in the current list being overwritten, causing traffic loss for the VLANs that were omitted.

# the goal of this arcticle is to create a lab which is a reflect of this issue.