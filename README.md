# pyttr logs

The first commit in this repository shows output from the pyttr example scripts when
running them with python3.4 (*.log files).
In one case the pyttr repository was reverted back to a very old commit to make one of the
example scripts run propertly.

The second commit shows output from the pyttr example scripts when running them
with python 3.12 and having done the following edits to the example scripts: https://github.com/robincooper/pyttr/pull/5

See the diff in the output between the python and code versions here: https://github.com/ailomaa/pyttr-logs/commit/9c436c426bc3b48d993032fed0eff1920e036a18

- the output from `example-neurons.py` was identical in both cases
- the diff in the output from `example-records.py` and `example-types.py` has to do with indeterministic ordering caused by how python handles certain array types
- the diff in the output from `example-nu.py` has the same issue with indeterministic ordering, but also there is an integer missing in the matrixes. For example:

```diff
arg1       0  0  0  1  1  1  1  0
c          0  0  1  0  0  0  0  0
believe_n  0  1  0  0  0  0  0  0
- ptype2     2  0  0  1  1  1  0  0
- rel        2  0  0  1  0  0  0  0
- arg0       2  0  0  0  1  0  0  0
- arg1       2  0  0  0  0  1  0  0
+ ptype2     *  0  0  1  1  1  0  0
+ rel        *  0  0  1  0  0  0  0
+ arg0       *  0  0  0  1  0  0  0
+ arg1       *  0  0  0  0  1  0  0
```
