## The Test Sandbox

The test sandbox is a repo that contains dummy tests that sleep for random times and then pass.

`test_*` directories contain shell scripts that sleep for durations based on the profile of the [Discourse](https://github.com/discourse/discourse) open source project.

Test files and their executable command are specified in the `.turbo_test.yml` configuration file:

```
test_suite:
  command: sh

  files:
    - test_17_mins/*sh
```

### 📚[See the TurboTest help pages for more info](https://turbo-test.help/benchmark)














































































