ucd-data-fetch(1) -- Fetch user-data and ssh keys from cloud services
=====================================================================

## SYNOPSIS

`/usr/bin/ucd-data-fetch <aws|oci|tencent>`

## DESCRIPTION

`ucd-data-fetch` is a helper agent program that fetches openstack user-data
from the http://169.254.*/ service, as well as the SSH pubkey
provided to the cloud instance. After fetching the two pieces of data,
ucd-data-fetch combines them into a valid `#cloud-config` user-data text
block and passes the output to `ucd`(1) for processing/execution.

The user-data file is currently only fetched for aws instances.

## OPTIONS

The only parameter supported is the name of the cloud service provider, and
can be `aws`, `oci` or `tencent`. It is required, and if not passed as
argument 1, will cause the program to terminate with an error message.

## EXIT STATUS

On success, 0 is returned, a non-zero failure code otherwise. The exit
code returned may be the exit code of the subsequent `ucd` program
execution.

## COPYRIGHT

 * Copyright (C) 2017-2019 Intel Corporation, License: CC-BY-SA-3.0

## SEE ALSO

`ucd`(1)

## NOTES

Creative Commons Attribution-ShareAlike 3.0 Unported

 * http://creativecommons.org/licenses/by-sa/3.0/
