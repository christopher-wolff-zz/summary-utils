# Summary utils for TensorBoard RL

This repository provides TensorFlow summary methods to log TensorFlow event
files.

Each module provides two methods: `op` and `pb`. The former creates a TensorFlow
summary op and the latter creates a TensorFlow Proto Buffer object that a
`tf.FileWriter` can use to log an event.

## Installing

Start by cloning this repository and then running the following command.

```
pip install ROOT_DIR
```

where `ROOT_DIR` is a path to the project's root directory.

## Example usage

The following is a simple example of how you may create a TensorFlow event file
for a 3 by 2 matrix of random numbers.

```
import tensorflow as tf
import numpy as np
from summary_utils import matrix_summary

writer = tf.summary.FileWriter('/tmp/summary_example')
summary = matrix_summary.pb(tag="m1", data=np.random.rand(3, 2))
writer.add_summary(summary)
writer.close()
```
