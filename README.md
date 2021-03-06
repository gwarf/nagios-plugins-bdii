# nagios-plugins-bdii

This nagios probe is used to monitor BDII.
It provides check_bdii_entries support for Nagios.
`nagios-common` dependency can be found in EPEL.

BDII documentation is available with the main [BDII documentation](https://gridinfo-documentation.readthedocs.io/)

## Building packages

A Makefile allowing to build source tarball and packages is provided.

### Building a RPM

The required build dependencies are:

- rpm-build
- make
- rsync
- openldap-devel

```sh
# Checkout tag to be packaged
git clone https://github.com/EGI-Foundation/nagios-plugins-bdii.git
cd nagios-plugins-bdii
git checkout X.X.X
# Building in a container
docker run --rm -v $(pwd):/source -it centos:7
yum install -y rpm-build make rsync gcc openldap-devel
cd /source && make rpm
```

The RPM will be available into the `build/RPMS` directory.

## Installing from source

This procedure is not recommended for production deployment, please consider
using packages.

Get the source by cloning this repo and do a `make install`.

## History

This work started under the EGEE project, and was hosted and maintained for a
long time by CERN.
This is now hosted here on GitHub, maintained by the BDII community with
support of members of the EGI Federation.
