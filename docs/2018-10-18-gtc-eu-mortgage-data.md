---
layout: default
has_children: false
nav_order: 2
title: 2018 GTC EU - Mortgage Demo
---

# 2018-10 GTC EU - Mortgage Demo

### Data Source

Dataset is derived from [Fannie Mae's Single-Family Loan Performance Data](http://www.fanniemae.com/portal/funding-the-market/data/loan-performance-data.html) with all rights reserved by Fannie Mae. This processed dataset is redistributed with permission and consent from Fannie Mae.

For the full raw dataset visit [Fannie Mae](http://www.fanniemae.com/portal/funding-the-market/data/loan-performance-data.html) to register for an account and to download.

### Using Data with RAPIDS Container

The RAPIDS container hosted on our [Docker Hub](https://hub.docker.com/r/rapidsai/rapidsai/) has notebooks that use the following datasets. 
1. Download the datasets below inside the container using `wget` or to the local host and use a docker volume mount to `/rapids/data/mortgage`
2. Make directories for the data
```
mkdir -p /rapids/data/mortgage/acq /rapids/data/mortgage/perf
```
3. Untar the acquisition data using `tar xvf acquisition-all-quarters.tar`
4. Move all `Acq*` files into `/rapids/data/mortgage/acq`
5. Untar the performance data using `tar xvf performance-all-quarters.tar`
6. Move all `Perf*` files into `/rapids/data/mortgage/perf`
7. Confirm that the following directory structure exists in `/rapids/data/mortgage`
```
/rapids/data/mortgage/acq/         <- all acquisition data
/rapids/data/mortgage/perf/        <- all performance data
/rapids/data/mortgage/names.csv    <- lender name normalization
```

### All Quarters in a Single TAR Download (17 years 2000-2016)
* [All acquisition data](https://s3.us-east-2.amazonaws.com/rapidsai-data/201810-gtc-eu-mortgage-data/all-quarters/acquisition-all-quaters.tar) [845 MB]
* [All performance data](https://s3.us-east-2.amazonaws.com/rapidsai-data/201810-gtc-eu-mortgage-data/all-quarters/performance-all-quarters.tar) [22.1 GB]
* [Loan name normalization](https://s3.us-east-2.amazonaws.com/rapidsai-data/201810-gtc-eu-mortgage-data/names.csv) [3.5 KB]
