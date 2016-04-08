# Change Log
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/).


## [0.1.0] - 2016-04-08
### Changed

- Removed support for older versions of Ansible. This callback plugin is only for Ansible >=v2.x. Tested on v2.0.1.0.

- Instead of `print`'ing to stdout, made use of the CallbackBase object's `_display.display()` method to show the output. This has the benefit that output will be logged to Ansible's log file as well as being sent to stdout.

- **NOTE:** I've configured the _display.display() method to **only** show the human_log output in the Ansible log file. My reasoning being that I prefer to see the standard Ansible output on stdout and see more detailed / friendly logging in the log file. If you want to see the same human friendly output on screen as well as in the log file, remove the `, log_only=True` bit from line 49 of the human_log.py file.

- Amended the json.dumps() to sort keys when displaying dicts. It makes comparing log output easier.

- Changed the code which deals with the result being a list of strings to simply return the list of strings as a string instead of reformatting their lengths. Again a personal preference as I prefer to see the output as it was produced by the source.

## unversioned - 2015-01-25

- This code was forked from: https://github.com/n0ts/ansible-human_log.git. The author (Naoya Nakazawa) added support for Ansible v2 amongst many other useful changes.

- Which was inspired from: https://github.com/redhat-openstack/khaleesi/blob/master/plugins/callbacks/human_log.py

- Which was originally from: https://gist.github.com/cliffano/9868180. The author (Cliffano Subagio) was the original creator of the human_log.py.

- The blog page about the gist is: http://blog.cliffano.com/2014/04/06/human-readable-ansible-playbook-log-output-using-callback-plugin/
