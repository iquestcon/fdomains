FDOMAINS(1)

### NAME

**fdomains** - monitor registered fuzzy matched domain names

### SYNOPSIS

**fdomains**
\[**-m**&nbsp;*recipient*]
\[**-u**]
*domain&nbsp;...*

### DESCRIPTION

**fdomains**
is a utility that will search and return all registered fuzzy matched domain
names.

When run without any options
**fdomains**
will print all matches for each
*domain*
to
*stdout*.
The output will also be saved to a file which will be updated on each run
with the complete list of matches.

The options are as follows:

**-m** *recipient*

> Email output to
> *recipient*
> instead of printing to
> *stdout*.

**-u**

> Only return updates to the saved output file.

### FILES

*~/.fdomains/$domain*

> Default save location and naming convention.

### EXIT STATUS

The **fdomains** utility exits&#160;0 on success, and&#160;&gt;0 if an error occurs.

### EXAMPLES

Display all results to the terminal.

	$ fdomains example.com
	axample.com
	cxamplc.com
	cxample.com
	...

Daily
crontab(5)
entry to alert on newly registered domains.

	0 6 * * * /bin/sh /home/neo/bin/fdomains -m root -u example.com

### SEE ALSO

mail(1),
crontab(5),
cron(8)

### AUTHORS

Sean Davies &lt;[sean@city17.org](mailto:sean@city17.org)&gt;

### CAVEATS

**fdomains**
replies on the Python package
*dnstwist*.

	$ pip install --user dnstwist
