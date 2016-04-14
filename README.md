# Drupal Development Environment

Some scripts to help set up and work with a Drupal environment, for use when
working on [tmgmt_zanata](https://github.com/zanata/tmgmt_zanata) and
[tmgmt_express_checkout](https://github.com/zanata/tmgmt_express_checkout).

*The scripts use hard-coded paths for the location of the code and the Drupal
environment, so just deal with it (or update the scripts to use a configurable
location)*

## Get the module code

Run these once to get started:

```
scripts/get-code-tmgmt_express_checkout
scripts/get-code-tmgmt_zanata
```

These scripts clone the code from GitHub to a hard-coded location, and set up
a remote for the associated Drupal project for each. Run them once to get
started.

## Install/start the Drupal server

Run this at the start of each development session:

```
scripts/install-and-run-drupal
```

This script installs the Drupal management tool "drush", then uses it to set
up a Drupal install, start the Drupal server and add all the modules needed by
tmgmt_zanata and tmgmt_express_checkout.

If it looks like the Drupal install is already present, it will just use it.

## Deploy new code to the running server

Run these any time you want to see your new code in the server:

```
scripts/copy-to-drupal-tmgmt_express_checkout
scripts/copy-to-drupal-tmgmt_zanata
```

These scripts copy the code from the local git repository into the right place
in the Drupal install. They do what is needed to copy the code without breaking
the running server.


## `git push` to Drupal fails???

Run this once if git complains about something with diffie-hellman-group1-sha1,
then resume whatever you were doing.

```
scripts/drupal-ssh-workaround
```

drupal.org has not updated to use a more recent algorithm for their git ssh.
This script will enable the old algorithm in the current shell so that git can
work.
