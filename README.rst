======
Saltrunner
======

Saltrunner contains a CLI script which uses libpepper to access a remote
`salt-api`__ instance.

The ``saltrunner`` CLI script allows users to execute Salt commands from computers
that are external to computers running the ``salt-master`` or ``salt-minion``
daemons as though they were running Salt locally.

.. __: https://github.com/saltstack/salt-api

Usage: saltrunner [opts]
-----

 A CLI interface to a remote salt-api instance

Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -c CONFIG             Configuration file location. Default is a file path in
                        the "SALTRUNNERRC" environment variable or ~/.saltrunnerrc.
  -v                    Increment output verbosity; may be specified multiple
                        times
  -H, --debug-http      Output the HTTP request/response headers on stderr

  Saltrunner ``salt`` Options:
    Mimic the ``salt`` CLI

    -t TIMEOUT, --timeout=TIMEOUT
                        Specify wait time (in seconds) before returning
                        control to the shell
    -f, --fail          Optional, fail if minions do not respond

  Targeting Options:
    Target which minions to run commands on

    -E, --pcre          Target hostnames using PCRE regular expressions
    -L, --list          Specify a comma delimited list of hostnames
    -G, --grain         Target based on system properties
    --grain-pcre        Target based on PCRE matches on system properties

  Authentication Options:
    Authentication credentials can optionally be supplied via the
    environment variables: SALTAPI_URL, SALTAPI_USER, SALTAPI_PASS,
    SALTAPI_EAUTH.

    -s SALTAPIURL, --saltapi-url=SALTAPIURL
                        Specify the host url.  Defaults to
                        http://localhost:8080
    -a EAUTH, --auth=EAUTH, --eauth=EAUTH, --extended-auth=EAUTH
                        Specify the external_auth backend to authenticate
                        against and interactively prompt for credentials
    -u USERNAME, --username=USERNAME
                        Optional, defaults to user name. will be prompt if
                        empty unless --non-interactive
    -p PASSWORD, --password=PASSWORD
                        Optional, but will be prompted unless --non-
                        interactive
    -z, --non-interactive
                        Optional, fail rather than waiting for input


Current status
--------------

The project is currently pre-alpha.

Please feel free to get involved by sending pull requests.

.. __: https://github.com/davebo/saltrunner

Acknowledgments
--------------

This project is a tweak of the CLI script provided by salt-pepper

.. __: https://github.com/saltstack/pepper

