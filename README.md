# IOPLIN 
The project is the keras implementation and simple application of IOPLIN. The source code is placed at /ioplin, the script is placed at /script, the required mini dataset is placed at /miniset, and the predict results shuold placed at /results.

For more details of IOPLIN, please refer to the paper "An Iteratively Optimized Patch Label Inference Network for Automatic Pavement Disease Detection". You can find the paper in https://arxiv.org/pdf/2005.13298

## Installation

### Requirements

* `Keras == 2.2.4` / `TensorFlow <= 1.15.0`
* `keras_applications >= 1.0.7`
* `scikit-image`
* `opencv-python`
* `efficientnet <= 0.0.3`

### Installing from the source

```bash
$ python setup.py install
```

## Examples
* *Initializing the model*:

```python
# models can be build with Keras

import ioplin

model = ioplin.init_model()  

```

* *Loading the pre-trained weights*:

```python
import ioplin

model = ioplin.load_model('path/to/model.h5')
```

* *Predicting*:

```python
import ioplin

pre = ioplin.predict(model,data)
```

* *Pretrain and train*:

```python
import ioplin

model = ioplin.pretrain(model,data_x,data_y)

model = ioplin.train(model,data_x,data_y)
```

## Script

### Pretrain
```bash
$ python pretrain.py --batch_size=32 --epoch=10
```
### train
```bash
$ python train.py --batch_size=32 --epoch=10 --path_pretrain_model=path/pretrain_model.h5
```
### Predict

#### if you want to use the trained IOPLIN model to predict data, you should download the model file and  enter:
```bash
$ python predict.py --path_model=path/trained_model.h5 --positive_index=0 
```
#### if you want to use the IOPLIN model trained by yourself to predict data, you only need enter:
```bash
$ python predict.py --path_model=path/your_model.h5
```