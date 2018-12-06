---
layout: default
title: Home
nav_order: 1
permalink: /
---


# Explore and Learn About RAPIDS
{: .fs-9 }

Leverage containers, demos, and notebooks from the RAPIDS team and community to explore RAPIDS hands on. For more information about RAPIDS visit [rapids.ai](http://rapids.ai)
{: .fs-6 .fw-300 }

[Get started now](#run-the-rapids-container){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View RAPIDS on GitHub](https://github.com/rapidsai){: .btn .fs-5 }

---

## Run the RAPIDS Container

The RAPIDS Docker containers are configured to run RAPIDS and provide example data/notebooks to get started quickly.

### Container Host Prerequisites

* NVIDIA Pascal™ GPU architecture or better
* CUDA 9.2 or 10.0 compatible nvidia driver
* Ubuntu 16.04 or 18.04
* Docker CE v18+
* [nvidia-docker](https://github.com/nvidia/nvidia-docker/wiki/Installation-%28version-2.0%29) v2+

### Start Container and Notebook Server

```bash
$ docker pull rapidsai/rapidsai:cuda9.2_ubuntu16.04
$ docker run --runtime=nvidia \
        --rm -it \
        -p 8888:8888 \
        -p 8787:8787 \
        -p 8786:8786 \
        rapidsai/rapidsai:cuda9.2_ubuntu16.04
jupyter@container:/rapids/notebooks/$ source activate rapids
(rapids) jupyter@container:/rapids/notebooks/$ bash utils/start-jupyter.sh
```
**NOTE:** This will run JupyterLab on port 8888 on your host machine

### Use JupyterLab to Explore the Notebooks

Notebooks can be found in two directories within the container:

* `/rapids/notebooks/cuml` - cuML demo notebooks
  * These notebooks have data pre-loaded in the container image and requires the following command to be run for decompression: `cd /rapids/notebooks/cuml/data && gunzip mortgage.npy.gz`
* `/rapids/notebooks/mortgage` - cuDF, Dask, XGBoost demo notebook
  * This notebook requires download of [Mortgage Data](datasets/mortgage-data), see notebook `E2E.ipynb` for more details

## Custom Data and Advanced Usage 

See the [RAPIDS Demo Container](containers/rapids-demo) page for more information about using custom datasets.

## Issues

File an issue [here](https://github.com/rapidsai/demos/issues/new) for any unexpected problems encountered with any of the information on this site.
