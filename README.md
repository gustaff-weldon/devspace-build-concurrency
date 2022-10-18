This repository contains multiple dummy devspace projects.
main-project depends on projects a-d, project-a depends on project-e.

To reproduce issue.

Run test for sequential flag:

```
cd main-project
devspace deploy  --build-sequential
```

observe how mulitple builds are started and their output is intertwined.

Now, clean up devspace cache:
```
find ../ -name .devspace | xargs rm -rf
```

And run test for concurrent builds flag:
```
devspace deploy  --max-concurrent-builds 1
```

Observe how mulitple builds are started and their output is intertwined.
