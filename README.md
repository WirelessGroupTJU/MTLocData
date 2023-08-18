# MTLocData

Dataset Tags: indoor localization, Wi-Fi fingerprinting, fingerprint update, long-term

## Overview

Due to pervasive deployments of access points (APs) and ubiquities of Wi-Fi-enabled mobile devices, Wi-Fi fingerprinting indoor localization has attracted much attention from both academia and industry in the past decade. However, in practice Wi-Fi fingerprinting system in the long term suffers from gradually deteriorative localization accuracy, leading to poor user experiences. The primary reason is the mismatching between the varied Wi-Fi signals and the stale fingerprint database. However, it is costly to keep high localization accuracy in the long term. We provide this long-term Wi-Fi fingerprinting data to ease research works that address the fingerprint update problem.

Details on the data can be found in our papers on the systems:

[UbiComp' 23] Jiankun Wang, Zenghua Zhao, Mengling Ou, Jiayang Cui, and Bin Wu. Automatic Update for Wi-Fi Fingerprinting Indoor Localization via Multi-Target Domain Adaptation. Proc. ACM Interact. Mob. Wearable Ubiquitous Technol.

The latest updates of the data will be released on Github: <https://github.com/WirelessGroupTJU/MTLocData>

## Data Description

MTLocData provides Wi-Fi fingerprints at 189 locations in the office building and 399 locations in the shopping mall over one year. The collections were interrupted from time to time due to holidays or epidemic of coronavirus. Therefore, in the office building, the experiments are partitioned into two periods: P1 and P2. The former is collected daily in 3 months from September to December 2020. The latter is collected weekly over 9 months from April to December 2021. To obtain a long-term dataset, we combine Office P1 and P2 by downsampling P1 to once-a-week. As a result, Office P1+P2 covers 15 months. In the mall, we collected fingerprints monthly over 13 months. Due to the interruptions, there are only 7 domains (collections) in total. For all datasets, the first collection is used as the source domain, and the others are targets.

In summary, we obtained four different datasets: Office P1, Office P2, Office P1+P2, and Mall.

### Data Format

The downloaded MTLocData should have the following form:

```
data.zip

├── OfficeP1
│ ├── meta.json
│ ├── OfficeP1_1_training.h5
│ ├── OfficeP1_1_testing.h5
│ ├── OfficeP1_2_training.h5
│ ├── OfficeP1_2_testing.h5
│ ├── …

├── OfficeP2
│ ├── meta.json
│ ├── OfficeP2_1_training.h5
│ ├── OfficeP2_1_testing.h5
│ ├── OfficeP2_2_training.h5
│ ├── OfficeP2_2_testing.h5
│ ├── …

├── OfficeP1+P2
│ ├── meta.json
│ ├── OfficeP1+P2_1_training.h5
│ ├── OfficeP1+P2_1_testing.h5
│ ├── OfficeP1+P2_2_training.h5
│ ├── OfficeP1+P2_2_testing.h5
│ ├── …

├── Mall
│ ├── meta.json
│ ├── Mall_1_training.h5
│ ├── Mall_1_testing.h5
│ ├── Mall_2_training.h5
│ ├── Mall_2_testing.h5
│ ├── …
```



Each folder contains the training and testing data of one dataset. It also contains a metafile that records all data collection dates.

Each data file is stored in hdf5 format. It includes the rssis and coordinates for each fingerprint and the bssids for each columns. Each file contains the following data:

- rssis: The matrix of received signal strength indicators. Each row records one fingerprint and each column represents one Access Point.
- cdns: The list of coordinates. Each row records the coordinate of the corresponding row of rssis.
- bssids: The list of BSSIDs (Basic Service Set IDentifiers) for the corresponding columns of rssis.
- RecordsNums: Records numbers of references point or test points.

## Download

The latest updates of the data will be released on Github: <https://github.com/WirelessGroupTJU/MTLocData>

## Reference

The dataset can only be used for research purpose. No commercial applications are allowed.

Please cite the following paper for the use of this dataset in any publications.:

[UbiComp' 23] Jiankun Wang, Zenghua Zhao, Mengling Ou, Jiayang Cui, and Bin Wu. Automatic Update for Wi-Fi Fingerprinting Indoor Localization via Multi-Target Domain Adaptation. Proc. ACM Interact. Mob. Wearable Ubiquitous Technol.

If you have published papers using our dataset, please send to [tjunet@outlook.com](tjunet@outlook.com) with the publication URL.

## Privacy Protection

To protect privacy, we replace the BSSIDs with virtual ones and remove the SSIDs.

## License

The dataset is distributed under the [BSD-3-Clause](https://opensource.org/license/bsd-3-clause/) license.