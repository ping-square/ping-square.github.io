+++
title = 'The Native Vlan Catch'
date = 2024-09-14T14:48:14-05:00
draft = true
summary = "How can you make sure that the Native VLAN does not become a trap..."
description = "This is a step-by-step tutorial on how native VLAN can pause a security risk"
draft = true
toc = false
readTime = true
autonumber = false
math = true
tags = ["database", "java"]
showTags = false
hideBackToTop = false
+++

#  About this article
Two hosts on the same subnet could still communicate if one host was connected to an access port associated to VLAN10 and the other host connects to a trunk port configured with a native VLAN of 10. This is not a best practice but demonstrates how there is not an 802.1Q VLAN tag added to the packet on either of the two ports.