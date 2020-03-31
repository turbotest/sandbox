## The Test Sandbox

The test sandbox is a repo that contains dummy tests that sleep for random times and then pass.

`test_*` directories contain shell scripts that merely sleep for random durations to simulate durations of real tests.

These test files and the command to run them are specified in the `.turbo_test.yml` configuration file, e.g.:

```test_suite:
  command: sh

  files:
    - test_17_mins/*sh
```

You can run an entire directory of tests on the command line like this:
 
`ls -1 test_17_mins/*.sh | xargs sh`


A Vagrant VM configuration file is used to test your configuration file locally before pushing to GitHub; e.g. test that your:

* install/setup is corrrect
* test suite file glob is correct
* test suite command is correct
* YAML is valid etc.