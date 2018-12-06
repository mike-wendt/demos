---
layout: default
title: Home
nav_order: 1
permalink: /
---


# Explore and learn about RAPIDS
{: .fs-9 }

Leverage containers, demos, and notebooks from the RAPIDS team and community to explore RAPIDS hands on. For more information about RAPIDS visit [rapids.ai](http://rapids.ai)
{: .fs-6 .fw-300 }

[Get started now](#getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View RAPIDS on GitHub](https://github.com/rapidsai){: .btn .fs-5 }

---

## Getting started

### Prerequisites

*   GPU support
    *   Compute Capability 6.0 (Pascal Architecture) or higher
*   CUDA support
    *   9.2 or newer
*   OS support
    *   Ubuntu 16.04 LTS (tested and confirmed working)
*   Docker support
    *   [Docker CE v18+](https://docs.docker.com/install/linux/docker-ce/ubuntu/) - _apt for Ubuntu 16.04 **doesn't** include v18+ by default_
    *   [nvidia-docker v2+](https://github.com/nvidia/nvidia-docker/wiki/Installation-%28version-2.0%29)

### Start Container and Notebook Server

```bash
$ docker pull rapidsai/rapidsai:cuda9.2_ubuntu1604
$ docker run --runtime=nvidia \
        --rm -it \
        -p 8888:8888 \
        -p 8787:8787 \
        -p 8786:8786 \
        rapidsai/rapidsai:cuda9.2_ubuntu1604
jupyter@container:/rapids/notebooks/$ source activate rapids
(rapids) jupyter@container:/rapids/notebooks/$ bash utils/start_jupyter.sh
```
**NOTE:** This will run JupyterLab on port 8888 on your host machine

### Use JupyterLab to Explore the Notebooks

Notebooks can be found in two directories within the container:

* `/rapids/notebooks/cuml` - cuML demo notebooks
  * **NOTE:** Data for these notebooks is included in the docker and requires the following command to be run for decompression: `cd /rapids/notebooks/cuml/data && gunzip cuml/data/mortgage.npy.gz`
* `/rapids/notebooks/mortgage` - cuDF, Dask, XGBoost demo notebook
  * This notebook requires additional data to be downloaded, and setup see notebook `E2E.ipynb` for more details

## Custom data and advanced usage 

See the [RAPIDS Demo Container](containers/rapids-demo) page for more information about using custom datasets.

## Issues

File an issue [here](https://github.com/rapidsai/demos/issues/new) for any unexpected problems encountered with any of the information on this site.
