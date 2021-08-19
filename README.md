# Zulip overview

Zulip is a powerful, open source group chat application that combines the
immediacy of real-time chat with the productivity benefits of threaded
conversations. Zulip is used by open source projects, Fortune 500 companies,
large standards bodies, and others who need a real-time chat system that
allows users to easily process hundreds or thousands of messages a day. With
over 700 contributors merging over 500 commits a month, Zulip is also the
largest and fastest growing open source group chat project.

[![GitHub Actions build status](https://github.com/zulip/zulip/actions/workflows/zulip-ci.yml/badge.svg?branch=master)](https://github.com/zulip/zulip/actions/workflows/zulip-ci.yml?query=branch%3Amaster)
[![coverage status](https://img.shields.io/codecov/c/github/zulip/zulip/master.svg)](https://codecov.io/gh/zulip/zulip/branch/master)
[![Mypy coverage](https://img.shields.io/badge/mypy-100%25-green.svg)][mypy-coverage]
[![code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier)
[![GitHub release](https://img.shields.io/github/release/zulip/zulip.svg)](https://github.com/zulip/zulip/releases/latest)
[![docs](https://readthedocs.org/projects/zulip/badge/?version=latest)](https://zulip.readthedocs.io/en/latest/)
[![Zulip chat](https://img.shields.io/badge/zulip-join_chat-brightgreen.svg)](https://chat.zulip.org)
[![Twitter](https://img.shields.io/badge/twitter-@zulip-blue.svg?style=flat)](https://twitter.com/zulip)
[![GitHub Sponsors](https://img.shields.io/github/sponsors/zulip)](https://github.com/sponsors/zulip)

[mypy-coverage]: https://blog.zulip.org/2016/10/13/static-types-in-python-oh-mypy/

## Getting started

Click on the appropriate link below. If nothing seems to apply,
join us on the
[Zulip community server](https://zulip.readthedocs.io/en/latest/contributing/chat-zulip-org.html)
and tell us what's up!

You might be interested in:

* **Contributing code**. Check out our
  [guide for new contributors](https://zulip.readthedocs.io/en/latest/overview/contributing.html)
  to get started.  Zulip prides itself on maintaining a clean and
  well-tested codebase, and a stock of hundreds of
  [beginner-friendly issues][beginner-friendly].

* **Contributing non-code**.
  [Report an issue](https://zulip.readthedocs.io/en/latest/overview/contributing.html#reporting-issues),
  [translate](https://zulip.readthedocs.io/en/latest/translating/translating.html) Zulip
  into your language,
  [write](https://zulip.readthedocs.io/en/latest/overview/contributing.html#zulip-outreach)
  for the Zulip blog, or
  [give us feedback](https://zulip.readthedocs.io/en/latest/overview/contributing.html#user-feedback). We
  would love to hear from you, even if you're just trying the product out.

* **Supporting Zulip**. Advocate for your organization to use Zulip, become a [sponsor](https://github.com/sponsors/zulip), write a
  review in the mobile app stores, or
  [upvote Zulip](https://zulip.readthedocs.io/en/latest/overview/contributing.html#zulip-outreach) on
  product comparison sites.

* **Checking Zulip out**. The best way to see Zulip in action is to drop by
  the
  [Zulip community server](https://zulip.readthedocs.io/en/latest/contributing/chat-zulip-org.html). We
  also recommend reading Zulip for
  [open source](https://zulip.com/for/open-source/), Zulip for
  [companies](https://zulip.com/for/companies/), or Zulip for
  [working groups and part time communities](https://zulip.com/for/working-groups-and-communities/).

* **Running a Zulip server**. Use a preconfigured [DigitalOcean droplet](https://marketplace.digitalocean.com/apps/zulip),
  [install Zulip](https://zulip.readthedocs.io/en/stable/production/install.html)
  directly, or use Zulip's
  experimental [Docker image](https://zulip.readthedocs.io/en/latest/production/deployment.html#zulip-in-docker).
  Commercial support is available; see <https://zulip.com/plans> for details.

* **Using Zulip without setting up a server**. <https://zulip.com>
  offers free and commercial hosting, including providing our paid
  plan for free to fellow open source projects.

* **Participating in [outreach
  programs](https://zulip.readthedocs.io/en/latest/overview/contributing.html#outreach-programs)**
  like Google Summer of Code.

You may also be interested in reading our [blog](https://blog.zulip.org/) or
following us on [Twitter](https://twitter.com/zulip).
Zulip is distributed under the
[Apache 2.0](https://github.com/zulip/zulip/blob/master/LICENSE) license.

[beginner-friendly]: https://github.com/zulip/zulip/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22

## Zulip Upgrade process

While upgrading zulip setup from. 4.3 to further releases.

We have to check the following things.

1. Create a branch from existing branch named --> zimbra-zulip-upgrade-x-x
where x-x is the major-minor version.

2. Check the differences between prod.txt in 4.3 and the higher version.

3.  Download particular python libraries that. digress from the current version.

using pip download <libname> -d <destination folder>

copy these downloaded wheel files in a folder and upload them in respective folders for uploading in zimbra cloud in
https://files.zimbra.com/downloads/zulip/packages/all-py-deps/

4. Check the differences between files cascading in folder zulip/zimbra with files in zulip/
all customisation regarding zimbra are included in zulip/zimbra
all original zulip files are in root folder zulip

add zimbra customization in zulip files as above.

4. Read zulip release notes for particular release if any more specific changes are required.
https://zulip.readthedocs.io/en/latest/overview/changelog.html

5.  Once changes are complete, we need to follow the upgrade guide for zulip.

    a. Commit the changes on the the branch

    b. Push changes on the branch

6.  Creating new upgraded tar from the changes.

    a. Go to respective build servers.

 

        u18 build - ubuntu@129.213.97.197

        u20 build - ubuntu@132.145.200.135

        cent7 build - opc@129.213.39.166

    b. Pull the changes on the branch zimbra-zulip-upgrade-x-x

         ssh on above servers.

 

         cd zulip

         git checkout <upgrade-branch>

         git pull

    c. Create new tars from the latest code.

        for u18 

        ./tools/build-release-tarball zimbra-installer-u18         

         for u20

         ./tools/build-release-tarball zimbra-installer-u20

         for centos7

         ./tools/build-release-tarball zimbra-installer-centos7

 After creating these tars copy the tars to respective server. <zulip-server-VERSION.tar.gz>

Please read upgrade notes before upgrading 
https://zulip.readthedocs.io/en/latest/overview/changelog.html#upgrade-notes

7. Log in to your Zulip production server and run as root:
/home/zulip/deployments/current/scripts/upgrade-zulip zulip-server-VERSION.tar.gz
