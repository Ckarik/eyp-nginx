# nginx

#### Table of Contents

1. [Overview](#overview)
2. [Module Description - What the module does and why it is useful](#module-description)
3. [Setup - The basics of getting started with nginx](#setup)
    * [What nginx affects](#what-nginx-affects)
    * [Setup requirements](#setup-requirements)
    * [Beginning with nginx](#beginning-with-nginx)
4. [Usage - Configuration options and additional functionality](#usage)
5. [Reference - An under-the-hood peek at what the module is doing and how](#reference)
5. [Limitations - OS compatibility, etc.](#limitations)
6. [Development - Guide for contributing to the module](#development)

## Overview

A one-maybe-two sentence summary of what the module does/what problem it solves.
This is your 30 second elevator pitch for your module. Consider including
OS/Puppet version it works with.

## Module Description

If applicable, this section should have a brief description of the technology
the module integrates with and what that integration enables. This section
should answer the questions: "What does this module *do*?" and "Why would I use
it?"

If your module has a range of functionality (installation, configuration,
management, etc.) this is the time to mention it.

## Setup

### What nginx affects

* A list of files, packages, services, or operations that the module will alter,
  impact, or execute on the system it's installed on.
* This is a great place to stick any warnings.
* Can be in list or paragraph form.

### Setup Requirements

If your module requires anything extra before setting up (pluginsync enabled,
etc.), mention it here.

### Beginning with nginx


nginx proxypass minimal configuration:

```puppet
class { 'nginx':
}

nginx::vhost { 'example':
}

nginx::proxypass { 'example':
  proxypass_url => 'http://127.0.0.1:5601'
}
```

nginx proxypass minimal configuration using yaml syntax:

```yaml
---
classes:
  - nginx
nginx::add_default_vhost: false
nginxvhosts:
  default:
    default: true
nginxproxypass:
  default:
    proxypass_url: http://127.0.0.1:5601
```

## Usage

Put the classes, types, and resources for customizing, configuring, and doing
the fancy stuff with your module here.

## Reference

Here, list the classes, types, providers, facts, etc contained in your module.
This section should include all of the under-the-hood workings of your module so
people know what the module is touching on their system but don't need to mess
with things. (We are working on automating this section!)

## Limitations

Tested on CentOS 6

## Development

We are pushing to have acceptance testing in place, so any new feature should
have some test to check both presence and absence of any feature
